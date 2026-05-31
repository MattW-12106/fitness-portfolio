# High Level Architecture - High-level sequence diagram

1. App Initialisation
 ```mermaid
 sequenceDiagram
  actor Player
  participant Browser as Browser / UI
  participant Webcam as Webcam API
  participant MP as MediaPipe Pose
  participant API as Express API
  participant Facade
  participant DB as Database

  Player->>Browser: Open Sky Hop app
  Browser->>API: GET /api/auth/verify-token
  API->>Facade: verifyToken(jwt)
  Facade->>DB: findById(userId)
  DB-->>Facade: User record
  Facade-->>API: { valid: true, userId }
  API-->>Browser: 200 OK → skip login

  alt Permission granted
    Browser->>Webcam: navigator.mediaDevices.getUserMedia()
    Webcam-->>Browser: Video stream ready
    Browser->>MP: loadModel(pose_landmarker)
    MP-->>Browser: Model loaded
    Browser-->>Player: Show "Start Game" screen
  else Permission denied
    Webcam-->>Browser: Error: NotAllowedError
    Browser-->>Player: Show permission error + retry
  end
 ```

2. Start of the game
```mermaid
sequenceDiagram
  actor Player
  participant Browser as Browser / UI
  participant GE as Game Engine
  participant Scene as Sky Hop Scene
  participant SB as Scoreboard
  participant API as Express API
  participant Facade
  participant DB as Database

  Player->>Browser: Select mode (Branch Hopper / Lily Leaper)
  Browser->>GE: init(mode, difficulty)
  GE->>Scene: loadScene(theme)
  Note right of Scene: Branch Hopper = push-up theme<br/>Lily Leaper = squat theme
  Scene-->>GE: Scene assets ready
  GE->>SB: reset()
  SB-->>GE: Rep counter : 0
  GE->>API: GET /api/users/:id/stats
  API->>Facade: getUserStats(userId)
  Facade->>DB: findByUser(userId)
  DB-->>Facade: SessionHistory[]
  Facade-->>API: { bestScore, totalReps }
  API-->>GE: 200 OK { stats }
  GE->>SB: setPersonalBest(score)
  GE-->>Browser: Render first frame
  Browser-->>Player: Countdown 3… 2… 1… Go!
```

3. Game Loop
```mermaid
sequenceDiagram
  participant Webcam
  participant MP as MediaPipe Pose
  participant GE as Game Engine
  participant Scene as Sky Hop Scene
  participant SB as Scoreboard
  participant Canvas as Canvas / UI
  participant API as Express API
  participant Facade
  participant DB as Database

  loop Runs every animation frame (~60fps)
    Webcam->>MP: raw video frame
    MP->>GE: detectPose(frame)
    GE->>GE: classifyMove(landmarks)

    alt Valid rep detected
      GE->>Scene: triggerJump(character)
      Scene-->>GE: Jump animation done
      GE->>SB: incrementRep()
      SB->>Canvas: Update rep counter
      Canvas-->>SB: Rendered
    else Partial / no movement
      GE->>Scene: idleState()
      GE->>Canvas: Render skeleton overlay
    end

    GE->>API: POST /api/sessions/heartbeat
    API->>Facade: updateSnapshot(sessionId, reps)
    Facade->>DB: upsert(sessionId, repCount)
    DB-->>Facade: OK
    Facade-->>API: ack
    API-->>GE: 202 Accepted
  end
```

4. End of the game
```mermaid
sequenceDiagram
  participant GE as Game Engine
  participant Scene as Sky Hop Scene
  participant SB as Scoreboard
  participant Browser as Browser / UI
  participant API as Express API
  participant Facade
  participant DB as Database
  actor Player

  GE->>GE: checkWinCondition()
  Note right of GE: e.g. target reps reached<br/>or timer expired

  alt Target reps reached
    GE->>Scene: triggerCelebration()
    Scene-->>Browser: Play win animation 🎉
  else Time expired
    GE->>Scene: triggerTimeUp()
    Scene-->>Browser: Play time-up animation
  end

  GE->>API: POST /api/sessions { reps, time, mode }
  API->>Facade: saveSession(dto)
  Facade->>DB: sessions.create(data)
  DB-->>Facade: Session { id, score }
  Facade->>DB: leaderboard.upsert(userId, score)
  DB-->>Facade: rank: 3
  Facade-->>API: { sessionId, rank, badges[] }
  API-->>GE: 201 Created { rank, badges }
  GE->>SB: rankResult(rank)
  SB-->>Browser: Render final score + leaderboard
  Browser-->>Player: Show results screen
```

5. Login / Authentication
```mermaid
sequenceDiagram
  actor Player
  participant Browser as Browser / UI
  participant Client as API Client
  participant API as Express API
  participant Facade
  participant DB as Database

  Player->>Browser: Open login page
  Browser-->>Player: Render login form
  Player->>Browser: Submit email + password
  Browser->>Client: login(email, password)
  Client->>API: POST /api/auth/login
  API->>Facade: authenticateUser(creds)
  Facade->>DB: findByEmail(email)

  alt Valid credentials
    DB-->>Facade: User record
    Facade-->>API: { token, userId }
    API-->>Client: 200 OK { token }
    Client-->>Browser: store token, resolve()
    Browser-->>Player: Redirect → game home
  else Invalid credentials
    DB-->>Facade: null
    Facade-->>API: throw AuthError
    API-->>Client: 401 Unauthorised
    Client-->>Browser: reject(error)
    Browser-->>Player: Show "Invalid email or password"
  end
```

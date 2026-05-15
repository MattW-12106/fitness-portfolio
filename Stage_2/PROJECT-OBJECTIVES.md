# 🎯 Project Objectives

## 📌 Project Purpose
The purpose of this project is to create a fitness web application that uses Mediapipe motion tracking to make exercise more interactive and engaging through games. Many people struggle to stay consistent with working out due to lack of motivation, so our goal is to combine fitness and gaming to encourage users to stay active in a more enjoyable way.

This project is also an opportunity for our team to explore real-time motion tracking, game interaction, and fullstack web development in a collaborative environment.

---

## ✅ MVP Objectives

### 1. Create an Interactive Fitness Experience
Develop a browser-based application where users can interact with simple fitness games using body movements tracked through their camera.

### 2. Encourage User Motivation and Consistency
Implement features such as XP, levels, and daily streaks to motivate users to continue exercising and build healthier habits over time.

### 3. Demonstrate Real-Time Motion Tracking Integration
Integrate Mediapipe pose detection into the application and connect user movements directly to gameplay mechanics in real time.

---

## Stakeholders and Team Roles

## Purpose
To document who is involved in or affected by the project and their respective responsibilities.

## Stakeholders

### Internal 
The Team members are Patrick, Anthonia, Matt and Karen

### External
- End-users: individuals seeking webcam-based fitness experiences
- Potential B2B clients: corporate wellness programs with employees expected to seat for a high number of hours, rehabilitation clients involving movements 

## Team Roles 
| Team Member | Major Role | Minor Role | Responsibilities |
|---|---|---|---|
| Karen | Computer Vision / Motion Engineer | Project Manager & Documentation | MediaPipe pose detection, game logic architecture, project coordination |
| Patrick | Fullstack / Backend Engineer | QA / Testing | Server-side logic, API development, database, quality assurance |
| Anthonin | Frontend / UI Engineer | DevOps | UI implementation, deployment pipeline, CI/CD |
| Matt | Game Logic Engineer | UI/UX Designer | Game mechanics, scoring systems, visual design |

> Project Manager responsibilities are shared across all members to ensure equal experience, per team agreement.

---

## Task 2 - Project Scope

**IN-SCOPE**

- Browser-based fitness web application using a webcam for motion tracking
- Body movement detection using MediaPipe pose tracking
- One playable mini-game controlled by physical movement (e.g. squats or arm raises)
- A technical warmup (Check Camera settings)
- Tracking user exercise level / XP mode
- User dashboard to show exercise history
- Light and dark mode user interface

**OUT-SCOPE**

- Native mobile applications for iOS or Android
- Integration with wearable fitness devices or smartwatches
- Integration with Fitness tracking app on phone
- Voice over on certain exercise to encourage user to hit target runs

## 🧠 Expected Outcome
By the end of the MVP, the team aims to deliver a working prototype that demonstrates how motion tracking and gamification can be combined to create a more engaging fitness experience. The project will also help the team strengthen skills in frontend development, backend systems, teamwork, and software integration.

# A relatively concise Risk Assessment of our Fitness App!!

## Overall Accuracy
1. Pose Estimation Accuracy: MediaPipe's pose landmark model was trained primarily on general human imagery, not sport/exercise-specific datasets. This means that joint angle miscalculation or subtle errors in landmark placement (e.g., shoulder vs. elbow positioning) can cause the app to approve dangerously poor form (or not a valid form at all).
2. Occlusion failures: so basically when body parts overlap (e.g., a lunge where the front leg obscures the back knee), landmarks either disappear or are estimated with low confidence, making real-time feedback unreliable.
3. Edge-case body types: the model performs less consistently on users with non-average proportions, mobility limitations, or who wear loose clothing that obscures body contours.

## Following that we also have the obvious hardware and environmental dependancies/potential issues: 
1. Lighting:  low light, backlighting, or shadows degrade landmark confidence (ability to recognise what it's looking at) significantly. 
2. Camera angle and distance: seeming as the model requires a largely unobstructed, reasonably close view; most users probably won't naturally position their phone or device optimally.
3. Device performance: This one is pretty self-explanatory but older hardware may not be able to keep up a framerate required for mediapipe to accurately analyse what the user is doing.

## Potential Legal Issues!! (YAY!!)
For this one we have 2 very important points.
1. Negligence claims: If a user follows our app's feedback and is injured, we could face liability, particularly if the feedback was demonstrably wrong due to a known model limitation.
2. Mitigations: Strong terms of service, explicit disclaimers ("not a substitute for a qualified trainer"), and consulting a healthcare/legal professional before launch are essential!! Otherwise there may be issues there.

## There are other potential issues too: 
1. Mediapipe may get updates which can break the API during or after development (unlikely to be within the scope of our development cycle but still something to think about.
2. Don't monitor or sell any data for people using the app!! (i.e., camera footage, or personaly details of users)

---

## High-Level Plan

## Project Timeline

| Stage | Phase | Status |
|---|---|---|
| Stage 1 | Idea Development | Completed |
| Stage 2 | Project Charter Development | Current |
| Stage 3 | Technical Documentation | Upcoming |
| Stage 4 | MVP Development | Upcoming |
| Stage 5 | Project Closure | Upcoming |

---

## Milestones & Deliverables

- **Week 1-2:** Team formation, idea generation, and role assignment
- **Week 3-4:** Project Charter creation — stakeholders, scope, risks, and objectives defined
- **Week 5-6:** Technical documentation finalised — architecture, stack, and API design
- **Week 7-10:** MVP Development — core game loop, MediaPipe integration, and frontend
- **Week 11-12:** Final presentation, demo, and project closure

---
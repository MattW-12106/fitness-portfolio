# MoveVerse - User Stories

## Overview

MoveVerse is a fitness-based web application that combines exercise tracking and gamification through motion-controlled gameplay. Users can create accounts, track their exercise progress, view performance statistics, and interact with the application using body movements detected through camera-based pose tracking.

---

# User Stories & Acceptance Criteria

## 1. User Registration

### User Story

As a new user, I want to create an account with my email and password, so that I can save my progress and access the app on future visits.

### Acceptance Criteria

* The signup form accepts:

  * Email address
  * Username
  * Password
* Input validation is performed on all fields.
* Users cannot register using an email address that already exists in the system.
* If a duplicate email is entered, a clear and descriptive error message is displayed.
* Upon successful registration, the user is redirected to the homepage.

---

## 2. User Login

### User Story

As a returning user, I want to log in with my credentials, so that I can resume my progress and stats where I left off.

### Acceptance Criteria

* The login form accepts:

  * Email address
  * Password
* User credentials are validated against stored account information.
* Invalid credentials display an appropriate error message.
* Upon successful authentication, the user is redirected to the homepage.

---

## 3. Camera Warm-Up & Pose Detection

### User Story

As a user, I want to go through a camera check before starting a game, so that I know my pose tracking is working correctly before my session begins.

### Acceptance Criteria

* Camera permission is automatically requested when the warm-up screen loads.
* A live camera feed is displayed to the user.
* A MediaPipe skeleton overlay is rendered on top of the camera feed.
* A status indicator clearly displays whether a valid pose has been detected.
* Users cannot proceed to gameplay until pose detection is successfully confirmed.

---

## 4. Motion-Controlled Exercise Gameplay

### User Story

As a user, I want to play a motion-controlled game that requires me to perform a real exercise.

### Acceptance Criteria

* At least one exercise (e.g., squats) is tracked using MediaPipe Pose.
* Repetitions are counted only when the exercise movement is performed correctly.
* The application validates the full movement range before incrementing the repetition count.
* Real-time feedback is provided during gameplay.
* Exercise data is recorded for future progress tracking.

---

## 5. Activity Dashboard & Progress Tracking

### User Story

As a user, I want to view a dashboard showing my activity history and stats, so that I can track my improvement over time.

### Acceptance Criteria

* The dashboard displays:

  * Total sessions completed
  * Total repetitions performed
  * Current level
  * Experience points (XP)
* Recent session history is displayed in either:

  * A list view, or
  * A chart/graph view
* Each session record includes:

  * Date completed
  * Score achieved
* Dashboard statistics update automatically after each completed session.
* Data always reflects the most recently completed activity.

---

## 6. Theme Preferences

### User Story

As a user, I want to toggle between light and dark mode, so that I can use the app comfortably in different lighting conditions.

### Acceptance Criteria

* A theme toggle is available from every page within the application.
* The toggle is accessible through a common navigation component (e.g., navbar).
* Users can switch between:

  * Light Mode
  * Dark Mode
* The selected theme is applied immediately across the application.
* Theme preference persists between sessions.

---

# Core Features Summary

| Feature             | Description                                     |
| ------------------- | ----------------------------------------------- |
| User Authentication | Account registration and login functionality    |
| Camera Validation   | Pre-game camera and pose detection verification |
| Motion Tracking     | Exercise detection using MediaPipe Pose         |
| Exercise Gameplay   | Motion-controlled fitness gaming experience     |
| Progress Dashboard  | Activity history, levels, XP, and statistics    |
| Theme Customization | Light and dark mode support                     |

---

# Technical Requirements

### Frontend

* Responsive web interface
* Light/Dark theme support
* Live camera feed rendering
* Real-time pose visualization

### Backend

* User authentication and account management
* Session and exercise data storage
* Dashboard statistics aggregation

### Computer Vision

* MediaPipe Pose integration
* Real-time skeleton tracking
* Exercise form validation
* Repetition counting logic

### Data Storage

* User accounts
* Session history
* Repetition counts
* XP and level progression
* Theme preferences

---

# Success Criteria

The application is considered complete when:

1. Users can successfully register and log in.
2. Camera and pose detection verification works before gameplay.
3. At least one exercise can be accurately tracked and counted.
4. Exercise results are saved and reflected on the dashboard.
5. Users can monitor progress through statistics and session history.
6. Light and dark mode are available and accessible throughout the application.

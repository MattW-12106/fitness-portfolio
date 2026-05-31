# Gamified Fitness App — React Component Architecture

## Overview

This document outlines the React component structure for the gamified fitness app, from the root entry point down to individual pages.

---

## Component Tree

```
APP (Root)
├── ThemeContext       — Light/Dark mode
├── AuthContext        — Stores user token
└── Router             — Browser routing
         │
         ▼
    Reusable Components
    ├── Button         — colour, size, onClick
    ├── Header         — Navbar, user icon
    ├── Footer         — Links, branding
    ├── ErrorBanner    — Error display details
    └── Loader         — Spinner
         │
         ▼
       Pages
    └── Home → Login/Register → Warm Up → Exercise/Game → Dashboard → Leaderboard
```

---

## Layers

### 1. App — Root Component
The top-level entry point. Wraps the entire application in global providers.

### 2. Contexts
| Context | Purpose |
|---|---|
| `ThemeContext` | Manages light/dark mode preference |
| `AuthContext` | Stores and shares the user auth token |
| `Router` | Handles browser-based navigation and route protection |

### 3. Reusable Components
Shared UI building blocks consumed by all pages.

| Component | Props / Role |
|---|---|
| `Button` | `color`, `size`, `onClick` |
| `Header` | Navbar, user icon, theme toggle |
| `Footer` | Links, branding |
| `ErrorBanner` | Displays error messages |
| `Loader` | Spinner for async states |

### 4. Pages
The main views, following the user workflow in sequence:

| Page | Purpose |
|---|---|
| **Home** | App landing and overview |
| **Login / Register** | User authentication |
| **Warm Up** | Camera check, body-in-frame detection |
| **Exercise / Game** | Motion tracking, rep counting, XP earning |
| **Dashboard** | Level, XP, streaks, weekly stats |
| **Leaderboard** | Ranked list of top players |

---

## User Flow

```
Home  → Login → Warm Up → Exercise/Game → Dashboard → Leaderboard
```

---

## Key Design Decisions

- **Contexts at root level** ensure theme and auth state are accessible to every component via `useTheme()` and `useAuth()` hooks.
- **Reusable components** are decoupled from page logic — they receive data via props only.
- **Pages** are lazy-loaded via React Router to keep the initial bundle small.
- The **Warm Up** page acts as a gate before the Exercise page, ensuring the camera and lighting are ready.
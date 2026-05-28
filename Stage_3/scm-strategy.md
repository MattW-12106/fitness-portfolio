# 🔧 MoveVerse SCM Strategy

## 📖 Purpose

This document defines the Software Configuration Management (SCM) strategy for the MoveVerse project.

The SCM process establishes:

- Git workflow standards
- Team collaboration procedures
- Branch management strategies
- Pull request workflows
- Code review processes
- Version control conventions

---

# 🛠️ Version Control Platform

| Tool | Purpose |
|---|---|
| Git | Distributed version control |
| GitHub | Repository hosting and collaboration |
| Docker | Local environment consistency |

---

# 🌿 Repository Branching Strategy

MoveVerse follows a simplified Git Flow workflow.

## Main Branches

| Branch | Purpose |
|---|---|
| `main` | Stable production-ready code |
| `dev` | Development integration branch |

### `main` Branch

The `main` branch contains:

- Stable releases
- Fully reviewed code
- Production-ready implementations

Direct commits to `main` are prohibited.

---

### `dev` Branch

The `dev` branch is used for:

- Team development
- Feature integration
- Local testing
- Pre-production validation

All feature branches must be merged into `dev` before deployment.

---

# 🌱 Conventional Branching Strategy

Each feature, fix, or documentation task must use its own branch.

## Branch Naming Format

```bash
<type>/<short-description>
```

---

## Branch Types

| Type | Purpose |
|---|---|
| `feat/` | New feature |
| `fix/` | Bug fixes |
| `docs/` | Documentation updates |
| `refactor/` | Code restructuring |
| `test/` | Testing-related work |
| `style/` | UI or formatting changes |
| `chore/` | Maintenance tasks |
| `hotfix/` | Urgent production fixes |

---

## Branch Naming Examples

### Frontend

```bash
feat/login-page
feat/dashboard-ui
fix/navbar-mobile-layout
refactor/auth-context
```

### Backend

```bash
feat/jwt-authentication
feat/workout-session-api
fix/token-validation
```

### Documentation

```bash
docs/system-architecture
docs/database-design
docs/scm-strategy
```

---

# 🔄 Development Workflow

```text
1. Pull latest changes from dev
2. Create feature branch from dev
3. Implement feature
4. Commit changes
5. Push branch to GitHub
6. Create Pull Request
7. Conduct code review
8. Merge into dev
9. Test integration
10. Merge dev into main
```

---

# 📝 Conventional Commits Strategy

MoveVerse follows Conventional Commits for readable Git history.

## Commit Format

```bash
<type>: <short-description>
```

---

## Commit Types

| Commit | Purpose |
|---|---|
| `feat:` | New feature |
| `fix:` | Bug fix |
| `docs:` | Documentation updates |
| `refactor:` | Code restructuring |
| `style:` | Styling/formatting |
| `test:` | Testing changes |
| `chore:` | Maintenance/configuration |

---

## Commit Examples

### Feature Commits

```bash
feat: implement JWT authentication
feat: add leaderboard API endpoint
```

### Fix Commits

```bash
fix: resolve login validation issue
fix: correct calorie calculation logic
```

### Documentation Commits

```bash
docs: add database design documentation
docs: update system architecture diagram
```

### Maintenance Commits

```bash
chore: configure docker environment
chore: update eslint rules
```

---

# 👥 Pull Request and Code Review Strategy

## Pull Request Rules

Before merging:

- Code must be tested
- Branch naming must follow standards
- Commits must follow conventions
- Pull requests should remain focused on one task

---

## Code Review Process

At least one teammate should review every pull request.

Review focus areas:

- Readability
- Folder structure
- API correctness
- Security
- Error handling
- UI consistency
- Database queries

---

## Merge Strategy

Preferred merge method:

```text
Squash and Merge
```

Benefits:

- Cleaner commit history
- Easier rollback management
- Reduced unnecessary commits

---

# 🐳 Docker Development Strategy

MoveVerse uses Docker for local development consistency.

Benefits:

- Standardized development environments
- Easier onboarding
- Dependency isolation
- Simplified PostgreSQL setup

Docker is primarily used during:

- Backend execution
- Database services
- Local integration testing

---

# 🚀 Future CI/CD Recommendation

## Recommended Platform

- GitHub Actions

Why GitHub Actions:

- Integrated directly with GitHub
- Beginner friendly
- Free for student projects
- Supports Node.js and Docker workflows

---

## Recommended CI Tasks

| Task | Purpose |
|---|---|
| Install dependencies | Validate package installation |
| Run linting | Detect formatting issues |
| Run tests | Validate application logic |
| Build frontend | Ensure production build works |
| Docker validation | Verify containers function correctly |

---

# 🔒 Recommended Repository Protections

Protect the following branches:

- `main`
- `dev`

Recommended GitHub branch rules:

- Prevent direct pushes
- Require pull requests
- Require review approval
- Require successful CI checks

---

# 📦 Semantic Versioning Strategy

MoveVerse should follow semantic versioning.

## Version Format

```text
MAJOR.MINOR.PATCH
```

### Example

```text
v1.2.3
```

| Version Type | Meaning |
|---|---|
| MAJOR | Breaking changes |
| MINOR | New features |
| PATCH | Bug fixes |

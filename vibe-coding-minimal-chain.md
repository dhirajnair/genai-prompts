# Vibe Coding - Minimal Document Chain

> **Input**: Vision → **Output**: 4 spec documents → **Start Coding**

---

## The Chain

```
[YOU] → Vision
            ↓
        Features & Stories
            ↓
        Screens & UI
            ↓
        Tech & Data
            ↓
        Build Plan
            ↓
       [START CODING]
```

---

## Document 0: Vision (YOUR INPUT)

Create `00-vision.md`:

```markdown
# App: [Name]

## What is it?
[One paragraph describing the app]

## Who is it for?
[Target users]

## Core Features
- Feature 1
- Feature 2
- Feature 3

## Constraints
[Platform, budget, timeline, tech preferences]
```

---

## Document 1: Features & Stories

### Prompt:
```
Based on this vision, create a features document.

<vision>
{{00-vision.md}}
</vision>

Output format:

# Features & User Stories

## MVP Features
For each feature:
- **Name**: 
- **Description**: 
- **User Story**: As a [user], I want [action] so that [benefit]
- **Acceptance Criteria**: List of testable criteria

## Future Features
[Features not in MVP]

## User Flows
[Key user journeys as numbered steps]
```

**Save as**: `01-features.md`

---

## Document 2: Screens & UI

### Prompt:
```
Based on these documents, create screen specifications.

<context>
{{00-vision.md}}
{{01-features.md}}
</context>

Output format:

# Screens & UI

## Screen List
| Screen | URL | Purpose |
|--------|-----|---------|

## Screen Details
For each screen:
### [Screen Name]
- **Purpose**: 
- **Components**: List of UI elements
- **Actions**: What users can do
- **States**: Loading, empty, error states

## Design Direction
- **Style**: [Modern/Minimal/Bold/etc.]
- **Colors**: Primary, secondary, accent
- **Typography**: Font suggestions
```

**Save as**: `02-screens.md`

---

## Document 3: Tech & Data

### Prompt:
```
Based on these documents, define the tech stack and data model.

<context>
{{00-vision.md}}
{{01-features.md}}
{{02-screens.md}}
</context>

Output format:

# Tech & Data

## Tech Stack
| Layer | Choice | Why |
|-------|--------|-----|
| Frontend | | |
| Backend | | |
| Database | | |
| Auth | | |
| Hosting | | |

## Data Model
For each entity:
### [Entity Name]
| Field | Type | Notes |
|-------|------|-------|

## Relationships
[How entities connect]

## Key API Endpoints
| Method | Endpoint | Purpose |
|--------|----------|---------|
```

**Save as**: `03-tech-data.md`

---

## Document 4: Build Plan

### Prompt:
```
Based on all documents, create a build plan.

<context>
{{00-vision.md}}
{{01-features.md}}
{{02-screens.md}}
{{03-tech-data.md}}
</context>

Output format:

# Build Plan

## Phase 1: Setup
- [ ] Project init
- [ ] Database setup
- [ ] Auth setup

## Phase 2: Core
- [ ] [Screen/Feature 1]
- [ ] [Screen/Feature 2]
- [ ] [Screen/Feature 3]

## Phase 3: Polish
- [ ] Error handling
- [ ] Responsive design
- [ ] Testing

## MVP Checklist
- [ ] [Must work item 1]
- [ ] [Must work item 2]
- [ ] [Must work item 3]
```

**Save as**: `04-build-plan.md`

---

## Quick Reference

| Step | Input | Output |
|------|-------|--------|
| 0 | Your idea | `00-vision.md` |
| 1 | Vision | `01-features.md` |
| 2 | Vision + Features | `02-screens.md` |
| 3 | All above | `03-tech-data.md` |
| 4 | All above | `04-build-plan.md` |

**Then**: Feed all 5 docs to AI and say "Build this app"


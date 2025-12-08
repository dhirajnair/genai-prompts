# Vibe Coding Document Chain

> **Single Input Required**: Your App Vision  
> **Output**: Complete specification suite for AI-assisted development

---

## How It Works

```
YOU → [Vision] → AI generates Doc 1
                      ↓
         [Vision + Doc1] → AI generates Doc 2
                                ↓
              [Vision + Doc1 + Doc2] → AI generates Doc 3
                                            ↓
                                          ... and so on
```

**Your only input is the initial Vision. Everything else chains automatically.**

---

## Document Chain Sequence

| Step | Document | Context Required | Output File |
|------|----------|------------------|-------------|
| 0 | App Vision | (Your input) | `00-vision.md` |
| 1 | User Personas | Vision | `01-personas.md` |
| 2 | User Stories | Vision + Personas | `02-user-stories.md` |
| 3 | Feature Requirements | Vision + Personas + User Stories | `03-features.md` |
| 4 | User Flows | All above | `04-user-flows.md` |
| 5 | Information Architecture | All above | `05-information-architecture.md` |
| 6 | Screen Specifications | All above | `06-screens.md` |
| 7 | Design System | All above | `07-design-system.md` |
| 8 | Tech Stack | All above | `08-tech-stack.md` |
| 9 | Data Model | All above | `09-data-model.md` |
| 10 | API Specification | All above | `10-api-spec.md` |
| 11 | Implementation Roadmap | All above | `11-roadmap.md` |

---

## Step 0: Vision Template (YOUR INPUT)

Create a file `00-vision.md` with this structure:

```markdown
# App Vision: [App Name]

## One-Liner
[Describe your app in one sentence]

## Problem Statement
[What problem does this solve? Why does it matter?]

## Target Users
[Who will use this? Be specific about the audience]

## Core Value Proposition
[What's the main benefit? Why would someone use this over alternatives?]

## Key Features (High-Level)
- [Feature 1]
- [Feature 2]
- [Feature 3]

## Success Criteria
[How will you know the app is successful?]

## Constraints & Considerations
[Budget, timeline, technical constraints, platform requirements, etc.]
```

---

## Step 1: Generate User Personas

### Prompt:
```
You are a product strategist. Based on the App Vision document below, create detailed user personas.

<context>
{{00-vision.md}}
</context>

Generate a User Personas document with the following structure:

# User Personas

For each persona (create 2-3 personas), include:

## Persona: [Name]
- **Role/Title**: 
- **Demographics**: Age range, location, tech savviness
- **Goals**: What they want to achieve
- **Pain Points**: Current frustrations the app solves
- **Behavior Patterns**: How they currently handle this problem
- **Success Metrics**: How they measure success
- **Quote**: A fictional quote that captures their mindset

## Persona Prioritization
Rank personas by importance and explain why.

## Key Insights
Summarize patterns across personas that should influence design decisions.
```

---

## Step 2: Generate User Stories

### Prompt:
```
You are a product manager. Based on the context documents below, create comprehensive user stories.

<context>
{{00-vision.md}}
{{01-personas.md}}
</context>

Generate a User Stories document with the following structure:

# User Stories

## Story Format
Use: "As a [persona], I want to [action] so that [benefit]"

## Epic 1: [Core Functionality Name]
### Stories:
| ID | Story | Priority | Acceptance Criteria |
|----|-------|----------|---------------------|
| US-001 | As a... | Must Have | - Criteria 1<br>- Criteria 2 |

## Epic 2: [Next Functionality Area]
[Continue pattern...]

## Story Map
Organize stories by user journey phase:
1. Discovery/Onboarding
2. Core Usage
3. Advanced Features
4. Retention/Return

## MVP Scope
List which stories are essential for MVP vs. future releases.
```

---

## Step 3: Generate Feature Requirements

### Prompt:
```
You are a business analyst. Based on the context documents below, create detailed feature requirements.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
</context>

Generate a Feature Requirements document with the following structure:

# Feature Requirements

## Feature Categorization (MoSCoW)

### Must Have (MVP)
| Feature | Description | User Stories | Priority |
|---------|-------------|--------------|----------|

### Should Have (V1.1)
| Feature | Description | User Stories | Priority |
|---------|-------------|--------------|----------|

### Could Have (Future)
| Feature | Description | User Stories | Priority |
|---------|-------------|--------------|----------|

### Won't Have (Out of Scope)
| Feature | Reason for Exclusion |
|---------|---------------------|

## Feature Details

### Feature: [Feature Name]
- **ID**: F-001
- **Related Stories**: US-001, US-002
- **Description**: Detailed explanation
- **Business Rules**: 
  - Rule 1
  - Rule 2
- **Validation Rules**:
  - Input constraints
  - Error handling
- **Dependencies**: Other features this depends on
- **Acceptance Criteria**: Testable criteria

[Repeat for each feature]

## Feature Dependency Map
Show which features depend on others for implementation order.
```

---

## Step 4: Generate User Flows

### Prompt:
```
You are a UX designer. Based on the context documents below, create detailed user flows.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
</context>

Generate a User Flows document with the following structure:

# User Flows

## Flow Notation
- [Start] = Entry point
- [Action] = User action
- [Decision] = Branch point
- [Screen] = UI screen
- [End] = Flow completion

## Primary Flows

### Flow 1: [Flow Name, e.g., "New User Onboarding"]
**Persona**: [Primary persona]
**Goal**: [What user achieves]
**Entry Point**: [Where flow starts]

```
[Start] → [Screen: Landing] → [Action: Click Sign Up] → [Screen: Registration]
    ↓
[Decision: Email Valid?]
    ↓ Yes                    ↓ No
[Screen: Verify Email]    [Error: Show validation]
    ↓
[Action: Enter Code] → [Screen: Profile Setup] → [End: Dashboard]
```

**Happy Path Steps**:
1. User lands on homepage
2. User clicks "Sign Up"
3. [Continue steps...]

**Alternative Paths**:
- If [condition]: [alternative flow]

**Error Handling**:
- [Error scenario]: [Recovery path]

### Flow 2: [Next Flow]
[Continue pattern...]

## Flow Summary Matrix
| Flow | Persona | Screens Involved | Features Used |
|------|---------|------------------|---------------|
```

---

## Step 5: Generate Information Architecture

### Prompt:
```
You are an information architect. Based on the context documents below, create the information architecture.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
</context>

Generate an Information Architecture document with the following structure:

# Information Architecture

## Site Map

```
[App Name]
├── Public (Unauthenticated)
│   ├── Landing Page
│   ├── Features
│   ├── Pricing
│   ├── Login
│   └── Register
├── Authenticated
│   ├── Dashboard
│   │   ├── Overview
│   │   └── Quick Actions
│   ├── [Feature Area 1]
│   │   ├── Sub-section
│   │   └── Sub-section
│   ├── [Feature Area 2]
│   └── Settings
│       ├── Profile
│       ├── Preferences
│       └── Account
└── Admin (if applicable)
    └── [Admin sections]
```

## Navigation Structure

### Primary Navigation
| Label | Destination | Visible To | Icon |
|-------|-------------|------------|------|

### Secondary Navigation
[Footer, utility nav, etc.]

### Contextual Navigation
[Breadcrumbs, in-page nav, etc.]

## Content Types
| Content Type | Description | Attributes | Relationships |
|--------------|-------------|------------|---------------|

## URL Structure
| Page | URL Pattern | Parameters |
|------|-------------|------------|

## Search & Discovery
- Search scope and behavior
- Filtering options
- Sorting options
```

---

## Step 6: Generate Screen Specifications

### Prompt:
```
You are a UI/UX designer. Based on the context documents below, create detailed screen specifications.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
</context>

Generate a Screen Specifications document with the following structure:

# Screen Specifications

## Screen Inventory
| Screen ID | Name | URL | Parent | Access Level |
|-----------|------|-----|--------|--------------|
| SCR-001 | Dashboard | /dashboard | - | Authenticated |

## Screen Details

### SCR-001: [Screen Name]

**Purpose**: [What this screen accomplishes]
**User Stories**: US-001, US-003
**Entry Points**: [How users arrive here]
**Exit Points**: [Where users can go from here]

**Layout Zones**:
```
┌─────────────────────────────────────┐
│           Header/Nav                │
├─────────┬───────────────────────────┤
│ Sidebar │     Main Content          │
│         │  ┌─────────┬─────────┐    │
│         │  │ Card 1  │ Card 2  │    │
│         │  └─────────┴─────────┘    │
│         │  ┌───────────────────┐    │
│         │  │   Data Table      │    │
│         │  └───────────────────┘    │
├─────────┴───────────────────────────┤
│              Footer                 │
└─────────────────────────────────────┘
```

**Components**:
| Component | Type | Data Source | Actions |
|-----------|------|-------------|---------|
| User Card | Card | User API | View Profile |

**States**:
- **Loading**: [Description]
- **Empty**: [Description]  
- **Error**: [Description]
- **Success**: [Description]

**Interactions**:
| Element | Trigger | Action | Result |
|---------|---------|--------|--------|

**Responsive Behavior**:
- Desktop (1200px+): [Layout]
- Tablet (768-1199px): [Layout]
- Mobile (<768px): [Layout]

[Repeat for each screen]
```

---

## Step 7: Generate Design System

### Prompt:
```
You are a design system architect. Based on the context documents below, create a design system specification.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
{{06-screens.md}}
</context>

Generate a Design System document with the following structure:

# Design System

## Brand Personality
[Based on vision and personas, define the visual personality]
- **Tone**: [e.g., Professional yet approachable]
- **Feel**: [e.g., Modern, clean, trustworthy]

## Color Palette

### Primary Colors
| Name | Hex | RGB | Usage |
|------|-----|-----|-------|
| Primary | #XXXXXX | rgb(X,X,X) | Main actions, brand elements |
| Primary Light | #XXXXXX | rgb(X,X,X) | Hover states, backgrounds |
| Primary Dark | #XXXXXX | rgb(X,X,X) | Active states, text |

### Secondary Colors
[Same format]

### Semantic Colors
| Name | Hex | Usage |
|------|-----|-------|
| Success | #XXXXXX | Positive feedback |
| Warning | #XXXXXX | Caution states |
| Error | #XXXXXX | Error states |
| Info | #XXXXXX | Informational |

### Neutral Colors
[Grays, blacks, whites for text and backgrounds]

## Typography

### Font Families
- **Headings**: [Font Name], [fallbacks]
- **Body**: [Font Name], [fallbacks]
- **Mono**: [Font Name], [fallbacks]

### Type Scale
| Level | Size | Weight | Line Height | Usage |
|-------|------|--------|-------------|-------|
| H1 | 48px | 700 | 1.2 | Page titles |
| H2 | 36px | 600 | 1.25 | Section headers |
| H3 | 24px | 600 | 1.3 | Subsections |
| Body | 16px | 400 | 1.5 | Paragraphs |
| Small | 14px | 400 | 1.4 | Captions |

## Spacing System
| Token | Value | Usage |
|-------|-------|-------|
| space-xs | 4px | Tight spacing |
| space-sm | 8px | Component internal |
| space-md | 16px | Default spacing |
| space-lg | 24px | Section spacing |
| space-xl | 32px | Large gaps |
| space-2xl | 48px | Page sections |

## Border Radius
| Token | Value | Usage |
|-------|-------|-------|
| radius-sm | 4px | Inputs, small elements |
| radius-md | 8px | Cards, containers |
| radius-lg | 16px | Modals, large cards |
| radius-full | 9999px | Pills, avatars |

## Shadows
| Token | Value | Usage |
|-------|-------|-------|
| shadow-sm | [CSS value] | Subtle elevation |
| shadow-md | [CSS value] | Cards |
| shadow-lg | [CSS value] | Dropdowns, modals |

## Components

### Buttons
| Variant | Usage | States |
|---------|-------|--------|
| Primary | Main actions | default, hover, active, disabled |
| Secondary | Secondary actions | [states] |
| Ghost | Tertiary actions | [states] |
| Danger | Destructive actions | [states] |

[CSS/Tailwind specifications for each]

### Form Elements
[Inputs, selects, checkboxes, etc.]

### Cards
[Card variants and usage]

### Navigation
[Nav patterns]

### Feedback
[Alerts, toasts, modals]

## Animation & Motion
| Type | Duration | Easing | Usage |
|------|----------|--------|-------|
| Micro | 150ms | ease-out | Hovers, toggles |
| Standard | 300ms | ease-in-out | Panels, reveals |
| Complex | 500ms | cubic-bezier(...) | Page transitions |

## Iconography
- **Icon Set**: [Recommended set, e.g., Lucide, Heroicons]
- **Sizes**: 16px, 20px, 24px
- **Style**: [Outline/Filled/etc.]
```

---

## Step 8: Generate Tech Stack

### Prompt:
```
You are a solutions architect. Based on the context documents below, recommend and specify the technology stack.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
{{06-screens.md}}
{{07-design-system.md}}
</context>

Generate a Tech Stack document with the following structure:

# Tech Stack Specification

## Stack Summary
| Layer | Technology | Version |
|-------|------------|---------|
| Frontend | [e.g., Next.js] | X.X |
| Styling | [e.g., Tailwind CSS] | X.X |
| Backend | [e.g., Node.js/Python] | X.X |
| Database | [e.g., PostgreSQL] | X.X |
| Auth | [e.g., NextAuth/Clerk] | X.X |
| Hosting | [e.g., Vercel] | - |

## Decision Rationale

### Frontend Framework
**Choice**: [Technology]
**Rationale**:
- [Reason 1 based on requirements]
- [Reason 2 based on features]
- [Reason 3 based on constraints]

**Alternatives Considered**:
| Option | Pros | Cons | Why Not |
|--------|------|------|---------|

### [Repeat for each major choice]

## Project Structure
```
project-root/
├── src/
│   ├── app/              # Routes/Pages
│   ├── components/       # UI Components
│   │   ├── ui/          # Design system components
│   │   └── features/    # Feature-specific components
│   ├── lib/             # Utilities
│   ├── hooks/           # Custom hooks
│   ├── services/        # API/external services
│   ├── stores/          # State management
│   └── types/           # TypeScript types
├── public/              # Static assets
├── tests/               # Test files
└── [config files]
```

## Dependencies

### Core Dependencies
| Package | Purpose | Version |
|---------|---------|---------|

### Dev Dependencies
| Package | Purpose | Version |
|---------|---------|---------|

## Development Environment
- **Node Version**: X.X
- **Package Manager**: [npm/yarn/pnpm]
- **IDE**: VS Code with [extensions]
- **Linting**: ESLint + Prettier

## Environment Variables
| Variable | Purpose | Required | Default |
|----------|---------|----------|---------|
| DATABASE_URL | DB connection | Yes | - |
| NEXT_PUBLIC_API_URL | API endpoint | Yes | - |

## Third-Party Services
| Service | Purpose | Tier/Cost |
|---------|---------|-----------|
```

---

## Step 9: Generate Data Model

### Prompt:
```
You are a database architect. Based on the context documents below, design the data model.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
{{06-screens.md}}
{{07-design-system.md}}
{{08-tech-stack.md}}
</context>

Generate a Data Model document with the following structure:

# Data Model

## Entity Overview
```
[Entity Relationship Diagram in text/mermaid format]

erDiagram
    USER ||--o{ POST : creates
    USER ||--o{ COMMENT : writes
    POST ||--o{ COMMENT : has
```

## Entities

### User
| Field | Type | Constraints | Description |
|-------|------|-------------|-------------|
| id | UUID | PK | Unique identifier |
| email | String | Unique, Not Null | User email |
| password_hash | String | Not Null | Hashed password |
| created_at | Timestamp | Not Null | Creation time |
| updated_at | Timestamp | Not Null | Last update |

**Indexes**: 
- `idx_user_email` on (email)

**Relationships**:
- Has many [Entity]

[Repeat for each entity]

## Relationships Summary
| From | To | Type | Through |
|------|-------|------|---------|
| User | Post | 1:N | user_id |

## Schema (SQL)
```sql
CREATE TABLE users (
    id UUID PRIMARY KEY DEFAULT gen_random_uuid(),
    email VARCHAR(255) UNIQUE NOT NULL,
    -- continue...
);
```

## Schema (Prisma/ORM)
```prisma
model User {
  id        String   @id @default(cuid())
  email     String   @unique
  // continue...
}
```

## Seed Data
[Essential data needed for app to function]

## Migration Strategy
[How to handle schema changes]
```

---

## Step 10: Generate API Specification

### Prompt:
```
You are an API architect. Based on the context documents below, design the API specification.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
{{06-screens.md}}
{{07-design-system.md}}
{{08-tech-stack.md}}
{{09-data-model.md}}
</context>

Generate an API Specification document with the following structure:

# API Specification

## Overview
- **Base URL**: `/api/v1`
- **Format**: JSON
- **Authentication**: Bearer Token (JWT)

## Authentication

### POST /auth/register
**Description**: Register new user
**Auth Required**: No

**Request Body**:
```json
{
  "email": "string",
  "password": "string",
  "name": "string"
}
```

**Response 201**:
```json
{
  "user": {
    "id": "string",
    "email": "string",
    "name": "string"
  },
  "token": "string"
}
```

**Errors**:
| Code | Description |
|------|-------------|
| 400 | Validation error |
| 409 | Email already exists |

### POST /auth/login
[Continue pattern...]

## Resources

### Users

#### GET /users/me
**Description**: Get current user profile
**Auth Required**: Yes

[Continue for all endpoints...]

## Error Handling

### Error Response Format
```json
{
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable message",
    "details": {}
  }
}
```

### Error Codes
| Code | HTTP Status | Description |
|------|-------------|-------------|
| UNAUTHORIZED | 401 | Invalid/missing token |
| FORBIDDEN | 403 | Insufficient permissions |
| NOT_FOUND | 404 | Resource not found |
| VALIDATION_ERROR | 400 | Invalid input |

## Rate Limiting
- **Limit**: X requests per minute
- **Headers**: `X-RateLimit-Remaining`, `X-RateLimit-Reset`

## Pagination
```json
{
  "data": [],
  "pagination": {
    "page": 1,
    "limit": 20,
    "total": 100,
    "totalPages": 5
  }
}
```
```

---

## Step 11: Generate Implementation Roadmap

### Prompt:
```
You are a technical project manager. Based on the context documents below, create an implementation roadmap.

<context>
{{00-vision.md}}
{{01-personas.md}}
{{02-user-stories.md}}
{{03-features.md}}
{{04-user-flows.md}}
{{05-information-architecture.md}}
{{06-screens.md}}
{{07-design-system.md}}
{{08-tech-stack.md}}
{{09-data-model.md}}
{{10-api-spec.md}}
</context>

Generate an Implementation Roadmap document with the following structure:

# Implementation Roadmap

## Phase Overview
```
Phase 0: Setup (Day 1-2)
    ↓
Phase 1: Foundation (Day 3-7)
    ↓
Phase 2: Core Features (Day 8-14)
    ↓
Phase 3: Polish & Testing (Day 15-18)
    ↓
Phase 4: Launch Prep (Day 19-21)
```

## Phase 0: Project Setup
**Duration**: 1-2 days

### Tasks:
- [ ] Initialize repository
- [ ] Setup project structure per tech stack
- [ ] Configure linting, formatting
- [ ] Setup environment variables
- [ ] Configure database connection
- [ ] Deploy empty shell to staging

### Deliverables:
- Working local dev environment
- CI/CD pipeline basics
- Staging deployment

## Phase 1: Foundation
**Duration**: X days

### Tasks:
- [ ] Implement design system components
- [ ] Setup authentication flow
- [ ] Create base layouts
- [ ] Setup database schema
- [ ] Implement core API routes

### Deliverables:
- Functional auth (register/login/logout)
- Base UI component library
- Database with seed data

## Phase 2: Core Features
**Duration**: X days

### Sprint 2.1: [Feature Group 1]
| Task | Screen | API | Priority |
|------|--------|-----|----------|
| [Task] | SCR-XXX | GET /xxx | Must |

### Sprint 2.2: [Feature Group 2]
[Continue pattern...]

## Phase 3: Polish & Testing
**Duration**: X days

### Tasks:
- [ ] Responsive design fixes
- [ ] Error handling improvements
- [ ] Loading states
- [ ] Empty states
- [ ] End-to-end testing
- [ ] Performance optimization

## Phase 4: Launch Preparation
**Duration**: X days

### Tasks:
- [ ] Production environment setup
- [ ] Domain configuration
- [ ] Analytics integration
- [ ] Error monitoring setup
- [ ] Final QA pass
- [ ] Documentation

## Risk Mitigation
| Risk | Impact | Mitigation |
|------|--------|------------|

## Success Criteria for MVP
- [ ] [Criteria 1]
- [ ] [Criteria 2]
- [ ] [Criteria 3]

## Post-MVP Backlog
[Features for future phases]
```

---

## Automation Script

Save this as a reference for chaining prompts in your AI tool:

```javascript
// Document Chain Automation Reference
const CHAIN = [
  { id: "00", name: "vision", context: [] },
  { id: "01", name: "personas", context: ["00"] },
  { id: "02", name: "user-stories", context: ["00", "01"] },
  { id: "03", name: "features", context: ["00", "01", "02"] },
  { id: "04", name: "user-flows", context: ["00", "01", "02", "03"] },
  { id: "05", name: "information-architecture", context: ["00", "01", "02", "03", "04"] },
  { id: "06", name: "screens", context: ["00", "01", "02", "03", "04", "05"] },
  { id: "07", name: "design-system", context: ["00", "01", "02", "03", "04", "05", "06"] },
  { id: "08", name: "tech-stack", context: ["00", "01", "02", "03", "04", "05", "06", "07"] },
  { id: "09", name: "data-model", context: ["00", "01", "02", "03", "04", "05", "06", "07", "08"] },
  { id: "10", name: "api-spec", context: ["00", "01", "02", "03", "04", "05", "06", "07", "08", "09"] },
  { id: "11", name: "roadmap", context: ["00", "01", "02", "03", "04", "05", "06", "07", "08", "09", "10"] }
];
```

---

## Quick Start

1. **Create your vision document** (`00-vision.md`) using the template in Step 0
2. **Start the chain**: Use the Step 1 prompt with your vision
3. **Save each output** with the corresponding filename
4. **Continue**: Each subsequent step includes all previous documents as context
5. **Begin coding**: Once you have all specs, feed them to your AI coding assistant

---

## Tips for Best Results

1. **Be specific in your vision** - The more detail you provide, the better the entire chain
2. **Review and refine** - After each step, review and tweak before moving to the next
3. **Context window limits** - For later steps, you may need to summarize earlier docs
4. **Iterate** - It's okay to regenerate a document if the output isn't quite right
5. **Living documents** - Update specs as you learn during implementation


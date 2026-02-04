# Backend Directory Structure Guide

## Root Level Files

### `implementation_steps.md`
**Purpose**: Main tracking document for development progress.
**Usage**: 
- Break down each phase into actionable steps
- Update status after each step completion

### `agent_choices.md`
**Purpose**: Technical decision log for consistency.
**Usage**:
- Document architecture decisions (e.g., JWT vs Session)
- Record library choices (e.g., why BCrypt for passwords)
- Update after significant technical decisions

### `api_alignment.md`
**Purpose**: Contract tracker between frontend and backend.
**Usage**:
- Maps frontend API requirements to backend implementation
- Track completion status of endpoints
- Reference when starting new endpoints

### `workflow.md`
**Purpose**: Step-by-step process guide for development.
**Usage**: 
- Follow when starting new phases
- Reference for prompt templates
- Guide for updating tracking documents

### `files.md` (this file)
**Purpose**: Documentation of project structure.

### `SETUP.md`
**Purpose**: Initial setup checklist and instructions.

---

## Directories

### `specs/`
**Purpose**: Pre-implementation planning documents.
**Created**: Before coding starts for each phase.
**Files**:
- `01_project_overview.md`: Overall backend architecture, tech stack decisions
- `02_database_schema.md`: Entity models, relationships, indexes, constraints
- `03_api_design.md`: All REST endpoints grouped by domain (auth, products, cart)
- `04_authentication.md`: JWT implementation, Spring Security configuration
- `05_business_logic.md`: Service layer rules, validation logic, workflows
- `06_performance.md`: Caching strategy, query optimization, pagination
- `07_deployment.md`: Docker setup, environment variables, CI/CD

### `details/`
**Purpose**: Post-implementation learning documentation.
**Created**: After each step completion.
**Naming**: `step_X_details.md` (matches step number from implementation_steps.md)
**Content**:
- What was implemented
- Code snippets and explanations
- Challenges faced and solutions
- Testing approach
- Performance considerations

**Usage**: Personal learning reference, not meant to be used by agents during development but can be used if required.

### `.github/copilot/`
**Purpose**: Custom GitHub Copilot commands.
**Files**: Prompt template files (e.g., `implement.md`)
**Usage**: Access via `/` commands in GitHub Copilot Chat (e.g., `/implement`)

### `src/`
**Purpose**: Spring Boot application code.
**Structure** (standard):
```
src/
├── main/
│   ├── java/com/newguru/store/
│   │   ├── controller/
│   │   ├── service/
│   │   ├── repository/
│   │   ├── model/
│   │   ├── dto/
│   │   ├── config/
│   │   ├── security/
│   │   └── exception/
│   └── resources/
│       ├── application.yml
│       └── db/migration/
└── test/
```

---

## Workflow Integration

### Starting a New Phase
1. Read frontend's `API team guide.md` section
2. Update `specs/` with requirements
3. Create steps in `implementation_steps.md`
4. Reference: "Based on specs/ and implementation_steps.md, start Step 1"

### During Implementation
1. Execute step from `implementation_steps.md`
2. Update status: `- [x] Step 3: Implement login API - **Completed**`
3. Create `details/step_3_details.md`
4. Update `api_alignment.md`: Mark endpoint ✅
5. Update `agent_choices.md` if technical decision made


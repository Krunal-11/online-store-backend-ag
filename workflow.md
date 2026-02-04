# Backend Execution Workflow

This workflow applies after planning is complete. It covers how to execute predefined steps and update tracking files.

## Prerequisites
- `specs/` contain the requirements for the current phase.
- `implementation_steps.md` lists all steps to execute.
- `api_alignment.md` is initialized with endpoints for the phase.

## Execution Steps
For each step listed in `implementation_steps.md`:

1. Implement
   - Read the step description in `implementation_steps.md`.
   - Follow the relevant `specs/` (database, API design, authentication, etc.).
   - Write code and tests for the step.

2. Update Tracking
   - Mark the step as completed in `implementation_steps.md` and reference its details file.
   - Create `details/step_<N>_details.md` and record what was built, tests executed, and any notes. The `details/step_<N>_details.md` is created mainly as an educational document which should teach the developer about what was implemented in that step. and include code snippets and explanations as needed. it should be detailed enough to help someone understand the implementation without referring back to the code but also make sure that it only has important topics that should be learnt. do not repeat points unless necessary.
   - If an endpoint was delivered, update `api_alignment.md` to mark it as completed.
   - If a technical decision was made, add it to `agent_choices.md`.

3. Proceed
   - Move to the next step and repeat until the phase is complete.

## Completion Checklist (per phase)
- All steps in `implementation_steps.md` are marked completed.
- All relevant endpoints are marked completed in `api_alignment.md`.
- Corresponding files under `details/` exist for completed steps.
- Tests for the phase pass and code is committed.

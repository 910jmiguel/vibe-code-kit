# Checklist Phase

You're helping me break down a project into a concrete, ordered checklist of tasks. I need something I can work through step by step.

**Answer these questions first:**

1. Do you have a PRD or requirements doc? If so, paste it here (or the key sections).
2. If no PRD — what are you building? Describe the scope and features.
3. Any tasks already completed? Tell me what's done so I can mark them off.
4. **Optional:** If you don't have a PRD yet, I can run the **PRD phase** first (which can also generate a plan if needed). Want me to do that? (If you already know the scope, skip this.)

**Wait for my answers before continuing.**

> **Note:** If I say yes to running the PRD phase first, use the PRD prompt (`prompts/02-prd.md`) to generate a PRD, save it to `docs/prd.md`, and then continue with the checklist using that PRD as the source.

---

Once I've answered, generate a checklist following these rules:

## Checklist Rules

- **Each task is a single, concrete action.** Not "build the frontend" — more like "create the login form component with email and password fields."
- **Tasks are ordered by dependency.** Things that must happen first come first.
- **Group tasks by phase or feature area** using headers.
- **Use checkbox format** so I can track progress:
  - `- [ ]` for incomplete tasks
  - `- [x]` for completed tasks
- **Include brief context** where helpful — a few words on approach or gotchas, not a paragraph.
- **Flag decision points** — places where I'll need to make a choice that affects later tasks.

## Checklist Structure

### Phase 1: [Name]
_Goal: [What's true when this phase is done]_

- [ ] Task 1 — brief context if needed
- [ ] Task 2
- [ ] Task 3
- [ ] **Decision point:** [What needs to be decided before continuing]

### Phase 2: [Name]
_Goal: [What's true when this phase is done]_

- [ ] Task 4
- [ ] Task 5
- [ ] Task 6

_(continue for all phases)_

### Final Checks
- [ ] All features from PRD are implemented
- [ ] Manual smoke test of core user flows
- [ ] Error states and edge cases handled
- [ ] Code cleaned up (no debug logs, commented-out code, TODOs)
- [ ] Ready for review / deploy

---

**After generating the checklist:**
- Tell me the total task count and which phase to start with
- **Always generate a `docs/checklist.md` file** containing the full checklist output. Create the `docs/` directory if it doesn't exist.
- Suggest running `/implement` or using the implement prompt to start building
- Ask if any tasks need to be added, removed, or reordered

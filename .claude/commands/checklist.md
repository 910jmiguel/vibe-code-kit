# Checklist Phase

You're helping the user break down their project into an ordered, actionable checklist.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it for project context
- Check for `docs/prd.md` — if it exists, read it and use it as the source for tasks
- Check for `docs/plan.md` — use for phase structure if PRD doesn't exist
- Ask: "Ready to generate a checklist from your PRD? Anything to add or change first? $ARGUMENTS"

**If CLAUDE.md does not exist:**
- Ask:
  1. Do you have a PRD or requirements doc? Paste it or the key sections.
  2. If no PRD — describe what you're building and the key features.
  3. Any tasks already completed?
- Wait for answers.

**If `$ARGUMENTS` is provided**, use it to filter or focus the checklist (e.g., "Phase 1 only" or "just the API tasks").

## Step 2: Generate the Checklist

Follow these rules:
- **Each task is a single, concrete action.** "Create the login form with email and password fields" — not "build auth."
- **Order by dependency.** Prerequisites first.
- **Group by phase or feature area.**
- **Checkbox format:** `- [ ]` incomplete, `- [x]` completed.
- **Brief context** where helpful (approach, gotchas) — not paragraphs.
- **Flag decision points** where a choice affects later tasks.

### Structure

```markdown
## Phase 1: [Name]
_Goal: [What's true when this phase is done]_

- [ ] Task 1 — brief context if needed
- [ ] Task 2
- [ ] **Decision point:** [What needs to be decided]

## Phase 2: [Name]
_Goal: [What's true when this phase is done]_

- [ ] Task 3
- [ ] Task 4

## Final Checks
- [ ] All features from PRD implemented
- [ ] Manual smoke test of core flows
- [ ] Error states and edge cases handled
- [ ] Code cleaned up
- [ ] Ready for review / deploy
```

## Step 3: Review & Save

- Report total task count and recommended starting phase
- Offer to save to `docs/checklist.md`
- Suggest next step: "Run `/implement` to start building, or `/implement Phase 1` to start with the first phase"
- Ask if tasks need to be added, removed, or reordered

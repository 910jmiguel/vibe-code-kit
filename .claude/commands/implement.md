# Implement Phase

You're helping the user build. Time to write code.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it for project context, conventions, and key commands
- Check for `docs/checklist.md` — if it exists, read it to know what tasks are pending
- Check for `docs/prd.md` — reference for requirements and acceptance criteria
- Scan the project structure to understand existing code

**If CLAUDE.md does not exist:**
- Ask:
  1. What are you implementing?
  2. What's the tech stack?
  3. Do you have a checklist or requirements? Paste the relevant section.
- Wait for answers.

**If `$ARGUMENTS` is provided**, interpret it as the implementation target:
- A task description: "add the login form"
- A phase reference: "Phase 2"
- A mode flag: "plan-only", "full-build"
- Default mode is step-by-step if not specified.

## Step 2: Determine Mode

**Step-by-step (default):**
- Work through one task at a time
- Show the result after each task
- Wait for confirmation before continuing

**Full build:**
- Complete all tasks in the current phase or scope
- Check in at the end with a summary

**Plan only:**
- Show what you would do for each task
- Don't write any code
- Let the user approve or modify the plan

## Step 3: Implement

### Before Writing Code
- Read existing code in the area you're modifying
- Follow conventions from CLAUDE.md and existing patterns
- If something is ambiguous, ask — don't guess on architecture

### While Writing Code
- **Complete, working code.** No pseudocode, no placeholders, no "// TODO: implement this."
- **Match project style.** Indentation, quotes, naming — match what's there.
- **Explain briefly** (1-2 sentences) before each piece of code.
- **Flag concerns early.** If something might break or conflicts with the plan, say so.

### After Each Task
- Show what was created/changed (file names, key snippets)
- Note any deviations from the plan
- State what's next
- In step-by-step mode: wait for go-ahead

### After the Session
- Summarize what was built
- List incomplete tasks (if any) and why
- Suggest next step (usually `/test` to validate)
- Offer to update `docs/checklist.md` with completed items

## Error Handling
If something breaks:
1. Stop — don't build on broken code
2. Diagnose — read the error, understand the cause
3. Fix or escalate — straightforward fix → do it; design issue → flag it
4. Continue from where you left off

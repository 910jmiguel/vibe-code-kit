# Implement Phase

You're helping the user build. Time to write code.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it for project context, conventions, and key commands
- Check for `docs/checklist.md` — if it exists, read it to know what tasks are pending
- Check for `docs/prd.md` — reference for requirements and acceptance criteria
- If neither `docs/checklist.md` nor `docs/prd.md` exist, ask: "No checklist or PRD found. Want me to run the Checklist phase first to generate `docs/checklist.md`? (Optional — I can implement from a description if you already know what to build.)"
- Scan the project structure to understand existing code

**If CLAUDE.md does not exist:**
- Ask:
  1. What are you implementing?
  2. What's the tech stack?
  3. Do you have a checklist or requirements? Paste the relevant section.
  4. Optional: Want me to run the Checklist phase first? (This can also generate a PRD and plan if needed.)
- Wait for answers.

**If the user wants the Checklist phase first**, run the full Checklist workflow (which may also run PRD and Plan if needed), save `docs/checklist.md`, then continue with implementation using that checklist as the guide.

**If `$ARGUMENTS` is provided**, interpret it as the implementation target:
- A task description: "add the login form"
- A phase reference: "Phase 2"
- A mode flag: "plan-only", "full-build"
- Default mode is step-by-step if not specified.

## Step 2: Determine Mode

Ask the user which mode they want to work in:

**Step-by-step (default):**
- Work through one task at a time
- Show the result after each task
- Wait for confirmation before continuing

**Cherry-pick:**
- Let the user choose specific items from their PRD or checklist
- Great for tackling things in their own order or doing a few items per session

**Full build:**
- Complete all tasks in the current phase or scope
- Check in at the end with a summary

**Plan only:**
- Show what you would do for each task
- Don't write any code
- Let the user approve or modify the plan

## Step 2.5: Plan & Discuss Before Building (Recommended)

**When the user chooses cherry-pick, step-by-step, or is working phase by phase**, ask:

> "Before we start coding, would you like to **plan and discuss** first? I'll walk through the selected tasks like a brief interview — asking clarifying questions about requirements, edge cases, dependencies, and design decisions. This produces a sharper plan and higher-quality code. (Recommended, but you can skip if you're ready to build.)"

**If the user says yes (Plan & Discuss mode):**

For each selected task or phase, conduct a focused interview:

1. **Clarify requirements** — Ask targeted questions about what the task should do, what inputs/outputs are expected, and what "done" looks like. Don't ask obvious questions — focus on ambiguities and decisions that affect implementation.
2. **Surface edge cases** — What should happen with empty data? Errors? Concurrent access? Permissions? Ask about the cases the user might not have considered.
3. **Identify dependencies** — Does this task depend on other tasks? Does it touch shared state, APIs, or components that other tasks also modify? Flag potential conflicts.
4. **Confirm design decisions** — If there are multiple valid approaches (e.g., client-side vs. server-side, new component vs. extend existing), present the options briefly and let the user decide.
5. **Produce a mini-plan** — After the discussion, summarize:
   - What will be built (scope)
   - Key decisions made
   - Edge cases to handle
   - Implementation approach
   - Any risks or open questions
6. **Get approval** — Ask the user to confirm the plan before writing code. They can adjust, add, or remove items.

**If the user says no (skip):**
- Proceed directly to implementation. You can still ask questions if something is genuinely ambiguous, but don't run the full interview.

> **Why this matters:** A 2-minute discussion before coding prevents 20 minutes of rework. This is especially valuable for complex tasks, tasks with unclear requirements, or when working on unfamiliar parts of the codebase.

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
- **Provide testing instructions:** Give the user clear, step-by-step instructions to manually verify the task works. Include what to run, what to click, what to look for, and what the expected outcome should be. Example: "Run `npm run dev`, navigate to `/login`, enter a valid email/password, and verify you're redirected to the dashboard."
- State what's next
- **Update docs immediately:** If `docs/checklist.md` exists, mark the completed task/item as done (e.g., `- [x]`). If `docs/prd.md` exists and has trackable items or acceptance criteria related to what was just completed, update or annotate it to reflect progress. Don't wait until the end of the session — update after each task so progress is never lost.
- In step-by-step mode: wait for go-ahead

### After the Session
- Summarize what was built
- List incomplete tasks (if any) and why
- Suggest next step (usually `/test` to validate)
- **Final doc check:** Verify that `docs/checklist.md` and `docs/prd.md` (if they exist) accurately reflect all completed work from this session. Fix any items that were missed.

## Error Handling
If something breaks:
1. Stop — don't build on broken code
2. Diagnose — read the error, understand the cause
3. Fix or escalate — straightforward fix → do it; design issue → flag it
4. Continue from where you left off

# Implement Phase

You're helping me build. Time to write code.

**Answer these questions first:**

1. What are you implementing? (specific feature, task from checklist, or general area)
2. Do you have a checklist or PRD? If so, paste the relevant section.
3. How do you want to work?
   - **Step-by-step** (default): One task at a time, check in after each
   - **Cherry-pick**: Choose specific items from your PRD or checklist to work on now (great for tackling things in your own order or doing a few items per session)
   - **Full build**: Do everything in the current phase, check in at the end
   - **Plan only**: Show me what you'd do but don't write code yet
4. **Optional:** If you don't have a checklist yet, I can run the **Checklist phase** first (which can also generate a PRD and plan if needed). Want me to do that? (If you already know what to build, skip this.)

**Wait for my answers before continuing.**

> **Note:** If I say yes to running the Checklist phase first, use the checklist prompt (`prompts/03-checklist.md`) to generate a checklist, save it to `docs/checklist.md`, and then continue with implementation using that checklist as the guide.

---

Once I've answered, here's how to work:

## Cherry-Pick Mode

If the user chose **cherry-pick**:

1. **Read their PRD** (`docs/prd.md`) **and/or checklist** (`docs/checklist.md`). If neither exists, ask them to paste or describe what's available.
2. **Present a numbered list** of all implementable items (features, tasks, endpoints, components, etc.) pulled from those docs. Group them by section/phase if the source doc has structure.
3. **Ask:** "Which items do you want to tackle this session? (Pick by number, or describe what you want.)"
4. **Wait for their selection.** Don't start coding until they confirm.
5. **Before coding, offer the Plan & Discuss step** (see below).
6. Once selected (and optionally discussed), implement each picked item using the same rules as step-by-step mode (one at a time, check in after each).
7. After completing all picked items, show:
   - What was completed
   - What remains on the full list
   - Suggest logical next picks for the following session
8. **Update the checklist** (`docs/checklist.md`) — mark completed items as done so progress carries across sessions.

> **Tip:** Cherry-pick mode is ideal when you want to work in short sessions, prioritize the most important items first, or skip around the plan based on what's ready.

---

## Plan & Discuss Before Building (Recommended)

**When the user chooses cherry-pick, step-by-step, or is working phase by phase**, ask before writing any code:

> "Before we start coding, would you like to **plan and discuss** first? I'll walk through the selected tasks like a brief interview — asking clarifying questions about requirements, edge cases, dependencies, and design decisions. This produces a sharper plan and higher-quality code. **(Recommended)**, but you can skip if you're ready to build."

### If the user says yes (Plan & Discuss mode):

For each selected task, subphase, or phase, conduct a focused interview:

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

### If the user says no (skip):

Proceed directly to implementation. You can still ask questions if something is genuinely ambiguous, but don't run the full interview.

> **Why this matters:** A 2-minute discussion before coding prevents 20 minutes of rework. This is especially valuable for complex tasks, tasks with unclear requirements, or when working on unfamiliar parts of the codebase.

---

## Implementation Rules

### Before Writing Code
- Read any existing code in the area you're modifying. Don't duplicate or contradict what's there.
- If CLAUDE.md or project docs exist, follow their conventions.
- If something is ambiguous, ask. Don't guess on architecture decisions.

### While Writing Code
- **Write complete, working code.** No pseudocode, no "// implement this", no placeholders.
- **Match the project's style.** If the codebase uses tabs, use tabs. If it uses single quotes, use single quotes.
- **One task at a time** (in step-by-step or cherry-pick mode). Complete it, show me the result, then move on.
- **Explain what you're doing** in 1-2 sentences before each piece of code. Not a lecture — just enough context so I can follow along.
- **Flag concerns early.** If you notice something that might break, conflicts with the plan, or needs a decision — say so before writing more code.

### After Each Task
- Show what was created or changed (file names and key snippets)
- Note any deviations from the plan and why
- State what's next
- If step-by-step or cherry-pick: wait for my go-ahead before continuing

### After the Phase/Session
- Summarize what was built
- List any tasks that weren't completed and why
- Suggest what to tackle next
- Recommend running the test prompt/command to validate the work

---

## Strict Error Handling & Verification

**Zero tolerance for broken code.** Every piece of code you write must be verified before moving on. Do not ignore, skip, or defer any error.

### Compilation & Build Verification
- After writing or modifying code, **run the build/compile step** (e.g., `npm run build`, `tsc`, `cargo build`, etc.) and confirm it passes with zero errors and zero warnings.
- If the project uses TypeScript or a typed language, confirm there are **no type errors** anywhere in the affected files.
- If the project has a linter configured, **run it** and fix any issues before moving on.
- **Do not move to the next task until the current code compiles cleanly.**

### Frontend / UI Verification
- After any UI change, **check the actual rendered frontend** — do not assume it looks correct just because the code compiled.
- Verify layout, styling, responsiveness, and interactive behavior match the intended design.
- Check for visual regressions: did your change break something else on the page?
- Test edge cases in the UI: empty states, long text, missing data, loading states, error states.
- If the project has a dev server, **run it and visually confirm** the output before marking a task complete.

### Backend & API Verification
- After writing or modifying an API endpoint, **test it** (e.g., with a curl command, test script, or the project's test suite).
- Verify correct responses for: valid input, missing/invalid input, unauthorized access, and edge cases.
- Check that error responses return proper status codes and messages — don't just verify the happy path.
- Confirm database operations (if any) work correctly: data is saved, retrieved, updated, and deleted as expected.
- Verify third-party API integrations handle: success, failure, timeouts, and rate limits.

### Edge Case & Integration Checks
- Think through edge cases **before** writing code. What happens with null/undefined values? Empty arrays? Extremely large inputs? Concurrent requests?
- After implementation, **verify those edge cases** actually work.
- Check that your new code integrates correctly with existing code — no broken imports, no conflicting state, no missing dependencies.
- If your change touches shared state or global config, verify nothing else broke.

### The Iron Rule: Stop, Diagnose, Fix, Continue

If **anything** goes wrong — a compilation error, a failing test, a UI glitch, a broken API response, an unhandled edge case — follow this process without exception:

1. **Stop immediately.** Do not write more code on top of broken code. Do not skip the error. Do not say "we'll fix that later."
2. **Diagnose thoroughly.** Read the full error. Trace it to the root cause. Check related files. Understand *why* it's failing, not just *what* is failing.
3. **Fix it or ask.** If the fix is clear, implement it and re-verify. If it's a design-level issue or you're unsure, flag it to me with your diagnosis and options — don't guess.
4. **Re-verify from scratch.** After fixing, re-run the build, re-check the UI, re-test the endpoint. Confirm the fix didn't introduce new issues.
5. **Only then continue** to the next task.

**Never present code as "done" if any of these checks have not passed.**

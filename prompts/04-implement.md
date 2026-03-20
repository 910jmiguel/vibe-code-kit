# Implement Phase

You're helping me build. Time to write code.

**Answer these questions first:**

1. What are you implementing? (specific feature, task from checklist, or general area)
2. Do you have a checklist or PRD? If so, paste the relevant section.
3. How do you want to work?
   - **Step-by-step** (default): One task at a time, check in after each
   - **Full build**: Do everything in the current phase, check in at the end
   - **Plan only**: Show me what you'd do but don't write code yet

**Wait for my answers before continuing.**

---

Once I've answered, here's how to work:

## Implementation Rules

### Before Writing Code
- Read any existing code in the area you're modifying. Don't duplicate or contradict what's there.
- If CLAUDE.md or project docs exist, follow their conventions.
- If something is ambiguous, ask. Don't guess on architecture decisions.

### While Writing Code
- **Write complete, working code.** No pseudocode, no "// implement this", no placeholders.
- **Match the project's style.** If the codebase uses tabs, use tabs. If it uses single quotes, use single quotes.
- **One task at a time** (in step-by-step mode). Complete it, show me the result, then move on.
- **Explain what you're doing** in 1-2 sentences before each piece of code. Not a lecture — just enough context so I can follow along.
- **Flag concerns early.** If you notice something that might break, conflicts with the plan, or needs a decision — say so before writing more code.

### After Each Task
- Show what was created or changed (file names and key snippets)
- Note any deviations from the plan and why
- State what's next
- If step-by-step: wait for my go-ahead before continuing

### After the Phase/Session
- Summarize what was built
- List any tasks that weren't completed and why
- Suggest what to tackle next
- Recommend running the test prompt/command to validate the work

## Error Handling
If something goes wrong during implementation:
1. **Stop.** Don't keep building on top of broken code.
2. **Diagnose.** Read the error. Check the relevant code. Understand what's failing and why.
3. **Fix or ask.** If the fix is straightforward, do it. If it's a design issue, flag it.
4. **Then continue** from where you left off.

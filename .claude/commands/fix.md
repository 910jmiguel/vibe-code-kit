# Fix Phase

Something's broken. Let's diagnose and fix it.

## Step 1: Understand the Issue

**If `$ARGUMENTS` is provided**, use it as the issue description. Analyze the relevant code immediately.

**If no arguments**, ask: "What's broken? Describe what you expected vs. what's happening, plus any error messages."

Check if `CLAUDE.md` exists — if so, read it for project context and conventions.

## Step 2: Diagnose

1. **Restate the issue** in your own words to confirm understanding
2. **Identify the type:** runtime error, logic bug, UI issue, build/config problem, type error, etc.
3. **Trace to root cause:**
   - Read the relevant code — follow the execution path
   - If there's an error message, explain what it means in plain language
   - Don't guess — understand the actual cause
4. **State your diagnosis clearly:** "The issue is X, caused by Y, in Z."
5. Ask 1-2 clarifying questions ONLY if the issue description is genuinely ambiguous

## Step 3: Fix

- Make the **minimal change** that fixes the issue correctly
- Don't refactor, add features, or "improve" surrounding code — just fix the bug
- Show the exact change (before → after)
- Explain why this fix works

## Step 4: Verify

- Describe how to verify the fix
- **Provide testing instructions:** Give the user clear, step-by-step instructions to manually verify the fix works. Include what to run, what to navigate to, what to look for, and what the expected outcome should be. Also describe how to confirm the original bug no longer occurs.
- Run tests if the project has them
- Check for related issues — same bug pattern elsewhere?
- Note if this fix could affect anything else

## Step 5: Summarize

**Problem:** One sentence
**Cause:** One sentence
**Fix:** One sentence
**Files changed:** List them
**Side effects:** Any, or "none expected"

---

## Complex Fixes

If the root cause requires significant changes:
1. Explain the scope
2. Propose options (quick fix vs. proper fix) with tradeoffs
3. Let the user choose before implementing
4. Consider whether this should be a separate task in the checklist

## Update Docs

- **Update docs immediately:** If `docs/checklist.md` exists, mark the fixed item or add a note about the fix. If `docs/prd.md` exists and has acceptance criteria related to the fix, update it to reflect the current status.
- **Final doc check:** Verify that `docs/checklist.md` and `docs/prd.md` (if they exist) accurately reflect the fix. Fix any items that were missed.

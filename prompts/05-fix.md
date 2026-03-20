# Fix Phase

Something's broken. Let's fix it.

**What's going on?** Describe the issue — what you expected to happen, what's actually happening, and any error messages you're seeing.

**Wait for my answer before continuing.**

---

Once I've described the issue, follow this process:

## Fix Process

### Step 1: Understand the Problem
- Restate the issue in your own words to confirm you understand it
- Identify what type of issue this is (runtime error, logic bug, UI issue, build/config problem, etc.)
- Ask 1-2 clarifying questions ONLY if the issue description is genuinely ambiguous

### Step 2: Diagnose
- Trace the issue to its root cause. Don't just treat symptoms.
- Read the relevant code. Follow the execution path.
- If there's an error message, explain what it means in plain language.
- State your diagnosis clearly: "The issue is X, caused by Y, in Z."

### Step 3: Fix
- Make the minimal change that fixes the issue correctly
- Don't refactor surrounding code, add features, or "improve" things while you're here — just fix the bug
- Show the exact change (before → after)
- Explain why this fix works

### Step 4: Verify
- Describe how to verify the fix works
- Check for related issues — if this bug exists, are there similar bugs nearby?
- Note if this fix could affect anything else

### Step 5: Summarize
Keep it short:
- **Problem:** One sentence
- **Cause:** One sentence
- **Fix:** One sentence
- **Files changed:** List them
- **Side effects:** Any, or "none expected"

---

## If the Problem is Unclear
If I can't describe the issue well, help me narrow it down:
- When did it start happening?
- What changed recently?
- Does it happen every time or intermittently?
- What's the exact error message or unexpected behavior?

## If the Fix is Complex
If the root cause requires significant changes:
1. Explain the scope of the fix
2. Propose options (quick fix vs. proper fix) with tradeoffs
3. Let me choose before implementing
4. Consider whether this should be a separate task in the checklist

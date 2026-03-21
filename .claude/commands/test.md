# Test Phase

Let's validate that what was built actually works.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it for project context and test commands
- Check for `docs/checklist.md` — use completed tasks as the basis for what to test
- Check for `docs/prd.md` — use acceptance criteria as test criteria
- Scan the project for existing tests

**If CLAUDE.md does not exist:**
- Ask:
  1. What was just built or changed?
  2. Do you have a checklist or PRD to test against? Paste the relevant section.
- Wait for answers.

**If `$ARGUMENTS` is provided**, use it to scope the testing (e.g., "auth flow" or "Phase 2 tasks").

## Step 2: Create Validation Checklist

Based on what was built, generate a tailored checklist:

**Core Functionality**
- [ ] Primary user flow works end to end
- [ ] Each feature/requirement is met
- [ ] Data is saved/loaded/displayed correctly

**Edge Cases**
- [ ] Empty states handled (no data)
- [ ] Invalid input handled (bad data)
- [ ] Boundary conditions (min/max values, long strings)

**Error Handling**
- [ ] Failures handled gracefully
- [ ] Missing data doesn't crash the app
- [ ] Error messages are helpful

**Integration Points**
- [ ] API calls work correctly
- [ ] Database operations complete
- [ ] Third-party services respond as expected

**UI/UX (if applicable)**
- [ ] Layout matches requirements
- [ ] Responsive on different screen sizes
- [ ] Loading states shown during async ops
- [ ] Basic accessibility (keyboard nav, labels)

## Step 3: Run Tests

**Automated tests (if they exist):**
- Run the project's test suite using commands from CLAUDE.md
- Report: passed / failed / skipped
- For failures: diagnose and suggest fixes

**Manual verification:**
Walk through each validation item:
- **Pass** — Confirmed working
- **Fail** — What's wrong, link to relevant code
- **Skip** — Can't test now (explain why)

**User verification instructions:**
For each tested area, provide clear step-by-step instructions so the user can independently verify the results. Include what to run, what to navigate to, what to look for, and what the expected outcome should be. Don't assume the user knows how to trigger or observe the behavior — spell it out.

## Step 4: Test Report

**Summary**
- Total checks: X | Passed: X | Failed: X | Skipped: X

**Failures (if any)**
For each:
- What failed
- Expected vs. actual behavior
- Suggested fix
- Severity: Critical / Major / Minor

**Recommendations**
- Must-fix before shipping
- Can-wait issues
- Areas needing deeper testing
- Automated tests to add

## Step 5: Update Docs

- **Update docs immediately:** If `docs/checklist.md` exists, mark tested items with their test results (pass/fail). If `docs/prd.md` exists and has acceptance criteria related to what was tested, annotate it to reflect verification status.
- If failures found, suggest running `/fix` for each issue
- If all passes, suggest next steps (deploy, review, etc.)
- **Final doc check:** Verify that `docs/checklist.md` and `docs/prd.md` (if they exist) accurately reflect all test results from this session. Fix any items that were missed.

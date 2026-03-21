# Test Phase

Let's validate that what we built actually works.

**Answer these questions first:**

1. What was just built or changed? (feature name, area of code, or "everything in the last session")
2. Do you have a checklist or PRD to test against? If so, paste the relevant section.

**Wait for my answers before continuing.**

---

Once I've answered, here's what I want you to do:

## Testing Process

### Step 1: Create a Validation Checklist
Based on what was built, generate a checklist of things to verify:

**Core Functionality**
- [ ] [Primary user flow works end to end]
- [ ] [Each feature/requirement from the PRD is met]
- [ ] [Data is saved/loaded/displayed correctly]

**Edge Cases**
- [ ] [Empty states — what happens with no data?]
- [ ] [Invalid input — what happens with bad data?]
- [ ] [Boundary conditions — min/max values, long strings, etc.]

**Error Handling**
- [ ] [Network failures handled gracefully]
- [ ] [Missing data doesn't crash the app]
- [ ] [Error messages are helpful, not cryptic]

**Integration Points**
- [ ] [API calls work with real endpoints]
- [ ] [Database operations complete without errors]
- [ ] [Third-party services respond as expected]

**UI/UX (if applicable)**
- [ ] [Layout matches design/requirements]
- [ ] [Responsive on mobile/tablet/desktop]
- [ ] [Loading states shown during async operations]
- [ ] [Accessible (keyboard nav, screen reader basics)]

### Step 2: Run Automated Tests (if they exist)
- Run the project's test suite
- Report results: passed, failed, skipped
- For failures: diagnose and suggest fixes

### Step 3: Manual Verification
Walk through each item in the validation checklist. For each:
- **Pass**: Confirmed working
- **Fail**: Describe what's wrong, link to relevant code
- **Skip**: Can't test right now (explain why)

### Step 3.5: User Verification Instructions
For each tested area, provide me with clear step-by-step instructions so I can independently verify the results. Include what to run, what to navigate to, what to look for, and what the expected outcome should be. Don't assume I know how to trigger or observe the behavior — spell it out.

### Step 4: Test Report

**Summary**
- Total checks: X
- Passed: X
- Failed: X
- Skipped: X

**Failures (if any)**
For each failure:
- What failed
- Expected behavior
- Actual behavior
- Suggested fix
- Severity: Critical / Major / Minor

**Recommendations**
- Issues that should be fixed before shipping
- Issues that can wait
- Areas that need more thorough testing
- Suggested automated tests to add

---

**After the test report:**
- **Update docs immediately:** If `docs/checklist.md` exists, mark tested items with their test results (pass/fail). If `docs/prd.md` exists and has acceptance criteria related to what was tested, annotate it to reflect verification status.
- If there are failures, suggest running `/fix` or the fix prompt for each issue
- If everything passes, suggest next steps (deploy, code review, etc.)
- **Final doc check:** Verify that `docs/checklist.md` and `docs/prd.md` (if they exist) accurately reflect all test results from this session. Fix any items that were missed.

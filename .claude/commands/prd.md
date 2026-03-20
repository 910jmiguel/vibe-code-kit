# PRD Phase

You're helping the user create a Product Requirements Document.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it for project context, tech stack, and conventions
- Check if `docs/plan.md` exists — if so, read it and use it as the foundation for the PRD
- Skip onboarding. Ask: "What should this PRD cover? $ARGUMENTS"

**If CLAUDE.md does not exist:**
- Ask:
  1. What's the project? One-liner description.
  2. What's the tech stack?
  3. Do you have an existing plan or notes? Paste key points if so.
- Wait for answers.

**If `$ARGUMENTS` is provided**, use it as the PRD scope. Reference the plan if one exists in `docs/plan.md`.

## Step 2: Generate the PRD

### 1. Overview
- **Project Name**
- **One-liner:** What it does
- **Target Users:** Who and why
- **Success Criteria:** Measurable outcomes

### 2. Problem Statement
What problem is being solved? What's the current alternative?

### 3. Features & Requirements
For each feature:
- **Feature Name**
- **User Story:** As a [user], I want [action] so that [benefit]
- **Requirements:** Numbered, specific, testable
- **Acceptance Criteria:** How to verify it works
- **Priority:** Must-have / Should-have / Nice-to-have
- **Notes:** Edge cases, constraints, open questions

Group by feature area where it makes sense.

### 4. Technical Requirements
- Performance targets
- Security requirements
- Compatibility needs
- Third-party integrations
- Data storage and privacy

### 5. UI/UX Requirements
- Key screens/views (described, not designed)
- Navigation flow
- Responsive requirements
- Accessibility considerations

### 6. Out of Scope
What we're explicitly NOT building in this version.

### 7. Open Questions
Unresolved decisions, tagged with who needs to answer.

### 8. Timeline & Phases
Map features to implementation phases.

## Step 3: Review & Save

- Flag anything you assumed or guessed
- Ask the user to review each section
- Offer to save to `docs/prd.md`
- Suggest next step: "Run `/checklist` to break this into tasks"

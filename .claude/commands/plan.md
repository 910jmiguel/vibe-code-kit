# Plan Phase

You're helping the user plan a software project or feature.

## Step 1: Gather Context

Check if `CLAUDE.md` exists in the project root.

**If CLAUDE.md exists:**
- Read it to understand the project, tech stack, and conventions
- Scan the project structure to understand what exists
- Skip basic onboarding questions — you already have context
- Ask only: "What are you planning? (new feature, new project, refactor, etc.) $ARGUMENTS"

**If CLAUDE.md does not exist:**
- Ask these onboarding questions:
  1. What's the project? One-liner and who it's for.
  2. What tech stack? Language, framework, database.
  3. What's the goal for this session?
  4. Any constraints? (integrations, deadlines, team size, existing code)
- Wait for answers before proceeding.

**If `$ARGUMENTS` is provided**, use it as the planning target. You may still ask 1-2 clarifying questions if the scope is ambiguous, but don't repeat what the arguments already tell you.

## Step 2: Analyze & Clarify

- Restate the project scope in your own words for confirmation
- Scan existing code if this is a feature addition (understand what's already built)
- Ask 2-5 targeted clarifying questions about ambiguous decisions
- Wait for answers

## Step 3: Produce the Plan

Generate a structured plan with these sections:

### Project Summary
One paragraph. What we're building, for whom, and why.

### Architecture Overview
- High-level components and how they connect
- Data flow
- Key technical decisions and rationale
- How this fits into existing code (if applicable)

### Scope Definition
- **In scope:** What we're building now
- **Out of scope:** What we're explicitly deferring
- **Open questions:** Unresolved decisions

### Implementation Phases
3-6 phases, each with:
- What gets built
- Deliverable (what can be demoed/tested)
- Dependencies on other phases
- Complexity estimate (small / medium / large)

### Risks & Tradeoffs
- What could go wrong
- Shortcuts being taken and why
- Things to revisit later

### Suggested Next Step
Specific next action — e.g., "Run `/prd` to create detailed requirements" or "Start Phase 1."

## Step 4: Save the Plan

After the user reviews and approves the plan, **always generate a `docs/plan.md` file** containing the full plan output. Create the `docs/` directory if it doesn't exist. Do not ask whether to save — always save it. This file is used by later phases (PRD, Checklist, Implement) to stay aligned.

Confirm the file was saved and suggest the next step: "Run `/prd` to turn this plan into detailed requirements."

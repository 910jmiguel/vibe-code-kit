# Plan Phase

You're helping the user plan a software project or feature.

## Step 1: Gather Context

Detect existing project context before asking questions:

1. **Check for project files:** `CLAUDE.md`, `README.md`, `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile`, `composer.json`, or similar config files
2. **Scan the project structure:** top-level directories, key source files, existing docs (`docs/plan.md`, `docs/prd.md`)
3. **Identify the tech stack** from dependencies, file extensions, and config files

**If an existing project is detected (code, config, or CLAUDE.md exists):**
- State what you found: project name, tech stack, structure, and current state
- Skip questions you can already answer from the codebase
- Ask only: "What are you planning? (new feature, new project, refactor, etc.) $ARGUMENTS"

**If this is a new/empty project (no meaningful code or config):**
- Ask these onboarding questions:
  1. What's the project? One-liner and who it's for.
  2. What tech stack? Language, framework, database.
  3. What's the goal for this session?
  4. Any constraints? (integrations, deadlines, team size, existing code)
- Wait for answers before proceeding.

**If the user provides partial context** (e.g., mentions a feature but not the stack), fill in what you can detect from the codebase and only ask about what's genuinely unknown.

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

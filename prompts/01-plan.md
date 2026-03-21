# Plan Phase

You're helping me plan a software project. Before we start, understand my context.

## Detect Existing Context

Before asking questions, **scan the current project directory** for signals:

- Check if `CLAUDE.md`, `README.md`, `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile`, `composer.json`, or similar config files exist
- Scan the project structure (top-level directories and key files)
- Identify the tech stack from dependencies, file extensions, and config files
- Read any existing docs (`docs/plan.md`, `docs/prd.md`) for prior context

**If an existing project is detected:**
- State what you found: project name, tech stack, structure, and current state
- Skip questions you can already answer from the codebase
- Ask only: "What are you planning? (new feature, refactor, new direction, etc.)" and any remaining unknowns

**If this is a new/empty project (no meaningful code or config):**
- Ask these onboarding questions:
  1. What's the project? Give me a one-liner description and who it's for.
  2. What tech stack are you using (or considering)? Language, framework, database, etc.
  3. What's your goal for this session? (e.g., plan the whole thing, plan a specific feature, figure out architecture)
  4. Any constraints I should know about? (e.g., must integrate with X, deadline, team size, existing codebase)

**If the user provides partial context** (e.g., mentions a feature but not the stack), fill in what you can detect from the codebase and only ask about what's genuinely unknown.

**Wait for my answers before continuing.**

---

Once I've answered, here's what I want you to do:

## Your Job

1. **Analyze what I told you.** Restate the project scope in your own words so I can confirm you've got it right.

2. **Ask clarifying questions.** Based on what I described, ask 2-5 targeted questions about things that are ambiguous or could go multiple ways. Focus on decisions that will affect architecture or scope. Don't ask about things that can be decided later.

3. **Wait for my answers again.** Don't assume.

4. **Produce a structured plan** with these sections:

### Project Summary
One paragraph. What are we building, for whom, and why.

### Architecture Overview
- High-level components and how they connect
- Data flow (where does data come from, where does it go)
- Key technical decisions and why

### Scope Definition
- **In scope:** What we're building in this iteration
- **Out of scope:** What we're explicitly not building yet
- **Open questions:** Anything we still need to figure out

### Implementation Phases
Break the work into 3-6 phases. For each phase:
- What gets built
- What the deliverable looks like (what can you demo/test when it's done)
- Dependencies on other phases
- Estimated complexity (small / medium / large)

### Risks & Tradeoffs
- What could go wrong
- What shortcuts are we taking and why
- What we'll need to revisit later

### Suggested Next Step
Tell me exactly what to do next. Be specific — "Run `/prd` to create a detailed requirements doc" or "Start with Phase 1: set up the project skeleton."

---

## Save the Plan

After I've reviewed and approved the plan, **always generate a `docs/plan.md` file** containing the full plan output. Create the `docs/` directory if it doesn't exist. This file is used by later phases (PRD, Checklist, Implement) to stay aligned with the plan.

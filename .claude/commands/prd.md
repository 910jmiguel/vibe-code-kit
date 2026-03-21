# PRD Phase

You're helping the user create a Product Requirements Document — the most important document before building. This defines WHAT to build, WHO it's for, and WHY it matters.

## Step 1: Gather Context

Detect existing project context before asking questions:

1. **Check for project files:** `CLAUDE.md`, `README.md`, `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile`, `composer.json`, or similar config files
2. **Scan the project structure:** top-level directories, key source files
3. **Identify the tech stack** from dependencies, file extensions, and config files
4. **Check for existing docs:** `docs/plan.md`, `docs/prd.md`

**If an existing project is detected (code, config, or CLAUDE.md exists):**
- State what you found: project name, tech stack, structure, and current state
- Skip questions you can already answer from the codebase (e.g., don't ask "what tech stack?" if you can see it in config files)
- Check if `docs/plan.md` exists — if so, read it and use it as the foundation for the PRD
- If `docs/plan.md` does NOT exist, ask: "No plan found. Want me to run the Plan phase first to generate `docs/plan.md`? (Optional — I can write the PRD without it if you already know the scope.)"
- If plan exists or user declines, ask: "What should this PRD cover? $ARGUMENTS"

**If this is a new/empty project (no meaningful code or config):**
- Ask:
  1. What's the project? One-liner description.
  2. What's the tech stack?
  3. Do you have an existing plan or notes? Paste key points if so.
  4. Optional: Want me to run the Plan phase first?
- Wait for answers.

**If the user provides partial context** (e.g., mentions a feature but not the stack), fill in what you can detect from the codebase and only ask about what's genuinely unknown.

**If the user wants the Plan phase first**, run the full Plan workflow (Step 1–4 from `/plan`), save `docs/plan.md`, then continue with the PRD using that plan as the foundation.

**If `$ARGUMENTS` is provided**, use it as the PRD scope. Reference the plan if one exists in `docs/plan.md`.

## Step 2: Determine Scope & Experience Level

Ask two questions:

**Scope:** "What's the scope of this PRD?
- **Full project** — Building a new app/product from scratch
- **Feature / enhancement** — Adding something to an existing project
- **Small task** — A focused change, component, or minor addition"

**Experience:** "What's your experience level?
- **A) Vibe-coder** — Great ideas, limited coding experience, using AI to build
- **B) Developer** — Experienced programmer
- **C) Somewhere in between** — Some coding knowledge, still learning"

If `$ARGUMENTS` or CLAUDE.md clearly indicate the scope (e.g., "add dark mode" is a feature, "build a SaaS app" is a full project), infer it and confirm rather than asking.

## Step 3: Adaptive Q&A

Based on **both scope and experience level**, gather all required context. Do NOT generate the PRD until all essential answers are collected.

### Full Project Questions

#### Path A — Vibe-Coder:
1. Product name (brainstorm if undecided)
2. One-sentence problem statement
3. Launch goal (100 users, $1K MRR, learning, etc.)
4. Target users — who they are, what frustrates them, tech-savviness
5. User journey as a story: "[Name] has problem... discovers app... does X... happy because Y"
6. 3-5 MUST-have launch features (essentials only)
7. Features explicitly saved for v2
8. 1-2 success metrics
9. Visual vibe in 3-5 words
10. Constraints — budget, deadline, performance, security, platform needs

#### Path B — Developer:
1. Product name and one-liner
2. Target audience — personas, demographics, jobs to be done
3. 3-5 user stories in standard format
4. MoSCoW prioritized feature list
5. Success metrics with specific targets (activation, engagement, retention, revenue)
6. Non-functional requirements — performance, accessibility, platform support, security, scalability
7. Risk assessment — technical, market, execution
8. Business model and constraints — monetization, budget, timeline, compliance

#### Path C — In-Between:
1. Product name and problem statement
2. Users — who they are, their problem, current solution, why they'd switch
3. Main user flow walkthrough
4. 3-5 v1 features with name, description, and why essential
5. What's NOT in v1 and why
6. Success metrics at 1 month and 3 months
7. Design direction — visual style, key screens, responsive
8. Constraints — budget, timeline, performance, security, scalability

### Feature / Enhancement Questions (All Experience Levels):
1. Feature name and one-liner description
2. What problem does this solve for existing users? Current workaround?
3. Who specifically benefits? (Could be a subset of users)
4. User flow — how someone discovers, uses, and gets value from this feature
5. Specific requirements — everything it must do
6. UI — key screens, components, or interactions
7. Edge cases and error states to handle
8. How it interacts with existing features — dependencies or conflicts
9. Success metric — how you'll know it's working

### Small Task Questions (All Experience Levels):
1. What are you building/changing? Be specific.
2. What should it do? List the requirements.
3. Does it have a UI component? If so, describe it.
4. Any edge cases to handle?
5. How will you verify it works?

## Step 4: Verification Echo (Required)

After ALL questions are answered, summarize back before generating. Adapt the echo to scope:

**Full Project:**
> **Product:** [Name] — [One-line description]
> **Target User:** [Primary persona]
> **Problem:** [Core problem]
> **Must-Have Features:** [Numbered list]
> **Success Metric:** [Primary metric and target]
> **Timeline:** [Launch target]
> **Constraints:** [Key constraints]

**Feature / Enhancement:**
> **Feature:** [Name] — [One-line description]
> **Problem it solves:** [What's broken or missing today]
> **Who benefits:** [Which users]
> **Requirements:** [Numbered list]
> **Depends on:** [Existing features/systems it touches]

**Small Task:**
> **Task:** [Name] — [What it does]
> **Requirements:** [Numbered list]
> **Has UI:** [Yes/No — brief description if yes]

Ask: **"Is this accurate? Should I adjust anything before creating the PRD?"**

Wait for confirmation. If the user corrects anything, update understanding before proceeding.

## Step 5: Generate the PRD

Generate a complete `.md` document adapting to **both scope and experience level** (conversational for A, technical for B, balanced for C).

### Full Project → Use all 11 sections:
```
# Product Requirements Document: [App Name] MVP

## 1. Product Overview
- App name, tagline, launch goal, target launch date, document status

## 2. Problem Statement
- What problem, why it matters, why now
- Table: Current solutions vs. their pain points vs. our advantage

## 3. Target Users
- Primary persona (who, goal, frustration, current workaround)
- User journey story (narrative format)
- User journey map table (stage, action, touchpoint, emotion, opportunity)

## 4. Features & Requirements
- Must Have (P0) — each with: description, user story, numbered requirements,
  acceptance criteria checkboxes, edge cases, priority
- Should Have (P1) — table format with planned timeline
- Won't Have — table with reason and revisit trigger

## 5. UI/UX Requirements
- Design direction (visual style words, design principles)
- Key screens with ASCII wireframes showing layout
- Navigation flow diagram
- UI quality standards: responsive breakpoints, loading/empty/error states,
  animations, typography, spacing, color contrast, touch targets, dark mode

## 6. Technical Requirements
- Performance targets table (page load, API response, TTI, Core Web Vitals)
- Security & privacy requirements
- Browser/device compatibility
- Third-party integrations table

## 7. Success Metrics
- North star metric
- Detailed metrics table (acquisition, activation, engagement, retention, revenue)

## 8. Constraints & Risks
- Constraints table (budget, timeline, team, technical)
- Risk assessment table (risk, probability, impact, mitigation)
- Assumptions and open questions

## 9. Quality Standards
- What this project will NOT accept (placeholder content, half-working features,
  broken mobile, skipped accessibility, swallowed errors, console warnings)
- Code quality rules (strict types, error handling, no dead code)
- Design quality rules (design tokens, interaction states, async states, alt text)

## 10. Definition of Done
- Feature checklist (P0 complete, acceptance criteria met, edge cases handled)
- Quality checklist (mobile/desktop, cross-browser, no critical bugs, error states,
  loading states, empty states)
- Performance checklist (load time, no layout shifts, optimized images)
- Accessibility checklist (keyboard nav, screen reader, color contrast)
- Launch ready checklist (analytics, SEO, privacy policy, deployment, beta tested)

## 11. Timeline & Phases
- Table mapping phases to features, deliverables, and estimates

## Next Steps
- Review PRD → Create checklist → Start building
```

### Feature / Enhancement → Lighter structure:
```
# Feature PRD: [Feature Name]

## Overview — feature name, parent project, one-liner, status, date
## Problem & Context — what problem, current workaround, who benefits, why now
## User Flow — step-by-step: entry point → core interaction → result → edge cases
## Requirements — must-have table (requirement + acceptance criteria), nice-to-have, out of scope
## UI/UX — design direction, key screens with ASCII wireframes + states, where it lives in nav
## Technical Considerations — files/systems it touches, dependencies, performance, security
## Quality Standards — matches project style, all states handled, responsive, accessible, no regressions
## Success Metric — how to know it works
## Definition of Done — requirements met, tested, reviewed, no regressions
```

### Small Task → Minimal structure:
```
# Task PRD: [Task Name]

## What — task name, parent project, date
## Why — one paragraph on what problem this solves
## Requirements — numbered table with done checkboxes
## UI (if applicable) — simple layout sketch + states
## Edge Cases — what happens when X/Y
## Definition of Done — requirements met, tested, no regressions
```

## Step 6: Self-Verification

After generating, verify the PRD against the appropriate checklist:

### Full Project:
| Required Section | Present? |
|:--|:--|
| Core problem clearly defined | ✅ / ❌ |
| Target user well described | ✅ / ❌ |
| 3-5 must-have features with user stories | ✅ / ❌ |
| Each feature has acceptance criteria | ✅ / ❌ |
| UI/UX direction with wireframes | ✅ / ❌ |
| Success metrics defined | ✅ / ❌ |
| Quality standards included | ✅ / ❌ |
| Definition of done included | ✅ / ❌ |
| Out-of-scope features listed | ✅ / ❌ |
| Constraints acknowledged | ✅ / ❌ |

### Feature / Enhancement:
| Required Section | Present? |
|:--|:--|
| Problem and context explained | ✅ / ❌ |
| User flow described | ✅ / ❌ |
| Requirements with acceptance criteria | ✅ / ❌ |
| UI/UX with states (loading, error, empty) | ✅ / ❌ |
| Technical considerations listed | ✅ / ❌ |
| Quality standards included | ✅ / ❌ |
| Definition of done included | ✅ / ❌ |

### Small Task:
| Required Section | Present? |
|:--|:--|
| Requirements listed | ✅ / ❌ |
| Edge cases identified | ✅ / ❌ |
| UI described (if applicable) | ✅ / ❌ |
| Definition of done included | ✅ / ❌ |

If any items are missing, add them before saving.

## Step 7: Save & Next

- **Always generate a `docs/prd.md` file** containing the full PRD. Create the `docs/` directory if it doesn't exist. Do not ask whether to save — always save it.
- Flag anything that was assumed or guessed
- Ask the user to review
- Confirm the file was saved and suggest next step: "Run `/checklist` to break this PRD into actionable tasks"

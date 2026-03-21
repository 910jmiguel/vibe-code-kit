# PRD Phase

You're helping me write a Product Requirements Document. This defines WHAT we're building, WHO it's for, and WHY it matters — whether that's a full app or a single feature.

---

## Before We Start

**Answer these questions first:**

1. What are you building? One-liner description.
2. What's the scope?
   - **Full project** — Building a new app/product from scratch
   - **Feature / enhancement** — Adding something to an existing project
   - **Small task** — A focused change, component, or minor addition
3. What's the tech stack? (Language, framework, database, hosting)
4. What's your experience level?
   - **A) Vibe-coder** — Great ideas, limited coding experience, using AI to build
   - **B) Developer** — Experienced programmer
   - **C) Somewhere in between** — Some coding knowledge, still learning
5. Do you have an existing plan or notes? If so, paste them here. If not, just describe what you want to build.
6. **Optional:** If you don't have a plan yet, I can run the **Plan phase** first to generate one before writing the PRD. Want me to do that? (If you already know what you're building, skip this.)

**Wait for my answers before continuing.**

> **Note:** If I say yes to running the Plan phase first, use the plan prompt (`prompts/01-plan.md`) to generate a plan, save it to `docs/plan.md`, and then continue with the PRD using that plan as the foundation.

---

## Scope-Aware Behavior

The PRD adapts based on scope. Use the right depth — don't force a full-project PRD onto a small feature.

| Scope | PRD Sections to Include | Questions to Ask |
|:--|:--|:--|
| **Full project** | All 11 sections (full template) | All questions for the experience level |
| **Feature / enhancement** | Sections 1, 3, 4, 5, 6, 9, 10 (skip problem statement, full metrics, constraints/risks, timeline) | Shortened set — focus on what the feature does, who uses it, UI, and acceptance criteria |
| **Small task** | Sections 1, 4, 5, 10 only (lightweight) | Minimal — what it does, requirements, UI if applicable, definition of done |

---

## Adaptive Q&A

Based on my **experience level** AND **scope**, ask the appropriate questions. Do NOT generate the PRD until all essential answers are collected.

### Full Project Questions

#### If I picked A (Vibe-Coder):

**Q1:** "What's the name of your product/app? (If undecided, we can brainstorm!)"

**Q2:** "In one sentence, what problem does it solve? (Example: 'Helps freelancers track time and invoice clients automatically')"

**Q3:** "What's your launch goal? (Examples: '100 users', '$1000 MRR', 'Replace my day job', 'Learn to build apps')"

**Q4:** "Who will use your app? Describe them like you're explaining to a friend — what do they do, what frustrates them, how tech-savvy are they?"

**Q5:** "Tell me the user journey as a story: '[Name] has problem X... discovers your app... does Y... now they're happy because Z.' Use your own character!"

**Q6:** "What are the 3-5 MUST-have features for launch? The absolute essentials only."

**Q7:** "What features are you intentionally saving for version 2? (This keeps MVP simple)"

**Q8:** "How will you know it's working? Pick 1-2 simple metrics: signups, daily active users, tasks completed, feedback score?"

**Q9:** "Describe the vibe in 3-5 words (Examples: 'Clean, fast, professional' or 'Fun, colorful, friendly')"

**Q10:** "Any constraints? Budget limits, launch deadline, performance needs, security/privacy concerns, platform requirements?"

#### If I picked B (Developer):

**Q1:** "Product name and one-liner."

**Q2:** "Define your target audience — primary persona (demographics, role, tech level), secondary personas, jobs to be done."

**Q3:** "Write 3-5 user stories: 'As a [user type], I want to [action] so that [benefit]'"

**Q4:** "List core MVP features with MoSCoW prioritization: Must have (3-5), Should have (2-3), Could have (2-3), Won't have this release."

**Q5:** "Define success metrics with specific targets — activation, engagement, retention, revenue (if applicable)."

**Q6:** "Non-functional requirements — performance targets, accessibility standards, platform support, security/privacy, scalability expectations, design system preferences."

**Q7:** "Risk assessment — technical risks, market risks, execution risks."

**Q8:** "Business model and constraints — monetization strategy, budget, timeline, compliance/regulatory needs."

#### If I picked C (In-Between):

**Q1:** "What's the name of your product? What problem does it solve in one sentence?"

**Q2:** "Who are your users? Describe their main problem, what they currently use, and why they'd switch."

**Q3:** "Walk through the main user flow: user arrives because... first thing they see... core action they take... value they get."

**Q4:** "What 3-5 features must be in v1? For each: name, what it does, why it's essential."

**Q5:** "What are you NOT building yet? What's saved for v2 and why?"

**Q6:** "How will you measure success at 1 month and 3 months?"

**Q7:** "Design direction — visual style, key screens, mobile responsive?"

**Q8:** "Constraints — budget, timeline, non-functional requirements (performance, security, scalability, compliance)?"

---

### Feature / Enhancement Questions (All Experience Levels)

**Q1:** "What's the feature called? One-liner description of what it does."

**Q2:** "What problem does this feature solve for existing users? What's the current workaround (if any)?"

**Q3:** "Who specifically benefits from this feature? (Could be a subset of your users)"

**Q4:** "Describe the user flow — how does someone discover, use, and get value from this feature?"

**Q5:** "What are the specific requirements? List everything it must do."

**Q6:** "What does the UI look like? Describe the key screens, components, or interactions."

**Q7:** "What edge cases or error states should we handle?"

**Q8:** "How does this feature interact with existing features? Any dependencies or conflicts?"

**Q9:** "How will you know this feature is successful? (Usage metric, user feedback, etc.)"

---

### Small Task Questions (All Experience Levels)

**Q1:** "What are you building/changing? Be specific."

**Q2:** "What should it do? List the requirements."

**Q3:** "Does it have a UI component? If so, describe what it looks like."

**Q4:** "Any edge cases to handle?"

**Q5:** "How will you verify it works?"

---

## Verification Echo (Required)

After completing ALL questions, summarize back to me before generating anything. Adapt the echo to scope:

### Full Project Echo:
> **Product:** [Name] — [One-line description]
> **Target User:** [Primary persona]
> **Problem:** [Core problem being solved]
> **Must-Have Features:**
> 1. [Feature 1]
> 2. [Feature 2]
> 3. [Feature 3]
> **Success Metric:** [Primary metric and target]
> **Timeline:** [Launch target]
> **Constraints:** [Key constraints]

### Feature / Enhancement Echo:
> **Feature:** [Name] — [One-line description]
> **Problem it solves:** [What's broken or missing today]
> **Who benefits:** [Which users]
> **Requirements:**
> 1. [Requirement 1]
> 2. [Requirement 2]
> 3. [Requirement 3]
> **Depends on:** [Existing features/systems it touches]

### Small Task Echo:
> **Task:** [Name] — [What it does]
> **Requirements:** [Numbered list]
> **Has UI:** [Yes/No — brief description if yes]

**Is this accurate? Should I adjust anything before creating the PRD?**

**Wait for my confirmation. If I correct anything, update your understanding before proceeding.**

---

## Generate the PRD

After verification, generate a PRD as a complete `.md` document. Adapt based on **both scope and experience level** — conversational for vibe-coders, technical for developers, balanced for in-between.

- **Full project** → Use the full template (all 11 sections)
- **Feature / enhancement** → Use the feature template (below the full template)
- **Small task** → Use the small task template (below the feature template)

### Full Project PRD Template

```markdown
# Product Requirements Document: [App Name] MVP

## 1. Product Overview

**App Name:** [Name]
**Tagline:** [One-liner, polished]
**Launch Goal:** [What success looks like]
**Target Launch:** [Date or timeframe]
**Document Status:** Draft
**Last Updated:** [Date]

---

## 2. Problem Statement

[What problem does this solve? Why does it matter? Why now?]

**Why Existing Solutions Fall Short:**
| Current Solution | Pain Points | Our Advantage |
|:--|:--|:--|
| [Solution/competitor] | [Why it fails] | [How we're better] |
| [Solution/competitor] | [Why it fails] | [How we're better] |

---

## 3. Target Users

### Primary Persona: [Name]
- **Who:** [Description — role, demographics, tech level]
- **Goal:** [What they want to achieve]
- **Frustration:** [What they struggle with today]
- **Current Workaround:** [What they use now]

### User Journey Story
> "[Name] is a [role] who struggles with [problem]. Every day they [painful current workflow].
> They discover [App Name] and [first action]. Within [timeframe], they can [core value].
> Now they [desired outcome] and no longer worry about [old problem]."

### User Journey Map
| Stage | User Action | Touchpoint | Emotion | Opportunity |
|:--|:--|:--|:--|:--|
| Discovery | [How they find us] | [Channel] | Curious | [Hook] |
| Onboarding | [First 5 minutes] | [Screen] | Hopeful | [Quick win] |
| Core Usage | [Main action loop] | [Feature] | Satisfied | [Delight] |
| Retention | [What brings them back] | [Trigger] | Loyal | [Growth] |

---

## 4. Features & Requirements

### Must Have (P0 — Launch Blockers)

#### Feature 1: [Name]
- **What:** [Clear description]
- **User Story:** As a [user], I want to [action] so that [benefit]
- **Requirements:**
  1. [Specific, testable requirement]
  2. [Specific, testable requirement]
  3. [Specific, testable requirement]
- **Acceptance Criteria:**
  - [ ] [Verifiable criterion]
  - [ ] [Verifiable criterion]
  - [ ] [Verifiable criterion]
- **Edge Cases:**
  - [What happens when X?]
  - [What happens when Y?]
- **Priority:** P0 (Critical)

#### Feature 2: [Name]
[Same structure — repeat for all must-have features]

### Should Have (P1 — Important, Not Blocking)
| Feature | Description | User Value | Planned For |
|:--|:--|:--|:--|
| [Feature] | [Brief] | [Why] | Post-launch |
| [Feature] | [Brief] | [Why] | Post-launch |

### Won't Have (Explicitly Out of Scope)
| Feature | Why It's Out | Revisit When |
|:--|:--|:--|
| [Feature] | [Reason] | [Trigger/milestone] |
| [Feature] | [Reason] | [Trigger/milestone] |

*Keeping these out of MVP ensures we ship on time and stay focused.*

---

## 5. UI/UX Requirements

### Design Direction
**Visual Style:** [3-5 descriptive words]

**Design Principles:**
1. **[Principle]** — [How it applies to this product]
2. **[Principle]** — [How it applies to this product]
3. **[Principle]** — [How it applies to this product]

### Key Screens

#### Screen 1: [Name] — [Purpose]
```
┌─────────────────────────────────┐
│  [Logo]            [Nav Items]  │
├─────────────────────────────────┤
│                                 │
│     [Hero / Primary Content]    │
│                                 │
├────────────┬────────────────────┤
│  [Sidebar] │  [Main Content]    │
│            │                    │
│            │                    │
├────────────┴────────────────────┤
│     [Footer / Secondary CTA]   │
└─────────────────────────────────┘
```
- **Key Elements:** [What's on this screen]
- **User Actions:** [What users can do here]
- **States:** Empty, loading, populated, error

#### Screen 2: [Name] — [Purpose]
[Same structure with wireframe]

### Navigation Flow
```
[Landing] → [Sign Up / Sign In] → [Dashboard]
                                       │
                          ┌────────────┼────────────┐
                          │            │            │
                    [Feature A]  [Feature B]  [Settings]
```

### UI Quality Standards
- **Responsive:** Mobile-first design, breakpoints at 640px / 768px / 1024px / 1280px
- **Loading States:** Skeleton screens for async content — never a blank screen
- **Empty States:** Helpful illustrations/copy with a clear CTA — never just "No data"
- **Error States:** User-friendly messages explaining what happened and what to do next
- **Animations:** Subtle, purposeful transitions (200-300ms) — no gratuitous movement
- **Typography:** Clear hierarchy (max 2 font families), minimum 16px body text
- **Spacing:** Consistent spacing scale (4px base unit)
- **Color:** Accessible contrast ratios (WCAG 2.1 AA minimum — 4.5:1 for text)
- **Touch Targets:** Minimum 44x44px for interactive elements on mobile
- **Dark Mode:** [Required / Nice-to-have / Not needed]

---

## 6. Technical Requirements

### Performance
| Metric | Target |
|:--|:--|
| Page load (initial) | < 3 seconds |
| Page load (cached) | < 1 second |
| API response time | < 500ms (p95) |
| Time to interactive | < 2 seconds |
| Core Web Vitals | All green |

### Security & Privacy
- [Authentication method]
- [Data encryption requirements]
- [Privacy considerations — what data is collected, stored, shared]
- [Compliance needs — GDPR, CCPA, etc.]

### Compatibility
- **Browsers:** Chrome, Safari, Firefox, Edge (latest 2 versions)
- **Mobile:** iOS 15+, Android 11+
- **Responsive:** Yes — mobile, tablet, desktop

### Integrations
| Service | Purpose | Required For |
|:--|:--|:--|
| [Service] | [What it does] | [Which feature] |

---

## 7. Success Metrics

### Primary Metric (North Star)
**[Metric Name]:** [Target] by [Date]

### Detailed Metrics
| Category | Metric | Target | How to Measure |
|:--|:--|:--|:--|
| Acquisition | [Metric] | [Target] | [Method] |
| Activation | [Metric] | [Target] | [Method] |
| Engagement | [Metric] | [Target] | [Method] |
| Retention | [Metric] | [Target] | [Method] |
| Revenue | [Metric] | [Target] | [Method] |

---

## 8. Constraints & Risks

### Constraints
| Type | Detail |
|:--|:--|
| Budget | [Amount or range] |
| Timeline | [Launch target] |
| Team | [Size and composition] |
| Technical | [Platform or framework constraints] |

### Risk Assessment
| Risk | Probability | Impact | Mitigation |
|:--|:--|:--|:--|
| [Risk] | High/Med/Low | High/Med/Low | [Strategy] |
| [Risk] | High/Med/Low | High/Med/Low | [Strategy] |

### Assumptions
- [Assumption about users]
- [Assumption about market]
- [Assumption about technology]

### Open Questions
- [Question — who needs to answer]
- [Question — who needs to answer]

---

## 9. Quality Standards

### What This Project Will NOT Accept
- Placeholder content in production ("Lorem ipsum", stock photos as final assets)
- Half-working features — everything ships complete or gets cut
- Broken mobile experience — test on real devices before launch
- Skipping accessibility basics (contrast, labels, keyboard nav)
- Swallowed errors — every error gets a user-friendly message
- Console warnings/errors in production

### Code Quality
- Strict types — no `any` in TypeScript, no untyped variables
- Explicit error handling on all API calls and user inputs
- No dead code, debug logs, or commented-out blocks at launch
- Consistent naming and file organization

### Design Quality
- Use design tokens (not raw hex/pixel values)
- Every interactive element has hover, active, focus, and disabled states
- Every async operation has loading, success, and error states
- All images have alt text, all form inputs have labels

---

## 10. Definition of Done

The MVP is ready to launch when:

### Features
- [ ] All P0 features are functional and tested
- [ ] Each feature meets its acceptance criteria
- [ ] Edge cases from PRD are handled

### Quality
- [ ] Works on mobile and desktop
- [ ] Cross-browser tested (Chrome, Safari, Firefox)
- [ ] No critical or major bugs
- [ ] All error states show user-friendly messages
- [ ] Loading states for all async operations
- [ ] Empty states are designed (not blank)

### Performance
- [ ] Page loads in under 3 seconds
- [ ] No layout shifts during load
- [ ] Images optimized

### Accessibility
- [ ] Keyboard navigable
- [ ] Screen reader friendly (alt text, ARIA labels)
- [ ] Color contrast meets WCAG AA

### Launch Ready
- [ ] Analytics/tracking configured
- [ ] Basic SEO (title, description, OG tags)
- [ ] Privacy policy / terms (if needed)
- [ ] Deployment pipeline working
- [ ] 5-10 people have tested it

---

## 11. Timeline & Phases

| Phase | What Gets Built | Deliverable | Estimate |
|:--|:--|:--|:--|
| 1. [Name] | [Features] | [What you can demo] | [Size] |
| 2. [Name] | [Features] | [What you can demo] | [Size] |
| 3. [Name] | [Features] | [What you can demo] | [Size] |

---

## Next Steps

1. Review and approve this PRD
2. Create a checklist — run the Checklist phase to break features into tasks
3. Start building — run the Implement phase

---
*Created: [Date]*
*Status: Draft — Ready for Review*
```

---

### Feature / Enhancement PRD Template

For features added to an existing project. Lighter than a full PRD — focuses on what the feature does, how it fits in, and how to verify it works.

```markdown
# Feature PRD: [Feature Name]

## Overview
**Feature:** [Name]
**Project:** [Parent project name]
**Status:** Draft
**Last Updated:** [Date]
**One-liner:** [What this feature does in one sentence]

---

## Problem & Context
**What problem does this solve?** [Description]
**Current workaround:** [What users do today, or "none"]
**Who benefits:** [Which user segment]
**Why now:** [Why this feature, why this priority]

---

## User Flow
[Step-by-step walkthrough of how a user discovers, uses, and gets value from this feature]

1. **Entry point:** [How users reach this feature]
2. **Core interaction:** [What they do]
3. **Result:** [What they get]
4. **Edge cases:** [What happens when things go wrong]

---

## Requirements

### Must Have
| # | Requirement | Acceptance Criteria |
|:--|:--|:--|
| 1 | [Requirement] | [How to verify] |
| 2 | [Requirement] | [How to verify] |
| 3 | [Requirement] | [How to verify] |

### Nice to Have
- [Requirement] — [Why it can wait]
- [Requirement] — [Why it can wait]

### Explicitly Out of Scope
- [Thing we're not building] — [Why]

---

## UI/UX

### Design Direction
[Visual style, how it fits with existing UI]

### Key Screens / Components
#### [Screen/Component Name]
```
┌─────────────────────────────┐
│  [Layout sketch]            │
│                             │
└─────────────────────────────┘
```
- **Elements:** [What's on screen]
- **States:** Empty, loading, populated, error
- **Interactions:** [Hover, click, drag, etc.]

### Where It Lives
[How users navigate to this feature — menu item, button, URL, etc.]

---

## Technical Considerations
- **Touches:** [Which existing files, APIs, or systems]
- **Dependencies:** [External services, other features]
- **Performance:** [Any specific targets]
- **Security:** [Data concerns, permissions]

---

## Quality Standards
- [ ] Matches existing project style and conventions
- [ ] All states handled (loading, empty, error, success)
- [ ] Responsive / works on mobile (if UI feature)
- [ ] Accessible (keyboard nav, labels, contrast)
- [ ] No regressions to existing features
- [ ] Edge cases from requirements are handled

---

## Success Metric
**How we'll know it works:** [Specific metric or verification method]

---

## Definition of Done
- [ ] All must-have requirements met
- [ ] Acceptance criteria verified
- [ ] UI matches design direction
- [ ] Tested on mobile and desktop
- [ ] No new console errors or warnings
- [ ] Existing tests still pass
- [ ] Code reviewed

---
*Created: [Date]*
*Status: Draft — Ready for Review*
```

---

### Small Task PRD Template

For focused changes — a component, a fix approach, a small addition. Just enough structure to build it right.

```markdown
# Task PRD: [Task Name]

## What
**Task:** [What you're building or changing]
**Project:** [Parent project name]
**Last Updated:** [Date]

## Why
[One paragraph — what problem this solves or what it enables]

## Requirements
| # | Requirement | Done? |
|:--|:--|:--|
| 1 | [Requirement] | [ ] |
| 2 | [Requirement] | [ ] |
| 3 | [Requirement] | [ ] |

## UI (if applicable)
```
[Simple layout sketch or "N/A — no UI changes"]
```
- **States:** [Loading, empty, error, success — or N/A]

## Edge Cases
- [What happens when X?]
- [What happens when Y?]

## Definition of Done
- [ ] All requirements met
- [ ] Edge cases handled
- [ ] Tested and working
- [ ] Matches project conventions
- [ ] No regressions

---
*Created: [Date]*
```

---

## After Generating the PRD

1. Run the **self-verification checklist** (use the one matching the scope):

### Full Project Verification:
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

### Feature Verification:
| Required Section | Present? |
|:--|:--|
| Problem and context explained | ✅ / ❌ |
| User flow described | ✅ / ❌ |
| Requirements with acceptance criteria | ✅ / ❌ |
| UI/UX with states (loading, error, empty) | ✅ / ❌ |
| Technical considerations listed | ✅ / ❌ |
| Quality standards included | ✅ / ❌ |
| Definition of done included | ✅ / ❌ |

### Small Task Verification:
| Required Section | Present? |
|:--|:--|
| Requirements listed | ✅ / ❌ |
| Edge cases identified | ✅ / ❌ |
| UI described (if applicable) | ✅ / ❌ |
| Definition of done included | ✅ / ❌ |

If any items are missing, add them before saving.

2. **Always generate a `docs/prd.md` file** containing the full PRD. Create the `docs/` directory if it doesn't exist.

3. Ask me to review and flag anything you had to assume or guess.

4. Suggest next step: "Run `/checklist` or use the checklist prompt to break this PRD into actionable tasks."

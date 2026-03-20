<p align="center">
  <h1 align="center">vibe-code-kit</h1>
  <p align="center">
    A structured vibe coding template for Claude Code.<br/>
    Go from raw idea to shipped feature in six guided phases.
  </p>
</p>

<p align="center">
  <strong>Plan</strong> &rarr; <strong>PRD</strong> &rarr; <strong>Checklist</strong> &rarr; <strong>Implement</strong> &rarr; <strong>Fix</strong> &rarr; <strong>Test</strong>
</p>

---

## How It Works

Two entry points — pick the one that fits your workflow:

<table>
<tr>
<td width="50%">

### A) Copy-Paste Prompts
**Zero setup. Just copy and paste.**

```
1. Open a file in prompts/
2. Copy the contents
3. Paste into Claude Code
4. Answer the onboarding questions
5. Follow the guided workflow
```

> Best for: quick projects, one-off tasks, trying it out

</td>
<td width="50%">

### B) Slash Commands
**Deep integration with Claude Code.**

```
1. Copy .claude/ into your project root
2. Fill in CLAUDE.md with your project details
3. Type /plan, /prd, /checklist, etc.
```

> Best for: ongoing projects, teams, repeated workflows

</td>
</tr>
</table>

### Not sure which to pick?

| | Prompts (A) | Slash Commands (B) |
|:--|:--|:--|
| **Setup time** | None | 5 minutes |
| **How to run** | Copy-paste into Claude Code | Type `/plan`, `/prd`, etc. |
| **Project context** | Asks you every time | Reads from `CLAUDE.md` automatically |
| **Codebase access** | No — can't scan files | Yes — scans project structure |
| **Inline arguments** | No | Yes — e.g. `/fix the login is broken` |

**Start with prompts. Move to slash commands when you want tighter integration.**

---

## The Six Phases

Each phase builds on the last. Use them in order for a new project, or jump to the one you need.

```
  +----------+       +-------+       +-----------+
  |  1. Plan  | ----> | 2. PRD | ----> | 3. Check- |
  |           |       |        |       |    list   |
  +----------+       +-------+       +-----------+
                                            |
                                            v
  +----------+       +-------+       +-----------+
  |  6. Test  | <---- | 5. Fix | <---- | 4. Imple- |
  |           |       |        |       |    ment   |
  +----------+       +-------+       +-----------+
```

### 1. Plan
> `/plan` or `prompts/01-plan.md`

Define what you're building, the architecture, and implementation phases. Produces a structured plan with scope, risks, and next steps.

### 2. PRD
> `/prd` or `prompts/02-prd.md`

Turn the plan into a Product Requirements Document — features, user stories, acceptance criteria, and technical requirements.

### 3. Checklist
> `/checklist` or `prompts/03-checklist.md`

Break the PRD into concrete, ordered tasks with checkboxes. Grouped by phase, ordered by dependency, decision points flagged.

### 4. Implement
> `/implement` or `prompts/04-implement.md`

Write the code. Three modes:
- **Step-by-step** (default) — one task at a time, check in after each
- **Full build** — complete a whole phase, check in at the end
- **Plan only** — preview the approach without writing code

### 5. Fix
> `/fix` or `prompts/05-fix.md`

Something broke? Diagnose the root cause, make the minimal fix, verify it works. No unnecessary refactoring.

### 6. Test
> `/test` or `prompts/06-test.md`

Validate the build. Generates a validation checklist, runs existing tests, walks through manual checks, and produces a test report.

---

## Project Structure

```
vibe-code-kit/
│
├── .claude/commands/        # Slash commands (Entry Point B)
│   ├── plan.md
│   ├── prd.md
│   ├── checklist.md
│   ├── implement.md
│   ├── fix.md
│   └── test.md
│
├── prompts/                 # Copy-paste prompts (Entry Point A)
│   ├── 01-plan.md
│   ├── 02-prd.md
│   ├── 03-checklist.md
│   ├── 04-implement.md
│   ├── 05-fix.md
│   └── 06-test.md
│
├── skills/
│   └── vibe-coding.md       # Core coding principles & behavior
│
├── examples/
│   ├── sample-prd.md         # Example PRD (GitHub Activity Dashboard)
│   └── sample-checklist.md   # Matching checklist with progress
│
├── CLAUDE.md                 # Project context template — fill this in
└── README.md
```

---

## Setting Up CLAUDE.md

> Only needed for Entry Point B (slash commands). Prompts work without it.

`CLAUDE.md` tells Claude Code about your project. Fill in what you can — you don't need everything on day one.

| Section | What to write | Priority |
|:--|:--|:--|
| **Overview** | What it does, who it's for | Start here |
| **Tech Stack** | Language, framework, database, testing | Start here |
| **Key Commands** | install, dev, test, build, lint | Start here |
| **Project Structure** | Top-level directory tree | Add when helpful |
| **Code Conventions** | Naming, patterns, file organization | Add when helpful |
| **Architecture Notes** | Data flow, key boundaries | Add when helpful |
| **Known Gotchas** | Things that trip people up | Add over time |
| **Current Status** | What works, what's in progress | Update as you go |

---

## Examples

The `examples/` folder has a complete PRD and matching checklist for a fictional **GitHub Activity Dashboard** project. Use them to:

- See what good output looks like from each phase
- Understand the level of detail the prompts produce
- Try the prompts/commands without committing to a real project

---

## Tips

| Tip | Details |
|:--|:--|
| **Jump to any phase** | Have a bug? Go straight to `/fix`. Know what to build? Skip to `/implement`. |
| **Phases chain together** | Slash commands save to `docs/` — the next phase picks up automatically. |
| **Prompts are editable** | They're just markdown. Add sections, change questions, adjust the tone. |
| **CLAUDE.md grows with you** | Update it as the project evolves. Better context = better output. |
| **Use inline arguments** | `/fix the API returns 500 on empty input` is faster than answering questions. |

---

## License

MIT

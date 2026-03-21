<p align="center">
  <h1 align="center">🎯 vibe-code-kit</h1>
  <p align="center">
    A structured vibe coding template for Claude Code.<br/>
    Go from raw idea to shipped feature in six guided phases.
  </p>
</p>

<p align="center">
  📋 <strong>Plan</strong> &rarr; 📄 <strong>PRD</strong> &rarr; ✅ <strong>Checklist</strong> &rarr; 🔨 <strong>Implement</strong> &rarr; 🔧 <strong>Fix</strong> &rarr; 🧪 <strong>Test</strong>
</p>

---

## 📑 Table of Contents

- [🗺️ What Do You Want to Do?](#️-what-do-you-want-to-do)
- [🚀 How It Works](#-how-it-works)
- [🔀 Not Sure Which to Pick?](#-not-sure-which-to-pick)
- [🔄 The Six Phases](#-the-six-phases)
- [📁 Project Structure](#-project-structure)
- [⚙️ Setting Up CLAUDE.md](#️-setting-up-claudemd)
- [📚 Examples](#-examples)
- [💡 Tips](#-tips)
- [📄 License](#-license)

---

## 🗺️ What Do You Want to Do?

Pick your scenario — each one tells you exactly which phases to use and in what order.

<table>
<tr>
<td width="50%">

### 🏗️ Build a whole project from scratch
**Use all 6 phases in order:**

```
📋 Plan  →  📄 PRD  →  ✅ Checklist  →  🔨 Implement  →  🧪 Test
```

1. Start with **Plan** to define scope and architecture
2. Run **PRD** to detail features, UI, and requirements
3. Run **Checklist** to break it into ordered tasks
4. Run **Implement** to build phase by phase
5. Run **Test** to validate the build
6. Use **Fix** whenever something breaks

> Each phase saves a `.md` file to `docs/` — the next phase reads it automatically.

</td>
<td width="50%">

### ✨ Add a feature to an existing project
**Start at PRD (feature mode), then build:**

```
📄 PRD  →  ✅ Checklist  →  🔨 Implement  →  🧪 Test
```

1. Run **PRD** and select "Feature / enhancement" scope
2. Run **Checklist** to break the feature into tasks
3. Run **Implement** to build it
4. Run **Test** to verify it works

> The PRD adapts — it asks feature-specific questions and generates a lighter doc focused on what the feature does, not the whole app.

</td>
</tr>
<tr>
<td width="50%">

### 🔧 Fix a bug or issue
**Jump straight to Fix:**

```
🔧 Fix  →  🧪 Test
```

1. Run **Fix** (or `/fix the button doesn't work`)
2. Run **Test** to verify the fix and check for regressions

> No planning needed. Fix diagnoses, patches, and verifies.

</td>
<td width="50%">

### 📌 Build a small task or component
**Lightweight PRD, then build:**

```
📄 PRD  →  🔨 Implement  →  🧪 Test
```

1. Run **PRD** and select "Small task" scope
2. Run **Implement** to build it
3. Run **Test** to verify

> Small task PRDs are minimal — just requirements, edge cases, and definition of done. No heavy planning needed.

</td>
</tr>
</table>

### 🔗 How Phases Chain Together

Each phase can trigger earlier phases if you haven't run them yet:

```
🔨 Implement  ─── "No checklist found. Want me to run Checklist first?" ───▶  ✅ Checklist
✅ Checklist   ─── "No PRD found. Want me to run PRD first?" ──────────────▶  📄 PRD
📄 PRD         ─── "No plan found. Want me to run Plan first?" ────────────▶  📋 Plan
```

> You can start at any phase. If earlier docs are missing, the phase offers to generate them — or you can skip and provide context directly.

---

## 🚀 How It Works

Two entry points — pick the one that fits your workflow:

<table>
<tr>
<td width="50%">

### 📋 A) Copy-Paste Prompts
**Zero setup. Just copy and paste.**

```
1️⃣  Open a file in prompts/
2️⃣  Copy the contents
3️⃣  Paste into Claude Code
4️⃣  Answer the onboarding questions
5️⃣  Follow the guided workflow
```

> 🟢 Best for: quick projects, one-off tasks, trying it out

</td>
<td width="50%">

### ⚡ B) Slash Commands
**Deep integration with Claude Code.**

```
1️⃣  Copy .claude/ into your project root
2️⃣  Fill in CLAUDE.md with your project details
3️⃣  Type /plan, /prd, /checklist, etc.
```

> 🔵 Best for: ongoing projects, teams, repeated workflows

</td>
</tr>
</table>

---

## 🔀 Not Sure Which to Pick?

| | 📋 Prompts (A) | ⚡ Slash Commands (B) |
|:--|:--|:--|
| **⏱️ Setup time** | None | 5 minutes |
| **▶️ How to run** | Copy-paste into Claude Code | Type `/plan`, `/prd`, etc. |
| **🧠 Project context** | Asks you every time | Reads from [`CLAUDE.md`](./CLAUDE.md) automatically |
| **📂 Codebase access** | No — can't scan files | Yes — scans project structure |
| **💬 Inline arguments** | No | Yes — e.g. `/fix the login is broken` |

> 💡 **Start with prompts. Move to slash commands when you want tighter integration.**

---

## 🔄 The Six Phases

Each phase builds on the last. Use them in order for a new project, or jump to the one you need.

```
  ┌──────────┐       ┌──────────┐       ┌──────────┐
  │ 📋 Plan  │ ────▶ │ 📄 PRD   │ ────▶ │ ✅ Check │
  │          │       │          │       │    list  │
  └──────────┘       └──────────┘       └──────────┘
                                              │
                                              ▼
  ┌──────────┐       ┌──────────┐       ┌──────────┐
  │ 🧪 Test  │ ◀──── │ 🔧 Fix   │ ◀──── │ 🔨 Impl  │
  │          │       │          │       │    ement │
  └──────────┘       └──────────┘       └──────────┘
```

### 📋 1. Plan
> `/plan` · [`prompts/01-plan.md`](./prompts/01-plan.md) · [`.claude/commands/plan.md`](./.claude/commands/plan.md)

Define what you're building, the architecture, and implementation phases. Produces a structured plan with scope, risks, and next steps.

### 📄 2. PRD
> `/prd` · [`prompts/02-prd.md`](./prompts/02-prd.md) · [`.claude/commands/prd.md`](./.claude/commands/prd.md)

Turn the plan into a Product Requirements Document — features, user stories, acceptance criteria, and technical requirements.

### ✅ 3. Checklist
> `/checklist` · [`prompts/03-checklist.md`](./prompts/03-checklist.md) · [`.claude/commands/checklist.md`](./.claude/commands/checklist.md)

Break the PRD into concrete, ordered tasks with checkboxes. Grouped by phase, ordered by dependency, decision points flagged.

### 🔨 4. Implement
> `/implement` · [`prompts/04-implement.md`](./prompts/04-implement.md) · [`.claude/commands/implement.md`](./.claude/commands/implement.md)

Write the code. Three modes:
- **🪜 Step-by-step** (default) — one task at a time, check in after each
- **🏗️ Full build** — complete a whole phase, check in at the end
- **🗺️ Plan only** — preview the approach without writing code

### 🔧 5. Fix
> `/fix` · [`prompts/05-fix.md`](./prompts/05-fix.md) · [`.claude/commands/fix.md`](./.claude/commands/fix.md)

Something broke? Diagnose the root cause, make the minimal fix, verify it works. No unnecessary refactoring.

### 🧪 6. Test
> `/test` · [`prompts/06-test.md`](./prompts/06-test.md) · [`.claude/commands/test.md`](./.claude/commands/test.md)

Validate the build. Generates a validation checklist, runs existing tests, walks through manual checks, and produces a test report.

---

## 📁 Project Structure

| File | Description |
|:--|:--|
| **⚡ Slash Commands** | |
| [`.claude/commands/plan.md`](./.claude/commands/plan.md) | 📋 Plan — scan codebase + generate plan |
| [`.claude/commands/prd.md`](./.claude/commands/prd.md) | 📄 PRD — generate requirements doc |
| [`.claude/commands/checklist.md`](./.claude/commands/checklist.md) | ✅ Checklist — break PRD into tasks |
| [`.claude/commands/implement.md`](./.claude/commands/implement.md) | 🔨 Implement — write the code |
| [`.claude/commands/fix.md`](./.claude/commands/fix.md) | 🔧 Fix — diagnose and fix bugs |
| [`.claude/commands/test.md`](./.claude/commands/test.md) | 🧪 Test — validate the build |
| **📋 Copy-Paste Prompts** | |
| [`prompts/01-plan.md`](./prompts/01-plan.md) | 📋 Plan — self-contained, asks onboarding questions |
| [`prompts/02-prd.md`](./prompts/02-prd.md) | 📄 PRD — standalone requirements generation |
| [`prompts/03-checklist.md`](./prompts/03-checklist.md) | ✅ Checklist — standalone task breakdown |
| [`prompts/04-implement.md`](./prompts/04-implement.md) | 🔨 Implement — standalone build mode |
| [`prompts/05-fix.md`](./prompts/05-fix.md) | 🔧 Fix — standalone bug fixing |
| [`prompts/06-test.md`](./prompts/06-test.md) | 🧪 Test — standalone validation |
| **🧩 Other Files** | |
| [`skills/vibe-coding.md`](./skills/vibe-coding.md) | 🧠 Core coding principles & behavior |
| [`examples/sample-prd.md`](./examples/sample-prd.md) | 📄 Example PRD (GitHub Activity Dashboard) |
| [`examples/sample-checklist.md`](./examples/sample-checklist.md) | ✅ Example checklist (matches the PRD) |
| [`CLAUDE.md`](./CLAUDE.md) | ⚙️ Project context template — fill this in |

---

## ⚙️ Setting Up CLAUDE.md

> 🔵 Only needed for Entry Point B (slash commands). Prompts work without it.

[`CLAUDE.md`](./CLAUDE.md) tells Claude Code about your project. Fill in what you can — you don't need everything on day one.

| Section | What to write | When to add |
|:--|:--|:--|
| 📝 **Overview** | What it does, who it's for | ⭐ Start here |
| 🛠️ **Tech Stack** | Language, framework, database, testing | ⭐ Start here |
| ▶️ **Key Commands** | install, dev, test, build, lint | ⭐ Start here |
| 🗂️ **Project Structure** | Top-level directory tree | 📌 When helpful |
| 📐 **Code Conventions** | Naming, patterns, file organization | 📌 When helpful |
| 🏗️ **Architecture Notes** | Data flow, key boundaries | 📌 When helpful |
| ⚠️ **Known Gotchas** | Things that trip people up | 🔄 Over time |
| 📊 **Current Status** | What works, what's in progress | 🔄 Update as you go |

---

## 📚 Examples

The [`examples/`](./examples) folder has a complete PRD and matching checklist for a fictional **GitHub Activity Dashboard** project:

| File | What it shows |
|:--|:--|
| 📄 [`sample-prd.md`](./examples/sample-prd.md) | Full PRD with features, user stories, acceptance criteria, and technical specs |
| ✅ [`sample-checklist.md`](./examples/sample-checklist.md) | Matching task checklist with a mix of completed and pending items |

Use them to:
- 👀 See what good output looks like from each phase
- 📏 Understand the level of detail the prompts produce
- 🧪 Try the prompts/commands without a real project

---

## 💡 Tips

| | Tip | Details |
|:--|:--|:--|
| 🎯 | **Jump to any phase** | Have a bug? Go straight to `/fix`. Know what to build? Skip to `/implement`. |
| 🔗 | **Phases chain together** | Slash commands save to `docs/` — the next phase picks up automatically. |
| ✏️ | **Prompts are editable** | They're just markdown. Add sections, change questions, adjust the tone. |
| 📈 | **CLAUDE.md grows with you** | Update it as the project evolves. Better context = better output. |
| ⚡ | **Use inline arguments** | `/fix the API returns 500 on empty input` is faster than answering questions. |

---

## 📄 License

MIT

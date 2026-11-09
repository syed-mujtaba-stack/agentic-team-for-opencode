# Sofwdocs-Agentic-Team — 31-Agent AI Product Team for OpenCode

> **By [Syed Mujtaba Abbas](https://syedmujtabaabbas.xyz)** · Portfolio: **<https://syedmujtabaabbas.xyz>**

[![OpenCode](https://img.shields.io/badge/OpenCode-ai%20agent%20team-blue)](https://opencode.ai)
[![Agents](https://img.shields.io/badge/agents-31-2ec27e)](#the-agent-team)
[![Phases](https://img.shields.io/badge/workflow-6%20phases-orange)](#how-the-workflow-runs)
[![Google Fonts](https://img.shields.io/badge/Google%20Fonts-1%2C959-b56bff)](#uiux-special-skill)
[![Theme pairs](https://img.shields.io/badge/light%2Fdark%20theme%20pairs-1%2C200-007A6C)](#uiux-special-skill)
[![Motion recipes](https://img.shields.io/badge/motion%20templates-12-ff9f43)](#motion-template-skill)

**Sofwdocs-Agentic-Team** is a production-ready, multi-agent template for
[OpenCode](https://opencode.ai). One command — `/team <task>` — turns a solo session
into a full 31-agent software team: a master orchestrator, 6 department heads, and
24 specialists who take a project from idea to launch through a gated workflow:

**Discovery → Architecture → Design → Development → Validation → Launch**

The template ships with two structured skills that give the team real design and
motion-engineering discipline instead of generic "make it pretty" output:

- **uiux-special** — prompt-driven UI/UX decisions backed by 1,959 real Google Fonts,
  360 curated pairings, 1,200 layout blueprints, and 1,200 WCAG-validated light/dark
  theme pairs.
- **motion-template** — production playbook for Framer Motion, GSAP, Three.js,
  React Three Fiber, Drei, and Lenis, with 82 curated libraries and 12 end-to-end
  template recipes.

---

## Table of contents

- [Why this template](#why-this-template)
- [What's inside](#whats-inside)
- [The agent team](#the-agent-team)
- [How the workflow runs](#how-the-workflow-runs)
- [uiux-special skill](#uiux-special-skill)
- [motion-template skill](#motion-template-skill)
- [Quick start](#quick-start)
- [Commands](#commands)
- [Agent brief protocol](#agent-brief-protocol)
- [Deliverables you get](#deliverables-you-get)
- [Quality guardrails](#quality-guardrails)
- [FAQ](#faq)
- [Keywords](#keywords)
- [About the author](#about-the-author)

---

## Why this template

Most "many agent" setups degrade into 10 copies of the same assistant. Sofwdocs-Agentic-Team
is built against the failure modes:

| Common failure | What this template does |
| --- | --- |
| All agents sound the same | Department structure, distinct scopes, explicit review contracts per specialist. |
| Agents forget the plan | Every agent writes a task brief under `.opencode/work/` and follows it. |
| Design becomes fetch-colors-from-vibes | Every visual decision cites real IDs from dataset files (font, pairing, layout, theme). |
| Motion/3D page runs slow on a phone | Static-first build, perf budgets, poster + reduced-motion + no-WebGL fallbacks enforced. |
| Tests become vibes | Each acceptance criterion is mapped to a test, then verified with evidence. |
| Too many `@framer-motion` and `gsap` duplicates | Selector script picks a minimal core stack per prompt and framework. |

---

## What's inside

```
.opencode/
├── agents/                      # 31 team agents (path-derived IDs)
│   ├── orchestrator.md          # master orchestrator (primary)
│   ├── heads/                   # 6 department heads
│   ├── product/                 # 4 product specialists
│   ├── design/                  # 4 design specialists
│   ├── engineering/             # 6 engineers
│   ├── qa/                      # 4 QA specialists
│   ├── devops/                  # 3 DevOps specialists
│   ├── growth/                  # 3 growth specialists
│   └── reviewer.md              # read-only reviewer agent
├── commands/
│   ├── team.md                  # /team — full 6-phase team workflow
│   ├── plan.md                  # /plan — plan-only, no code edits
│   ├── verify.md                # /verify — narrowest real checks
│   └── review.md                # /review — read-only review
└── skills/
    ├── dev-workflow/SKILL.md    # understand → explore → plan → implement → verify → report
    ├── task-brief/SKILL.md      # per-agent task brief protocol
    ├── uiux-special/SKILL.md    # design decision datasets + query tool
    └── motion-template/SKILL.md # motion/3D stack selection + recipes

AGENTS.md                        # working agreement, team roster, rules
opencode.jsonc                   # formatter, todo, subagent_depth: 2, safe permissions
```

---

## The agent team

**1 orchestrator + 6 department heads + 24 specialists = 31 team agents**, plus one
read-only `reviewer`. Depth is capped at **2** (`orchestrator → head → specialist`) so
specialists cannot spawn more agents.

| Department | Head | Specialists |
| --- | --- | --- |
| Product & Project | `heads/product-manager` | `product/business-analyst`, `product/project-manager`, `product/product-owner`, `product/technical-architect` |
| UI/UX & Design | `heads/design-director` | `design/ux-researcher`, `design/ui-designer`, `design/design-system-engineer`, `design/motion-designer` |
| Software Engineering | `heads/engineering-lead` | `engineering/frontend-engineer`, `engineering/backend-engineer`, `engineering/database-engineer`, `engineering/authentication-engineer`, `engineering/integration-engineer`, `engineering/performance-engineer` |
| Testing & Security | `heads/qa-lead` | `qa/functional-qa-engineer`, `qa/automation-test-engineer`, `qa/security-auditor`, `qa/accessibility-auditor` |
| DevOps & Delivery | `heads/devops-lead` | `devops/cicd-engineer`, `devops/cloud-engineer`, `devops/release-engineer` |
| Growth & SEO | `heads/growth-lead` | `growth/technical-seo-specialist`, `growth/content-strategist`, `growth/analytics-specialist` |

Every phase ends with the department head reviewing its specialists' output. Defects are
sent back to the owning specialist as a correction task. Final approval is a user gate.

---

## How the workflow runs

```
Discovery → Architecture → Design → Development → Validation → Launch
```

1. **Discovery** — `heads/product-manager`. Deliverable: requirements, PRD, task plan.
2. **Architecture** — `heads/engineering-lead`. Deliverable: architecture doc and API contracts.
3. **Design** — `heads/design-director`. Deliverable: design spec, design system, motion
   guidelines (recipe ID, scroll owner, 3D scene contract).
4. **Development** — `heads/engineering-lead`. Deliverable: working, integrated
   application built from a `motion-template` recipe, with fallbacks and measured budgets.
5. **Validation** — `heads/qa-lead`. Deliverable: test plan + report, security audit,
   accessibility report.
6. **Launch** — `heads/devops-lead` and `heads/growth-lead`. Deliverable: deployment
   plan and SEO/analytics plan.

The orchestrator shows a gate summary after each phase and waits for user approval
before starting the next one. `/team <task>` keeps the human in control.

---

## uiux-special skill

A prompt-driven design decision system for the design department. It does not impose
one style: it reads your prompt, queries the datasets for relevant candidates, records
a **Design Decision Record** at `.opencode/work/<task-slug>/design-ddr.md`, and implements
the recorded choice.

| Asset | Count |
| --- | --- |
| Real Google Fonts | **1,959** (1,838 Latin, 565 variable) |
| Curated font pairings | **360** |
| Layout blueprints | **1,200** (40 page types × 6 families × 5 hero patterns) |
| Theme pairs | **1,200** (each = light + dark, so 2,400 mode variants) |
| Motion/3D scenes | 10 GSAP + 10 Three.js reference scenes |

Contrast is validated: **body text ≥ 7:1**, **muted text ≥ 4.5:1**, **accent text ≥ 4.5:1**,
and **UI boundaries/focus ≥ 3:1** (WCAG AA and above across both modes). Only
**light and dark** modes exist — no "third mode", no intermediate auto theme.

Query the datasets (never dumps them into context):

```bash
node .opencode/skills/uiux-special/scripts/query.mjs fonts --category "Sans Serif" --tag ui --limit 10
node .opencode/skills/uiux-special/scripts/query.mjs layouts --page property-detail --fit 4 --limit 8
node .opencode/skills/uiux-special/scripts/query.mjs themes --best-for property-management --strategy warm-neutral --limit 8
# Re-validate the datasets any time they change:
node .opencode/skills/uiux-special/scripts/validate.mjs
```

---

## motion-template skill

Design-with-implementation-strategy sibling to uiux-special: it turns the chosen design
into a production template for **Framer Motion** (`motion`), **GSAP**, **Three.js**,
**React Three Fiber**, **Drei**, and **Lenis** — with supporting libraries.

| Asset | Count |
| --- | --- |
| Curated libraries | **82** packages across 21 categories (status, weight, SSR, framework) |
| Template recipes | **12** end-to-end blueprints: `MT-01` … `MT-12` |
| Reference guides | 9 docs: stack matrix, Motion, Three.js/R3F, GSAP/Lenis, architecture, performance, checklist |
| Frameworks supported | Next.js, Vite (React), Astro, Nuxt (Vue), SvelteKit (Svelte) |

Prompt-driven stack selection:

```bash
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework nextjs --goal marketing --3d yes --scroll cinematic
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework astro --goal editorial --scroll cinematic
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework nextjs --goal dashboard --charts yes --json
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework nuxt --goal property --3d yes --json
```

Self-verify the skill contents (catalog, links, code fences, recipe cross-check, and script
syntax) any time you edit it:

```bash
node .opencode/skills/motion-template/scripts/check-skill.mjs
```

### Non-negotiable production rules

1. **Static-first** — the page works with JS and WebGL disabled.
2. **One animation owner per element** — Motion for UI state, GSAP for scroll timelines,
   CSS for hover/focus. Never both owners on the same property.
3. **One scroll owner per page** — native scroll, Motion `useScroll`, or GSAP
   ScrollTrigger. Lenis is a transport layer, not a second scroll system.
4. **No 3D without a contract** — every scene ships a static poster, a reduced-motion
   static state, an offscreen/hidden pause, and a no-WebGL fallback.
5. **Budget before adding** — LCP, INP, CLS, initial JS, 3D chunk size, DPR, draw calls,
   and texture budget are written down and measured before/after.

---

## Quick start

**Prerequisites:** [Node.js 20+](https://nodejs.org) and [OpenCode](https://opencode.ai)
installed.

```bash
# 1) Add the template to any project folder
git clone https://github.com/syed-mujtaba-stack/agentic-team-for-opencode.git
cp -r agentic-team-for-opencode/.opencode .opencode
cp agentic-team-for-opencode/AGENTS.md agentic-team-for-opencode/opencode.jsonc .

# 2) Open OpenCode inside your target project
opencode

# 3) Run the full team workflow
> /team Create a premium Next.js website for a US property management company
```

For a quick, small task, use the default `build` agent. For a full product run, use
`/team <task>` or select the `orchestrator` agent.

---

## Commands

| Command | Purpose |
| --- | --- |
| `/team <task>` | Runs the whole 6-phase agentic workflow with gated phase approvals. |
| `/plan <task>` | Plan-only. Explore the codebase and produce a plan; no edits. |
| `/verify` | Runs the narrowest real checks (typecheck/lint/build/test) and reports pass/fail. |
| `/review` | Read-only review of the current diff or task. |

Other prompts the orchestrator handles well:

```
/team Build a cinematic product landing page with a 3D hero
/team Build a property listing marketplace with filters and detail pages
/team Build an editorial blog on Astro with subtle motion
/team Build a SvelteKit analytics dashboard with charts
```

---

## Agent brief protocol

Before doing any work, every agent writes a task-specific brief under:

```text
.opencode/work/<task-slug>/<role>.md
```

The brief contains the objective, inputs, steps, deliverables, and acceptance checks.
The agent then follows that brief and cites its path in the final report. `.opencode/work/`
is git-ignored, so scratch artifacts never pollute your repo.

---

## Deliverables you get

Every `/team` run produces working code **and** structured documentation:

| Path | Content |
| --- | --- |
| `docs/product/` | Requirements, PRD, task plan |
| `docs/architecture/` | Architecture, API contracts, implementation notes |
| `docs/design/` | UX research, design spec, design system, motion guidelines, cited design decisions |
| `docs/engineering/` | Performance report with before/after measurements |
| `docs/qa/` | Test plan + report, security audit, accessibility report |
| `docs/devops/` | Infrastructure, deployment, release plan |
| `docs/growth/` | SEO plan, content map, analytics plan |

---

## Quality guardrails

- **No code without evidence.** Agents must run real checks (typecheck, lint, build,
  tests) and report the commands and results — a failing check is unfinished work, not a note.
- **No unapproved dependencies or tooling changes.**
- **No secrets in code or config.** Use environment variables, and `{env:NAME}` in OpenCode config.
- **Destructive commands ask first.** `git push`, `git reset --hard`, and recursive deletes
  require approval.
- **Read-only heads.** Department heads review but only write to `.opencode/work/`.
- **Dataset-driven design.** No invented palettes, pairings, or layouts when matching
  options exist in `uiux-special`.
- **No scene without a fallback.** 3D ships with poster, reduced-motion, no-WebGL,
  and paused-when-hidden behavior.

---

## FAQ

Frequently asked structural questions, answered directly for clarity and for
generative-engine discoverability.

### What is Sofwdocs-Agentic-Team?

It is a multi-agent template for
[OpenCode](https://opencode.ai). It defines a 31-agent software team (orchestrator,
6 department heads, 24 specialists) plus two data-driven skills for design and motion
engineering. It is configuration and documentation, not an app — OpenCode loads it
automatically from your project's `.opencode/` folder.

### Do I need the paid OpenCode plan?

No. OpenCode is open source and supports many model providers through its config. This
template does not depend on a specific model — any capable chat model can power the team.

### Does this build production apps, or only mockups?

Production apps. Specialists implement minimal complete changes, verify with real
commands (typecheck, lint, tests, build), and the QA department validates acceptance
criteria against the running app — not against assumptions.

### What frontend frameworks does it cover?

Next.js (primary), plus Vite/React, Astro, Nuxt/Vue, and SvelteKit. The
`motion-template` skill adapts the stack (Motion, GSAP, Three.js/R3F, Lenis,
TresJS, Threlte) to the framework, page goal, scroll mode, 3D need, and bundle target.

### Can I add or remove agents?

Yes. Agents are simple Markdown files at `.opencode/agents/**`. Agent IDs are derived
from the file path (e.g. `.opencode/agents/design/ui-designer.md` → `design/ui-designer`).
Keep the department-head pattern if you want the review-gate workflow to stay intact.

### Can I use just one skill without the full team?

Yes. `uiux-special` and `motion-template` are standalone skills. You can call them from
your own agents or use OpenCode's skill detection — no team launch is required.

### Does it keep the work consistent across sessions?

The working agreement lives in `AGENTS.md`, loaders are defined in `opencode.jsonc`,
and each agent writes a task brief under `.opencode/work/`. Design changes are recorded
in a design decision record `.opencode/work/<task-slug>/design-ddr.md`, and final
code/spec documentation lands under `docs/`; nothing relies on in-session memory alone.

---

## Keywords

`agentic team` · `multi-agent AI workflow` · `OpenCode agents` · `OpenCode skills` ·
`AI software team` · `AI product team template` · `6-phase product workflow` ·
`PRD generator` · `design system generator` · `WCAG light dark themes` ·
`Framer Motion templates` · `GSAP ScrollTrigger recipe` · `Three.js React Three Fiber` ·
`Lenis smooth scroll` · `Next.js template engineering` · `Astro motion` ·
`Nuxt TresJS` · `SvelteKit Threlte` · `web performance budgets` ·
`Core Web Vitals` · `repository-of-agents` · `Sofwdocs` · `Syed Mujtaba Abbas`

---

## About the author

**Syed Mujtaba Abbas** 🇵🇰 · Full-stack developer & AI workflow builder

[![Portfolio](https://img.shields.io/badge/Portfolio-syedmujtabaabbas.xyz-0a0a0a?logo=aboutdotme&logoColor=white)](https://syedmujtabaabbas.xyz)
[![GitHub](https://img.shields.io/badge/GitHub-syed--mujtaba--stack-181717?logo=github&logoColor=white)](https://github.com/syed-mujtaba-stack)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mjsyed/)
[![Instagram](https://img.shields.io/badge/Instagram-m.j__syed-E4405F?logo=instagram&logoColor=white)](https://www.instagram.com/m.j_syed/)
[![Facebook](https://img.shields.io/badge/Facebook-Follow-1877F2?logo=facebook&logoColor=white)](https://www.facebook.com/profile.php?id=61557499523385)
[![WhatsApp](https://img.shields.io/badge/WhatsApp-Message-25D366?logo=whatsapp&logoColor=white)](https://wa.me/923460630802)
[![Email](https://img.shields.io/badge/Email-Say%20Hi-D14836?logo=gmail&logoColor=white)](mailto:abbasmujtaba125@gmail.com)

| Channel | Link |
| --- | --- |
| 🌐 Portfolio | <https://syedmujtabaabbas.xyz> |
| 🐙 GitHub | <https://github.com/syed-mujtaba-stack> |
| 💼 LinkedIn | <https://www.linkedin.com/in/mjsyed/> |
| 📸 Instagram | <https://www.instagram.com/m.j_syed/> |
| 👍 Facebook | <https://www.facebook.com/profile.php?id=61557499523385> |
| 💬 WhatsApp | <https://wa.me/923460630802> |
| ✉️ Email | <mailto:abbasmujtaba125@gmail.com> |

## ⭐ Support the project

If this agentic team template saves you time on your next build, please give it a star — it helps other developers discover free, production-grade agent workflows.

[![GitHub Repo stars](https://img.shields.io/github/stars/syed-mujtaba-stack/agentic-team-for-opencode?style=social&logo=github)](https://github.com/syed-mujtaba-stack/agentic-team-for-opencode/stargazers)

**Star the repo:** [github.com/syed-mujtaba-stack/agentic-team-for-opencode/stargazers](https://github.com/syed-mujtaba-stack/agentic-team-for-opencode/stargazers)

---

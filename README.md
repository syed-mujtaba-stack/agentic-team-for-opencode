# propergygurd — starter workflow + 31-agent AI team

Ye repository abhi khali hai, lekin OpenCode ke liye poora workflow aur ek 31-agent
AI team set up hai. Har agent ek hi discipline follow karta hai: task brief banao →
kaam karo → verify karo → evidence ke saath report karo.

## Core workflow files

| File | Kaam |
| --- | --- |
| `AGENTS.md` | Working agreement, AI team roster, deliverable paths, safety rules. |
| `opencode.jsonc` | Formatter, todo tool, `subagent_depth: 2`, aur destructive commands ke liye `ask`. |
| `.opencode/skills/dev-workflow/SKILL.md` | Understand → explore → plan → implement → verify → report. |
| `.opencode/skills/task-brief/SKILL.md` | Har task par apni task-specific brief/skill likhne ka protocol. |
| `.opencode/skills/uiux-special/SKILL.md` | Prompt-driven UI/UX system: 1,959 fonts, 1,200 layouts, 1,200 light/dark themes, GSAP + Three.js scenes. |
| `.opencode/skills/motion-template/SKILL.md` | Production motion/3D template engineering: Motion, GSAP, Three.js, R3F, Lenis, 82 libraries, 12 recipes. |
| `.opencode/commands/plan.md` | `/plan <task>` — sirf plan, koi edit nahi. |
| `.opencode/commands/verify.md` | `/verify` — narrowest checks aur result. |
| `.opencode/commands/review.md` | `/review` — read-only review. |
| `.opencode/commands/team.md` | `/team <task>` — poora 6-phase team workflow. |
| `.opencode/agents/reviewer.md` | Simple read-only reviewer. |

## AI team — 31 agents

1 orchestrator + 6 department heads + 24 specialists = 31 team agents.
Iske ilawa 1 utility `reviewer` agent bhi hai jo `/review` command use karta hai.

| Department | Head | Specialists |
| --- | --- | --- |
| Product & Project Management | `heads/product-manager` | Business Analyst, Project Manager, Product Owner, Technical Architect |
| UI/UX & Design | `heads/design-director` | UX Researcher, UI Designer, Design System Engineer, Motion Designer |
| Software Engineering | `heads/engineering-lead` | Frontend, Backend, Database, Authentication, Integration, Performance Engineer |
| Testing & Security | `heads/qa-lead` | Functional QA, Automation Test, Security Auditor, Accessibility Auditor |
| DevOps & Delivery | `heads/devops-lead` | CI/CD Engineer, Cloud Engineer, Release Engineer |
| Growth & SEO | `heads/growth-lead` | Technical SEO Specialist, Content Strategist, Analytics Specialist |

Agent IDs path se bante hain, e.g. `product/business-analyst`, `heads/qa-lead`.

## UI/UX Special skill

Design team ke liye ek dedicated skill hai:

```text
.opencode/skills/uiux-special/
```

Is mein sirf theory nahi, real generated datasets hain:

| Asset | Count |
| --- | --- |
| Real Google Fonts | 1,959 (1,838 Latin, 565 variable) |
| Curated font pairings | 360 |
| Layout blueprints | 1,200 (40 page types, 12 families, 12 hero patterns; 6 families × 5 heroes per page) |
| Theme pairs | 1,200 (har pair light + dark, WCAG-validated) |
| Motion recipes | 10 GSAP + 10 Three.js scenes |

Sirf **light aur dark** modes hain. Har theme pair ka body text 7:1, muted text 4.5:1,
aur accent text 4.5:1 contrast pass karta hai.

UI designer prompt padh kar query tool se sirf relevant options nikalta hai:

```text
node .opencode/skills/uiux-special/scripts/query.mjs fonts --category "Sans Serif" --tag ui --limit 10
node .opencode/skills/uiux-special/scripts/query.mjs layouts --page property-detail --fit 4 --limit 8
node .opencode/skills/uiux-special/scripts/query.mjs themes --best-for property-management --strategy warm-neutral --limit 8
```

Phir `.opencode/work/<task-slug>/design-ddr.md` mein Design Decision Record likhta hai
(font IDs, pairing, layout blueprint, theme, motion) aur usi ke mutabiq implement karta
hai. Design spec, design system, aur motion guidelines sab chosen IDs cite karte hain.

Datasets dobara generate ya verify karne ke liye:

```text
node .opencode/skills/uiux-special/scripts/validate.mjs
```

## Motion Template skill

`uiux-special` design decide karta hai. Us design ko production template mein implement
karne ke liye dedicated skill hai:

```text
.opencode/skills/motion-template/
```

Is mein Framer Motion (ab `motion`), GSAP, Three.js, React Three Fiber, Drei, Lenis aur
supporting libraries ke liye complete playbook hai:

| Asset | Count |
| --- | --- |
| Curated libraries | 82 packages, status aur caveats ke saath |
| Template recipes | 12 (`MT-01` ... `MT-12`) |
| Reference guides | stack matrix, Motion, Three.js/R3F, GSAP/Lenis, architecture, performance, checklist |

Prompt ke mutabiq stack select karne ke liye:

```text
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework nextjs --goal marketing --3d yes --scroll cinematic
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework astro --goal editorial --scroll cinematic
node .opencode/skills/motion-template/scripts/select-stack.mjs --framework nextjs --goal dashboard --charts yes --json
```

Skill khud verify hoti hai:

```text
node .opencode/skills/motion-template/scripts/check-skill.mjs
```

Rules: static-first, one animation owner per element, one scroll owner, no 3D without a
poster + reduced-motion + no-WebGL fallback, aur performance budget ke baghair scene ship
nahi hota.

## Kaise chalta hai

```text
Discovery → Architecture → Design → Development → Validation → Launch
```

- Orchestrator har phase department head ko deta hai.
- Head apne specialists ko tasks deta hai, output review karta hai, defect wapas
  usi specialist ko correction task ke tor par bhejta hai.
- Har phase ke baad user ko gate summary milti hai; approval ke baad next phase.
- Delegation depth 2 hai (orchestrator → head → specialist), is liye head worker
  bula sakta hai lekin worker aage agent nahi bana sakta.

## Task brief protocol

Har agent kaam shuru karne se pehle apni task-specific skill likhta hai:

```text
.opencode/work/<task-slug>/<role>.md
```

Us mein objective, inputs, steps, deliverables, aur acceptance checks hote hain.
Agent usi brief ko follow karta hai aur final message mein uska path deta hai.
`.opencode/work/` git-ignored hai.

## Usage

```text
/team Create a premium Next.js website for a US property management company

/plan add authentication
/verify
/review
```

Chhote kaam ke liye normal `build` agent use karein; bade projects ke liye `/team`
ya `orchestrator` agent select karein.

## Deliverables

- `docs/product/` — requirements, PRD, task plan
- `docs/architecture/` — architecture, API contracts, implementation notes
- `docs/design/` — UX research, design spec, design system, motion, cited design decisions
- `docs/qa/` — test plan/report, security audit, accessibility report
- `docs/devops/` — infrastructure, deployment, release plan
- `docs/growth/` — SEO plan, content map, analytics plan

## Next step

Jab stack choose ho jaye, `AGENTS.md` ke **Repository map** section mein install, dev,
test, lint, aur build commands bhar dein — phir team ke `/verify` aur engineers ko
pata hoga ke exactly kya chalana hai.

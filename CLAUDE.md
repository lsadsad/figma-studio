# CLAUDE.md — Throughline × Figma

Operating-layer instructions for Claude Code when working on Throughline design artifacts in Figma via figma-console-mcp. Read on every session start.

**What Throughline is:** a design-evaluation methodology for AT&T's mobile app team. The thesis is that design *is* connection — every screen either creates connection or extracts. Throughline is the lens for telling which.

**What Throughline is not:** a style guide, a component library, or a process to roll out. The component library is the **AT&T Relay Design System** — always written in full. Never shorten to "Relay" alone; that name was Throughline's earlier working title and the collision is live.

---

## The anchoring question

> **Does this create connection, or does it extract?**

Asked at every level, on every shipped decision. Everything else is commentary.

Domain-bound by design: AT&T mobile app, consumer-facing, contractual stakes, hierarchical relationship. Outside that domain the question goes thin — feature, not flaw.

---

## The three pillars

Every screen reads through three lenses. When all three hold, connection lands. When any one is missing, the work drifts toward extraction.

### Language — every word points to an outcome, not an obligation
- ✅ "Deals unlock at 33%"
- ❌ "Your minimum payment threshold is $300"

### Signal — every signal element earns its meaning
Across visual, motion, auditory, haptic. A refresh icon *outlined* in the gauge vs. *filled* in the strip carries semantic difference, not decoration. Cross-modal congruence operates inside a ~100ms binding window — bundle sonic / haptic / motion / color cues that tightly or they read as separate events.

### Trust — every constraint is surfaced, not hidden
The trade-in requirement appears on the Nibble Card — not buried in Terms & Conditions.

---

## Critique mode — the Dual Read

When evaluating any Figma frame, run both reads. Both must hold. When they disagree, the disagreement is data — surface it, don't smooth it.

### Cross-Map read — is the craft sound?
Pillars × craft dependencies × accessibility. Four checks:
- **Temporal order** — does the sequence of reveals match the user's decision sequence?
- **Redundant encoding** — is critical info carried in at least two channels (color + shape, position + label)?
- **Historical precedent** — does this echo a form that's already working, or invent without reason?
- **Cognitive limits** — does the screen respect working-memory capacity at the moment of decision?

### Play Audit read — did this land as connection?
Eight dimensions:
1. **Voluntariness** — can the user meaningfully decline, exit, reshape, revisit without penalty?
2. **Frame clarity** — does the interface signal "exploration" vs. "consequence"?
3. **Meaningful choice** — do user actions produce *perceptible* and *integrated* effects?
4. **Lusory attitude invited** — does constraint enrich or strip?
5. **Scaffolded agency** — does structure preserve agency (guided) or remove it (forced funnel)?
6. **SDT nourishment** — does the interaction feed autonomy / competence / relatedness, or substitute badges and streaks?
7. **Grokkability** — is the user still learning, or has the interface stopped teaching?
8. **Back-talk** — does the material respond to user moves in a way that invites further moves?

Verb form: "Let's dual-read this." / "The dual-read turned up a trust gap."

---

## Connection failure patterns to flag

First-class vocabulary. When critiquing, name them by name.

- **Hidden Terms** — constraints buried where users won't see them until it's too late. *Trust* violation.
- **False Hierarchy** — visual prominence doesn't match semantic importance. *Signal* violation.
- **Promise Gap** — copy promises something the system can't or won't deliver. *Language* violation.
- **Decision Orphan** — user asked to decide without the information needed to decide well. *Trust + Language*.
- **Trust Erosion** — small, repeated breaks of expectation compounding across sessions. Cross-pillar.

---

## Create mode — working vocabulary

The current proof-of-concept is the **Nibble Card** — installment progress for AT&T's device payment plans. The vocabulary below is shipping language, not draft.

| Term | Role |
|---|---|
| **Nibble Card** | Always-visible entry point in the Services scroll. Self-contained 2-second scan. |
| **Fuel Gauge** | Horizontal progress bar with milestone markers. **Data layer** — measures, shows. |
| **Signal Strip** | Translates gauge state into actionable message. **Communication layer** — interprets, speaks. |
| **Decision Space** | Bottom sheet modal opened by Signal Strip tap. Holds Bite + Chew layers. *Action* context, not *info* context. |
| **Refresh Icon** | *Outlined* (gauge) = waypoint. *Filled* (strip) = destination. Communicates the cycle / trade-in mechanic. |
| **Nibble → Bite → Chew** | Progressive disclosure. Match information density to user intent at each layer. |

**Architectural rule: the gauge shows; the Signal Strip speaks.** Data layers measure. Communication layers interpret. Each layer owns its content without overlap — no dollar amount in both card body and strip.

### Signal Strip copy registers
Five contextual registers. Pick the one matching user intent:

1. **Outcome** — "$96 to unlock upgrade deals"
2. **Math** — "27 mo = $900 / 3 mo = $100"
3. **Momentum** — "You're 3 payments away"
4. **Agency** — "Switch any time after $396"
5. **Cycle** — "3 payments from a fresh start"

### Information vs. Decision separation
- *Inline expand* = reference context (cost breakdown, where am I?)
- *Bottom sheet modal* = decision context (options, what can I do?)
- The disclosure mechanism signals the nature of the content. Don't blur this.

---

## Standing constraints

### 4pt grid — non-negotiable
Every dimension snaps to a multiple of 4. Heights, widths, padding, spacing, icon containers, touch targets.

| Element | ❌ | ✅ |
|---|---|---|
| Signal Strip height | 62px | 64px |
| Icon container | 30px | 32px |
| Card padding | 18px | 20px |
| Touch target | 42px | 44px |

If a Figma value isn't divisible by 4, fix it or flag it. No exceptions for "it looks better" — find the right multiple.

### Iteration sequence — never skip
ASCII mockup → HTML interactive diagram → Figma-ready spec → Rive build.

If asked to jump straight to Figma without an ASCII or HTML pass first, push back. Lower-fidelity passes catch decisions that hide inside high-fidelity polish.

### Decision discipline
- Every decision worth keeping gets a **DD-NNN** entry in Notion (Design Decisions DB) with: Decision, Rationale, Pillar, Affected Components, Resolved Audit Gap, Status.
- Every new noun gets a **Throughline Vocabulary** entry before reuse.
- No silent decisions. If a Figma comp embodies a decision, name it.

---

## The Sicart Rule — non-negotiable

> Throughline produces contexts that invite appropriation. It does not require behaviors.

What this means for Claude Code in Figma:

- ✅ Critique a frame against the pillars when asked.
- ✅ Generate Figma work that holds the pillars.
- ✅ Surface failure patterns when they appear.
- ❌ Do not invent metrics on framework activity (audit count, DD count, "compliance score").
- ❌ Do not produce checklists that turn the methodology into a gate.
- ❌ Do not score frames on a 1–5 pillar rubric. The point is the question, not the number.

When asked "how do we know this is working?" — the answer is never a count. It's *"the trade-in disclosure is no longer buried."*

---

## Naming hygiene

| Right | Wrong |
|---|---|
| **Throughline** | "the framework," "the methodology" — use the name |
| **AT&T Relay Design System** (full) | "Relay" alone (collides with Throughline's old name) |
| **Connection vs. Transaction** | "Good UX vs. bad UX" |
| *"Does this create connection or extract?"* | *"Is this on-brand?"* |

Historical artifacts in old Notion DDs that say "Relay" referring to the methodology are left as-is — don't rewrite history. New work uses Throughline.

---

## Working with figma-console-mcp

**Reading a frame:**
- Pull the frame, its variables, and its component instances in one diagnostic pass before commenting.
- Identify which named component (Nibble Card, Signal Strip, Fuel Gauge, Decision Space) the frame *is* or *contains*. If none, name what it's adjacent to.
- Run the Dual Read before suggesting changes.

**Writing to a frame:**
- Confirm the change is reversible or has a stated rollback before applying.
- Snap every new value to the 4pt grid.
- Match existing variable tokens. Don't invent new ones unless explicitly asked.
- For any structural move (renaming a component, restructuring a layer hierarchy), confirm in chat before executing.

**When the file disagrees with the methodology:**
- Don't silently "correct" the file. Flag the disagreement, name which pillar is implicated, propose the fix, wait for confirmation.

---

## When in doubt

- **Additive, not corrective.** Throughline evaluates whether existing UI / UX principles land. It does not compete with them.
- **Lives inside existing feature windows.** Don't propose new processes or rituals. Propose tighter shifts inside the windows already shipping.
- **Don't seed ahead of need.** Empty placeholder structures resist substrate. Lived material earns its place — components, variables, and patterns prove themselves through real work, not completionism.
- If a proposal turns framework activity into a metric, push back hard.
- If naming is unclear, ask. Don't ship a comp with a placeholder name that quietly becomes load-bearing.
- If the question on the surface seems thin, ask what spurred it before deploying a framework response.

---

*Throughline is methodology. The AT&T Relay Design System is the component library. Different organs — don't collapse them.*

# Figma Console MCP

The most comprehensive MCP server for Figma — design tokens, components, variables, and programmatic design creation.

## Build & Test

```bash
npm run build          # Compiles local + cloudflare + apps
npm run build:local    # Local mode only (use if Cloudflare types fail)
npm test               # Jest test suite
npx tsc --noEmit       # Type-check (pre-existing errors in src/apps/*/ui/mcp-app.ts are expected)
```

## Release Process

Before any release, read `.notes/RELEASING.md` and follow all five phases. Run `scripts/release.sh` for automated version/count updates before manual content edits.

## Known Issues

- **Cloudflare build type error**: `src/index.ts` line ~54 Env type mismatch is pre-existing on main. Does not affect runtime.
- **npm publish**: Use `npm publish --ignore-scripts` if prepublishOnly triggers a build failure.
- **Pre-existing tsc errors**: `src/apps/*/ui/mcp-app.ts` DOM type errors are expected (separate tsconfig files).

## Architecture

- Entry points: `src/local.ts` (local/NPX mode), `src/index.ts` (Cloudflare Workers)
- Tool registration: `registerXxxTools(server, getFigmaAPI, ...)` pattern in `src/tools/`
- Desktop Bridge: WebSocket (`src/core/websocket-server.ts`) with CDP fallback
- Schema compatibility: No `z.any()` — Gemini requires strictly typed Zod schemas

## finePrint — Issue Tracking (`.issues/`)

Issues are plain markdown files with YAML frontmatter, tracked in git. No external tools needed.

```
.issues/
  open/       # active issues
  closed/     # completed issues
```

### Frontmatter schema

```yaml
---
id: abc              # short mnemonic ID (3 chars; 4 for epics)
alias: my-feature    # optional readable name for conversational use
category: feature    # feature area (project-specific)
title: "..."
type: task|feature|bug|epic
priority: 1          # 0=critical, 1=high, 2=medium, 3=low, 4=backlog
status: open
depends_on: []       # list of IDs this issue is blocked by
created: 2026-03-28
---
```

### Conventions

- File naming: `P{priority}-{category}-{id}-{slug}.md` (e.g., `P2-feature-abc-my-feature.md`)
- To close an issue: `git mv .issues/open/P2-feature-abc-*.md .issues/closed/`
- To find ready work: issues in `open/` with empty `depends_on` or all deps in `closed/`
- Dependencies reference other issue IDs (check `depends_on` arrays)
- IDs must be globally unique within the project
- Obsidian-compatible: open `.issues/` as a vault, use Dataview for queries

### Trigger phrases

| Shortcut | Natural language | Action |
|---|---|---|
| `/issues` | "what's open" | List all open issues |
| `/ready` | "what's ready", "what should I work on" | Show unblocked issues only |
| `/issue X` | "show issue X" | Read a specific issue |
| `/track X` | "create an issue for X", "track this" | Write new `.issues/open/P{n}-{category}-{id}-{slug}.md` |
| `/close X` | "close X", "mark X done" | `git mv .issues/open/... .issues/closed/` |

## finePrint — Project Memory (`.memory/`)

Append-only knowledge base for decisions, context, and open questions.

### Format

Files are named `YYYY-MM-DD-slug.md` and contain free-form markdown. Content should be self-contained and dateable.

### Trigger phrases

| Shortcut | Natural language | Action |
|---|---|---|
| `/memory` | "check memory" | List all memory entries |
| `/recall X` | "what do we know about X" | Grep `.memory/` for topic |
| `/remember` | "remember this", "save to memory" | Write new `.memory/YYYY-MM-DD-slug.md` |
| `/supersede X` | "this replaces the decision on X" | New entry with "Supersedes:" reference |

## Session Completion

**When ending a work session**, you MUST complete ALL steps below.

1. **File issues** for remaining work (create new `.issues/open/*.md` files)
2. **Run quality gates** (if code changed) — tests, linters, builds
3. **Update issue status** — move completed issues to `closed/`
4. **PUSH TO REMOTE**:
   ```bash
   git pull --rebase
   git push
   git status  # MUST show "up to date with origin"
   ```
5. **Verify** — all changes committed AND pushed

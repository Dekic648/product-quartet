# Product Ensemble

Product Ensemble is a complete product design workflow for your coding agents, built on composable "skills" that make sure your agent doesn't just jump into building — it thinks through the experience, the scope, the strategy, the technical risks, the implementation plan, and the quality first.

## The Agents

### Soft Launch (Core 5)

| Agent | Role | Runs | Output |
|-------|------|------|--------|
| **UX Designer** | Defines the user experience — flows, interactions, friction, IA | 1st (leads) | UX Brief |
| **Product Manager** | Shapes UX into buildable spec — scope, stories, acceptance criteria | 2nd | Annotated Product Spec |
| **CPO / Strategist** | Validates strategic fit — vision, positioning, timing, opportunity cost | 3rd | Strategic Assessment |
| **Lead Engineer** | Flags technical risks — architecture gaps, security, scalability | 4th | Technical Advisory |
| **Roadmap Strategist** | Synthesizes all artifacts into a prioritized implementation plan | 5th (last) | Prioritized Implementation Roadmap |

### Quality (Post-Build)

| Agent | Role | Runs | Output |
|-------|------|------|--------|
| **User Tester** | Simulates 6 real users walking through actual code paths — finds what breaks, confuses, or dead-ends | After building, before shipping | User Test Report |

### Full Launch (3 Specialists)

| Agent | Role | Runs | Output |
|-------|------|------|--------|
| **Safety & Compliance** | Reviews regulatory, safety, accessibility, and compliance requirements | After core re-evaluation | Safety & Compliance Review |
| **Research Advisor** | Validates feasibility of expanded capabilities at required quality bar | After safety review | Feasibility Assessment |
| **GTM Strategist** | Defines pricing, distribution, launch planning, and documentation strategy | After research check | Go-to-Market Strategy |

## How It Works

It starts the moment you describe what you want to build. Instead of jumping straight into code, your agent steps back and thinks through the product.

The **UX Designer** goes first — asking what the user actually does, step by step, where they'll get confused, and what the happy path looks like. Once you've signed off on the experience, the **Product Manager** takes that vision and draws the line between what's in and what's out. Scope, user stories, acceptance criteria — the stuff that turns a good idea into a buildable spec.

Then the **CPO** weighs in at the strategic level: is this the right bet? Does it serve the long-term vision? They issue a verdict — GO, REDIRECT, DEFER, or KILL. If they redirect, the PM revises and the CPO re-evaluates. The orchestrator handles this loop automatically (max 3 iterations).

Then the **Lead Engineer** reviews what everyone agreed on and flags technical risks — missing error recovery, no caching strategy, privacy gaps, vendor lock-in — each rated by severity. Advisory only.

The **Roadmap Strategist** takes everything the team has produced and synthesizes it into a prioritized implementation roadmap — phases, dependencies, effort sizing, and sequencing rationale. The first phase always delivers a closed loop of user value. Technical risks get front-loaded. Deferred items get explicit activation triggers.

After you build, the **User Tester** walks through the actual code as 6 different personas — a first-time visitor, a rushing consultant, a non-technical user, a power user, a report builder, and a mobile user. Each attempts their task by tracing real code paths, and reports every issue with file paths and line numbers. This catches what specs miss: broken handlers, empty states, dead-end flows, and friction that only surfaces when someone actually uses the product.

You approve after every agent. Nothing advances without your sign-off. Agents are expected to challenge each other's decisions — constructive tension is built into the process.

## Soft Launch First, Always

Every ensemble session produces a **Soft Launch** plan — a complete, shippable V1 designed to validate your core thesis with real users. It's not a prototype. It's a finished product, scoped tightly.

Once you've shipped V1 and collected real-world feedback, you can expand into a **Full Launch** — adding safety review, research validation, go-to-market strategy, and data-driven iteration.

You don't need Full Launch to ship. You need it to scale.

## Domain Configuration

Drop a `domain.md` file in your project root to make every agent smarter about your specific product. It injects company context — user personas, tech stack, regulatory requirements, competitive landscape, and product principles — into every agent's thinking. Without it, agents operate as generalists. With it, they think in your domain.

## Commands

| Command | What it does |
|---------|-------------|
| `/ensemble:design` | Soft Launch session — idea through 5 core agents (UX, PM, CPO, Engineer, Roadmap), produces shippable V1 plan |
| `/ensemble:critique` | Run 5 core agents on an existing proposal in Soft Launch mode |
| `/ensemble:test` | Simulate 6 users walking through actual code — finds broken flows, missing states, and friction before real users do |
| `/ensemble:retro` | Retrospective on a shipped V1 — capture learnings, validate assumptions, inform next steps |
| `/ensemble:full-launch` | Expand a shipped V1 into Full Launch — re-evaluates with 5 core agents, then adds 3 specialists (Safety, Research, GTM) |
| `/ensemble:ux-review` | Standalone UX Designer review |
| `/ensemble:tech-review` | Standalone Lead Engineer technical review |

## Installation

### Claude Code Plugin Marketplace

```bash
/plugin install product-ensemble@claude-plugins-official
```

### Claude Code (via Plugin Marketplace)

```bash
/plugin marketplace add milovandekic/product-ensemble-marketplace
/plugin install product-ensemble@product-ensemble-marketplace
```

### Manual Installation

Clone this repo and copy into your Claude Code config:

```bash
git clone https://github.com/Dekic648/product-ensemble.git

# Copy commands (enables /ensemble:* slash commands)
mkdir -p ~/.claude/commands/ensemble
cp product-ensemble/commands/*.md ~/.claude/commands/ensemble/

# Copy skills and agents (enables agent execution)
mkdir -p ~/.claude/ensemble
cp -r product-ensemble/skills ~/.claude/ensemble/
cp -r product-ensemble/agents ~/.claude/ensemble/
```

## Repo Structure

```
product-ensemble/
├── .claude-plugin/
│   ├── plugin.json                    # Plugin manifest
│   └── marketplace.json               # Marketplace config
├── skills/
│   ├── ux-designer/SKILL.md           # UX Designer agent
│   ├── product-manager/SKILL.md       # Product Manager agent
│   ├── cpo/SKILL.md                   # CPO / Strategist agent
│   ├── lead-engineer/SKILL.md         # Lead Engineer agent
│   ├── roadmap-strategist/SKILL.md    # Roadmap Strategist agent
│   ├── user-tester/SKILL.md           # User Tester (Quality)
│   ├── safety-compliance/SKILL.md     # Safety & Compliance (Full Launch)
│   ├── research-advisor/SKILL.md      # Research Advisor (Full Launch)
│   └── gtm-strategist/SKILL.md        # GTM Strategist (Full Launch)
├── commands/
│   ├── design.md                      # /ensemble:design — Soft Launch session
│   ├── critique.md                    # /ensemble:critique — critique existing
│   ├── test.md                        # /ensemble:test — simulate 6 users
│   ├── retro.md                       # /ensemble:retro — retrospective on V1
│   ├── full-launch.md                 # /ensemble:full-launch — expand to Full Launch
│   ├── ux-review.md                   # /ensemble:ux-review — UX only
│   └── tech-review.md                 # /ensemble:tech-review — tech only
├── agents/
│   └── orchestrator.md                # Sequencing, routing, redirect loops
├── domain.md                          # Domain configuration (customize for your product)
├── README.md
└── RELEASE-NOTES.md
```

## The 9 Agents

```
DESIGN                    QUALITY              SCALE
─────────────────────     ──────────           ──────────────────
UX Designer          ─┐                        Safety & Compliance
Product Manager      ─┤   User Tester          Research Advisor
CPO / Strategist     ─┤   (6 personas)         GTM Strategist
Lead Engineer        ─┤
Roadmap Strategist   ─┘
        │                      │                       │
   Soft Launch            Post-Build              Full Launch
   (plan & build)      (test & fix)          (scale & distribute)
```

## Trigger

The ensemble activates when you describe a new feature or product idea:

- "I want to add onboarding to my app"
- "Let's design a notifications system"
- "I'm building a marketplace, where do I start?"

Or invoke directly with `/ensemble:design`.

## Design Principles

- **Distinct voices** — each agent has a non-overlapping lens and worldview
- **Sequential, not parallel** — order matters. UX before scope. Scope before strategy. Strategy before architecture. Architecture before roadmap. Build before test
- **Constructive tension** — agents challenge each other's decisions. Disagreements surface tradeoffs
- **User gates** — you approve every artifact before it moves forward
- **Advisory, not authoritative** — agents recommend. You decide
- **Soft Launch first** — always start with a shippable V1. Full Launch builds on real-world evidence
- **Test what shipped, not what was designed** — the User Tester reads code, not specs
- **Domain-aware** — configure `domain.md` to make agents think in your domain
- **Composable** — use the full ensemble, individual agents standalone, or just the commands you need

## License

MIT

# Release Notes

## v3.0.0 — User Tester + ISO Usability Metrics

### What's New

**User Tester agent (Persona 7: UI Purist):**
- 7 simulated personas walk through actual code paths and report what breaks
- Personas: First-Time Visitor, Rushing Consultant, Non-Technical User, Power User, Report Builder, Mobile User, UI Purist (ex-Apple designer)
- Each persona has a specific task, profile, and failure criteria
- Reports include file:line references for every issue found

**ISO 9241-11 Usability Scoring:**
- Every persona scored on 3 dimensions / 7 sub-metrics:
  - **Effectiveness (40%):** Completion Rate + Error Count
  - **Efficiency (30%):** Step Count (actual vs. minimum) + Wasted Effort
  - **Satisfaction (30%):** Clarity (1-5) + Confidence (1-5) + Delight (1-5)
- Composite score 0-100 per persona with benchmarks (90+ Excellent, 75-89 Good, 60-74 Acceptable, <60 Poor)
- Usability Scorecard table in every test report

**New command:**
- `/ensemble:test` — simulate 7 users walking through the product, get scored usability report

### Agent Count: 9

```
DESIGN (5)              QUALITY (1)           SCALE (3)
UX Designer             User Tester           Safety & Compliance
Product Manager         (7 personas)          Research Advisor
CPO / Strategist                              GTM Strategist
Lead Engineer
Roadmap Strategist
```

---

## v2.0.0 — Soft Launch / Full Launch + Roadmap Strategist

### What's New

**Roadmap Strategist agent:**
- Synthesizes all 4 prior artifacts into a prioritized implementation roadmap
- Phases with effort sizing, gates, dependencies, and deferred item triggers
- Decision Log capturing every major decision across all agents

**Soft Launch / Full Launch philosophy:**
- Every session produces a Soft Launch plan (shippable V1) by default
- Full Launch expands with Safety, Research, and GTM after V1 ships
- `/ensemble:retro` captures learnings from shipped V1

**3 Full Launch specialist agents:**
- Safety & Compliance — regulatory, accessibility, data flow review
- Research Advisor — feasibility validation for expanded capabilities
- GTM Strategist — pricing, distribution, launch planning

**New commands:**
- `/ensemble:retro` — retrospective on shipped V1
- `/ensemble:full-launch` — expand V1 into Full Launch with 3 specialist agents

---

## v1.0.0 — Initial Release

### What's New

**Four composable product agents:**
- **UX Designer** — leads new feature design with flows, friction analysis, and information architecture
- **Product Manager** — shapes UX briefs into buildable specs with scope boundaries and acceptance criteria
- **CPO / Product Strategist** — validates strategic fit at portfolio level with GO/REDIRECT/DEFER/KILL verdicts
- **Lead Engineer** — flags technical risks with severity-rated architecture advisories

**Orchestrator:**
- Sequential routing: UX Designer → PM → CPO → Lead Engineer
- CPO redirect loop handling (max 3 iterations)
- User approval gates between every agent
- Full artifact chain passed to each subsequent agent

**Commands:**
- `/ensemble:design` — full ensemble session for new feature ideas
- `/ensemble:critique` — run all four agents on an existing proposal
- `/ensemble:ux-review` — standalone UX Designer review
- `/ensemble:tech-review` — standalone Lead Engineer technical review

**Plugin compatibility:**
- `.claude-plugin` manifest for Claude Code plugin marketplace
- Standard SKILL.md conventions and plugin architecture

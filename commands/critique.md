---
description: "Run all five quartet agents on an existing proposal or spec — produces UX review, scope critique, strategic assessment, technical advisory, and prioritized roadmap"
---

You are running the Product Quartet in critique mode on an existing proposal.

## What This Does

Unlike `/design` (which starts from scratch), `/critique` takes an existing proposal, spec, or feature description and runs all five agents against it. Each agent evaluates the proposal through their lens and produces their standard artifact.

## How to Use

Provide or point to the existing proposal. This can be:
- A document in the repo
- A pasted spec or PRD
- A description of a feature that's already been designed or partially built

## Process

Run all four agents in sequence on the existing material:

1. **UX Designer** — reviews the proposal's user experience. Produces a UX Brief that identifies what's well-designed and what's missing from an experience perspective.
2. **Product Manager** — reviews scope and prioritization. Produces an Annotated Product Spec highlighting scope gaps, missing acceptance criteria, and prioritization concerns.
3. **CPO / Strategist** — evaluates strategic fit. Produces a Strategic Assessment with a GO/REDIRECT/DEFER/KILL verdict.
4. **Lead Engineer** — reviews technical implications. Produces a Technical Advisory with severity-rated architecture flags.
5. **Roadmap Strategist** — synthesizes all artifacts into a prioritized implementation roadmap with phases, dependencies, and sequencing rationale.

The user approves after each agent before proceeding to the next. Follow the same sequencing and redirect logic as the full design flow.

Present the complete output as a consolidated deliverable at the end.

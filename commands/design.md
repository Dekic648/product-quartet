---
description: "Run the full product quartet on a new feature or product idea — UX Designer, Product Manager, CPO, Lead Engineer, and Roadmap Strategist in sequence"
---

You are starting a full Product Quartet design session.

## What This Does

This command activates the quartet orchestrator, which routes your feature idea through four specialized agents in sequence:

1. **UX Designer** — defines the user experience (flows, interactions, friction points)
2. **Product Manager** — shapes it into a buildable spec (scope, stories, acceptance criteria)
3. **CPO / Strategist** — validates strategic fit (vision alignment, competitive positioning, timing)
4. **Lead Engineer** — flags technical risks (architecture gaps, security, scalability)
5. **Roadmap Strategist** — synthesizes everything into a prioritized implementation roadmap

You approve after each agent before the next one begins.

## How to Use

Describe your feature or product idea. Be as detailed or rough as you like — the UX Designer will ask clarifying questions.

Examples:
- "I want to add onboarding to my app"
- "Let's design a notifications system"
- "I'm building a marketplace — where do I start?"

## Process

Use the product-quartet:ux-designer skill first. After the UX Brief is approved by the user, proceed to product-quartet:product-manager. After the Product Spec is approved, proceed to product-quartet:cpo. If the CPO verdict is GO and the user approves, proceed to product-quartet:lead-engineer.

If the CPO issues a REDIRECT, route back to product-quartet:product-manager with the CPO's feedback. Maximum 3 redirect loops before surfacing to the user.

Follow the sequencing logic defined in the quartet-orchestrator agent. Every artifact must be approved by the user before advancing.

After the Lead Engineer's technical advisory is approved, proceed to product-quartet:roadmap-strategist. The Roadmap Strategist receives all four approved artifacts and produces a prioritized implementation roadmap.

After the roadmap is delivered, present the complete quartet output to the user and ask how they'd like to proceed.

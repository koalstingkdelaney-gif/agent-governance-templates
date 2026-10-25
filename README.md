# Agent Governance Templates

Free, ready-to-use templates for putting bounds around AI agents before they run — from **ghostcorpnet**.

If you run agents with tools, APIs, or a budget, these templates help you answer three questions before anything executes:

1. What is this agent allowed to do?
2. What is it allowed to spend?
3. Where is the record of what it actually did?

## What's inside

| File | What it is |
|---|---|
| [`templates/agent-bounds-checklist.md`](templates/agent-bounds-checklist.md) | The nine bounds every agent plan needs — workload, data class, resources, time, location, egress, storage, cost ceiling, and expiry — plus identity, approval tiers, spend controls, and stop conditions. Fill it in before any agent runs. |
| [`templates/approval-gate-policy.md`](templates/approval-gate-policy.md) | A fill-in policy template for risk-tiered approval gates: what always needs a human, what can run automatically inside bounds, and what stays draft-only. |
| [`templates/audit-log-template.md`](templates/audit-log-template.md) | A simple audit-log template: one row per action with actor, action, target, outcome, and timestamp — so "it probably didn't run" is never your audit trail. |
| [`templates/agent-bounds-checklist.pdf`](templates/agent-bounds-checklist.pdf) | Printable one-page PDF of the bounds checklist. |
| [`examples/playbook-sample-edition.md`](examples/playbook-sample-edition.md) | Free sample edition (sections 1–2) of The Playbook — why governance is the hard part, and the 8-layer governance stack. Also as a [PDF](examples/playbook-sample-edition.pdf). |
| [`examples/agent-bounds-checklist-original.md`](examples/agent-bounds-checklist-original.md) | The original free Agent Bounds Checklist document, exactly as published by ghostcorpnet. |

## How to use

1. Copy the template you need into your own project.
2. Fill in every field — an empty bound is an unbounded agent.
3. Keep the filled-in copy with your project records and review it whenever the agent's tools, data, or budget change.

These templates are framework-neutral: they work alongside LangGraph, CrewAI, AutoGen, or a hand-rolled agent loop, because they govern the plan, not the framework.

## License

MIT — see [`LICENSE`](LICENSE). Use, copy, modify, and share freely, including commercially. Attribution is appreciated but not required beyond the license terms.

## Go deeper

- **ghostcorpnet home:** https://koalstingkdelaney-gif.github.io/kestrelattice/
- **The Playbook — Studio Edition ($29):** the full system behind these templates — the 8-layer governance stack, approval-gate patterns, spend-limit configurations, and hash-linked audit trails, with a two-week rollout plan: https://koalstin.gumroad.com/l/hdigmr

The free templates stand on their own. The Playbook is there if you want the complete, worked version.

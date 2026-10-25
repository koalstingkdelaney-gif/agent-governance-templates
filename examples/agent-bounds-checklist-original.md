---
title: Agent Bounds Checklist (Free)
description: Free one-page checklist from ghostcorpnet: the bounds every AI agent plan needs before it runs — workload, data class, resources, time, location, egress, storage, cost, expiry — plus approval tiers and stop conditions. From The Playbook — Studio Edition: https://koalstin.gumroad.com/l/hdigmr
---

# Agent Bounds Checklist

**Before any AI agent runs, state its bounds. If you can't state the bounds, you don't have a plan — you have a wish.**

From The Playbook — Studio Edition by ghostcorpnet. Free to use and share.

---

## The nine bounds (fill in every one)

- [ ] **Workload** — exactly what tasks this agent may run, and nothing else
- [ ] **Data class** — what data it may read or write (public / internal / customer / secrets)
- [ ] **Resources** — which tools, APIs, and systems it may touch
- [ ] **Time** — when it may run, and the hard stop time
- [ ] **Location** — where it runs and where its outputs may go
- [ ] **Egress** — what it may send outside (email, posts, API calls) and to whom
- [ ] **Storage** — what it may create, keep, or delete
- [ ] **Cost ceiling** — the maximum spend for this plan, in dollars, counted per plan (not per account)
- [ ] **Expiry** — the date/time this plan dies unless a human renews it

## Identity and grants

- [ ] Every agent has a stable, owner-scoped identity — no anonymous or shared actors
- [ ] Every capability is an explicit grant record: capability, scope, expiry
- [ ] Least privilege by default; a request with no recorded identity is blocked, not warned

## Approval tiers

- [ ] **Hard-gated (always a human):** money, contracts, external outreach, credentials, permission changes, legal actions
- [ ] **Bounded auto:** routine work inside the nine bounds above — runs automatically, fully audited, auto-blocks at any bound
- [ ] **Draft-only:** proposals and messages are prepared and recorded, never executed

## Spend controls

- [ ] A meter or proxy counts spend in front of the framework — something is always counting
- [ ] When the ceiling is hit, the result is **blocked and recorded as blocked** — never retried, never billed

## Stop conditions

- [ ] A kill condition is named in advance (error rate, spend rate, unexpected egress, owner command)
- [ ] A blocked action persists an exact blocked result — "it probably didn't run" is not an audit trail
- [ ] Every action writes an audit row: actor, action, target, outcome, timestamp

---

**Want the full system?** The Playbook — Studio Edition ($29) covers the 8-layer governance stack, approval-gate patterns, spend-limit configurations, and hash-linked audit trails, with a two-week rollout plan:

**https://koalstin.gumroad.com/l/hdigmr**

ghostcorpnet digital products carry a no-refunds policy, stated plainly on every listing.

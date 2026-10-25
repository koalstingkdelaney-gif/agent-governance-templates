# Approval Gate Policy — Template

> A fill-in policy for deciding which agent actions need a human, which can run automatically inside stated bounds, and which must never execute at all.
>
> Free template from ghostcorpnet, derived from the free Agent Bounds Checklist. MIT licensed — see the repository LICENSE.

**Organization / project:** _fill in_
**Policy owner (team or role):** _fill in_
**Effective date:** _fill in_
**Review date:** _fill in_

---

## Principle

Every agent action falls into exactly one tier. If an action does not clearly fit a tier, it defaults to the **most restrictive** tier (Draft-only or Hard-gated) until a human classifies it. Missing evidence blocks the action instead of warning.

## Tier 1 — Hard-gated (always a human decision)

These actions never run automatically, regardless of bounds:

- [ ] Money movement, purchases, or spend commitments: _fill in examples_
- [ ] Contracts, terms acceptance, or legal actions: _fill in_
- [ ] External outreach (email, posts, messages) to people outside the organization: _fill in_
- [ ] Credential creation, use, rotation, or sharing: _fill in_
- [ ] Permission or access changes for any system: _fill in_
- [ ] Deleting data, products, or records: _fill in_
- [ ] Other: _fill in_

**How approval works for this tier**

- Who may approve: _fill in (named role)_
- Where the request is recorded: _fill in_
- What the record must contain: requesting agent identity, action, target, reason, timestamp
- Rejection path: a rejected action is recorded as rejected with the reason — never silently dropped, never retried in altered form without a new approval

## Tier 2 — Bounded auto (automatic, inside bounds)

Routine work may run automatically **only** when every condition holds:

- [ ] The action is inside the agent's nine bounds (see `agent-bounds-checklist.md`)
- [ ] The agent acts under a stable, owner-scoped identity
- [ ] A recorded grant covers this capability, scope, and time window
- [ ] Spend, if any, is counted by a meter/proxy and under the plan's cost ceiling
- [ ] The action writes an audit row (see `audit-log-template.md`)

The moment any bound is hit, the action **auto-blocks** and the block is recorded.

Examples for this project: _fill in_

## Tier 3 — Draft-only (prepare, never execute)

- [ ] Proposals, messages, and plans are prepared and recorded, never executed by the agent
- [ ] A human reviews the draft and decides whether it happens at all — outside the agent

Examples for this project: _fill in_

## Recording rules

- Every approval, rejection, and block is persisted with: actor, action, target, tier, outcome, timestamp.
- "It probably didn't run" is not an audit trail. A blocked action persists an exact blocked result.
- Approval records are append-only; corrections are new rows, not edits.

---

**Source:** derived from the approval tiers in the free Agent Bounds Checklist by ghostcorpnet.
Full system: The Playbook — Studio Edition — https://koalstin.gumroad.com/l/hdigmr

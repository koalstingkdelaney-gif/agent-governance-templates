# Agent Bounds Checklist — Template

> **Before any AI agent runs, state its bounds. If you can't state the bounds, you don't have a plan — you have a wish.**
>
> Free template from ghostcorpnet. Fill in one copy per agent plan. MIT licensed — see the repository LICENSE.

**Agent / plan name:** _fill in_
**Owner (team or role):** _fill in_
**Date prepared:** _fill in_
**Expiry / review date:** _fill in_

---

## The nine bounds (fill in every one)

- [ ] **Workload** — exactly what tasks this agent may run, and nothing else
  - Allowed: _fill in_
  - Explicitly not allowed: _fill in_
- [ ] **Data class** — what data it may read or write (public / internal / customer / secrets)
  - May read: _fill in_
  - May write: _fill in_
  - Never touches: _fill in_
- [ ] **Resources** — which tools, APIs, and systems it may touch
  - _fill in_
- [ ] **Time** — when it may run, and the hard stop time
  - Runs: _fill in_
  - Hard stop: _fill in_
- [ ] **Location** — where it runs and where its outputs may go
  - Runs in: _fill in_
  - Outputs may go to: _fill in_
- [ ] **Egress** — what it may send outside (email, posts, API calls) and to whom
  - May send: _fill in_
  - To: _fill in_
  - Never sends: _fill in_
- [ ] **Storage** — what it may create, keep, or delete
  - May create/keep: _fill in_
  - May delete: _fill in (default: nothing)_
- [ ] **Cost ceiling** — the maximum spend for this plan, in dollars, counted per plan (not per account)
  - Ceiling: $_fill in_
  - Counted by: _fill in (meter / proxy / provider dashboard check)_
- [ ] **Expiry** — the date/time this plan dies unless a human renews it
  - Expires: _fill in_

## Identity and grants

- [ ] Every agent has a stable, owner-scoped identity — no anonymous or shared actors
  - Agent identity: _fill in_
- [ ] Every capability is an explicit grant record: capability, scope, expiry
  - Grants recorded at: _fill in (file / system)_
- [ ] Least privilege by default; a request with no recorded identity is blocked, not warned

## Approval tiers

- [ ] **Hard-gated (always a human):** money, contracts, external outreach, credentials, permission changes, legal actions
- [ ] **Bounded auto:** routine work inside the nine bounds above — runs automatically, fully audited, auto-blocks at any bound
- [ ] **Draft-only:** proposals and messages are prepared and recorded, never executed

See `approval-gate-policy.md` in this folder for a full policy template.

## Spend controls

- [ ] A meter or proxy counts spend in front of the framework — something is always counting
- [ ] When the ceiling is hit, the result is **blocked and recorded as blocked** — never retried, never billed

## Stop conditions

- [ ] A kill condition is named in advance (error rate, spend rate, unexpected egress, owner command)
  - Kill conditions: _fill in_
  - Who can stop this agent, and how: _fill in_
- [ ] A blocked action persists an exact blocked result — "it probably didn't run" is not an audit trail
- [ ] Every action writes an audit row: actor, action, target, outcome, timestamp

See `audit-log-template.md` in this folder for the audit row format.

---

**Source:** derived from the free Agent Bounds Checklist by ghostcorpnet.
Full system: The Playbook — Studio Edition — https://koalstin.gumroad.com/l/hdigmr

# Audit Log — Template

> One row per agent action: actor, action, target, outcome, timestamp. If it isn't in the log, it didn't happen — and if it happened, it must be in the log.
>
> Free template from ghostcorpnet, derived from the free Agent Bounds Checklist. MIT licensed — see the repository LICENSE.

## How to use

- Append one row for **every** action an agent attempts — including blocked and rejected ones. A blocked action persists an exact blocked result.
- Never edit or delete rows. Corrections are new rows that reference the original row.
- Keep the log with the project it governs, and review it on the plan's expiry/review date.

**Project / plan:** _fill in_
**Log started:** _fill in_
**Kept at:** _fill in (file / system)_

## Log

| # | Timestamp (UTC) | Actor (agent identity) | Action | Target | Tier | Outcome | Notes |
|---|---|---|---|---|---|---|---|
| 1 | _2026-01-01T00:00:00Z_ | _agent-id_ | _what was attempted_ | _what it acted on_ | _hard-gated / bounded-auto / draft-only_ | _done / blocked / rejected / failed_ | _reason, approval reference, or block condition_ |
| 2 | | | | | | | |
| 3 | | | | | | | |

## Field guide

- **Timestamp (UTC)** — when the action was attempted, in ISO 8601 UTC.
- **Actor** — the agent's stable, owner-scoped identity. Never "the agent" or a shared account.
- **Action** — the verb and object, plainly stated (e.g. "send email", "write file", "call API").
- **Target** — the specific system, file, address, or record acted on.
- **Tier** — which approval tier governed this action (see `approval-gate-policy.md`).
- **Outcome** — exactly one of: `done`, `blocked`, `rejected`, `failed`.
  - `blocked` = a bound, grant, or spend ceiling stopped it before execution.
  - `rejected` = a human reviewer said no.
  - `failed` = it was allowed and attempted, but did not complete.
- **Notes** — the approval reference, the bound that blocked it, or the failure reason. Enough for a reviewer to reconstruct the decision without asking anyone.

## Machine-readable row (optional)

For automated logs, one JSON object per line (JSONL) with the same fields:

```json
{"ts":"2026-01-01T00:00:00Z","actor":"agent-id","action":"send email","target":"list@example.com","tier":"hard-gated","outcome":"blocked","notes":"no recorded grant for external outreach"}
```

---

**Source:** derived from the audit-row rule in the free Agent Bounds Checklist by ghostcorpnet.
Full system: The Playbook — Studio Edition — https://koalstin.gumroad.com/l/hdigmr

# Phase 3 — Companies

Goal: help the user browse the offline company pack in Notion, compare against their criteria, and record ratings on **Companies** rows. Do not invent companies. Default mode: **get end-to-end on the first good Select quickly**, then come back to rate more and refill the funnel.

## Start

1. Say you’re in Phase 3.
2. Require Companies rows in Notion (or Status notes that the pack is ready). If missing, stop and tell them to wait for the operator. Pack field rules: fetch **Companies pack schema** (https://raw.githubusercontent.com/mpetrovich/Fewer-public/main/companies-schema.md); rating properties: fetch **Notion state schema** (https://raw.githubusercontent.com/mpetrovich/Fewer-public/main/notion-state-schema.md).
3. Read Notion Search criteria and Profile for judgment context.
4. Quietly ensure Status has `active_conversation_limit` (default **5** if missing). Do not announce the limit unless enforcing capacity later.
5. Update Status: `phase` → `3-companies`. Confirm only the phase — not the conversation limit.

## How to work

- Present companies in small batches (not a dump of the whole DB). Lead with offline score/rationale when present, then your read against Hard/Soft criteria and Conflict notes.
- User rates each company. Status must be exactly one of: **Select**, **Reject**, **Unsure**.
- **Always capture a reason** with the rating (one or two lines). That reason is load-bearing: it improves later scoring and the pipeline, not just the user’s memory.
  - **Select** — why this company earns energy now (fit signal, not vibes-only).
  - **Reject** — which criterion or pattern failed (feeds false-positive analysis).
  - **Unsure** — what evidence is missing; don’t force a call.
- **Bullets before cannons:** as soon as there is **one Select with a reason** and they want to work that company now, **start Phase 4** for it (people → outreach) — set Status and begin; do not ask “ready for Phase 4?” Do not wait for a full pack rating. Momentum matters more than finishing the spreadsheet.
- After first outreach is in motion (or the user prefers to keep rating), return here to rate more batches and refill Selects so the funnel doesn’t go empty.
- Prefer depth over breadth: a short Select list they can actually work beats a long maybe-pile. Respect `active_conversation_limit` for companies with **active conversations** (post-outreach).
- **Upsert Notion Companies** Fit + Notes (reason) per **Notion state schema** (Select → `Interesting`, Reject → `Not a fit`, Unsure → empty Fit + `Unsure:` Notes). Prefer upsert by `Company ID`.
- Never add companies that aren’t in the Notion pack unless the user explicitly pastes a company to add — then create a Companies row with a note it was user-supplied.

## When to leave (first pass)

Leave Phase 3 for Phase 4 when:

1. At least one company is **Select** with a **reason**, and
2. The user agrees to work that company now (people → outreach).

When both are true, set Status and start Phase 4 work immediately — no ready-ask. Rating the rest of the pack is **not** a gate. Unrated rows stay deferred until they return.

## When to return

Come back to Phase 3 when the Select/active pipeline needs refill (e.g. after sends, declines, or spare capacity under `active_conversation_limit`). Continue batches; same rating rules.

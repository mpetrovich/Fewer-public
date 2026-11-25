# Phase 6 — Conversations

Goal: stay on top of active outreach — due follow-ups first, then replies, call prep, and terminal outcomes. The **due board** is read from Notion Conversations (**Next Step** / **Next Step Date**).

Message templates stay in **Phase 5 — Outreach** / **archived Outreach Chat Prompt (repo; optional harvest into Phase 5)**. Status, Next Step, Next Step Date, and Complete outcomes follow **Notion state schema**.

## Start

1. Say you’re in Phase 6.
2. Require at least one Conversations row (usually past `To outreach`). If none, send them to Phase 5.
3. Read Notion Conversations, Profile (especially **conversation-only** Non-negotiables), and Voice.
4. **Due board first** (below). Do not draft new first-touch outreach until overdue/due items are handled or the user explicitly defers them.
5. Then ask which lane: due follow-ups, reply, call prep, log an outcome, or refill (Phase 3/4/5).
6. Update Status: `phase` → `6-conversations`. Confirm only the phase on this upsert — mention the conversation limit only when enforcing capacity or offering refill.

## Due board

Query Conversations where Status is **In progress** (`Outreach sent`, `First followup sent`, `Second followup sent`, `Outreach engaged`, `Meeting scheduled`, `Meeting held`).

Show a short list, oldest Next Step Date first:

1. **Overdue** — Next Step Date before today
2. **Due today** — Next Step Date is today
3. **Upcoming** (optional, next 7 days) — only if they ask or the overdue/due lists are empty

Each line: person + company, Status, Next Step, Next Step Date, Contact Method. Mark overdue clearly in plain text.

If Next Step Date is missing on an In-progress row, treat it as **needs a next step now** — ask once, then set Next Step + Next Step Date before moving on.

Operator shorthand: `status check` → re-run the due board only.

## Default next-step cadence

When logging a send or bump, always set both fields (clear them when Status becomes **Complete**):

| After status | Default Next Step | Default Next Step Date |
|---|---|---|
| `Outreach sent` | Send first followup | ~7 days out |
| `First followup sent` | Send second followup | ~14 days out |
| `Second followup sent` | Mark as outreach ignored | ~7 days out |
| `Outreach engaged` | Reply / schedule (from thread) | as agreed, or ask |
| `Meeting scheduled` | Hold meeting / prep | meeting date |
| `Meeting held` | Thank-you / next name / outcome | <24h for thank-you; else decide |

Adjust dates if the user prefers; don’t invent replies or outcomes.

## Follow-ups (bumps)

For due bump rows, draft with Phase 5 **Bump** template into Voice. After they confirm send:

- `Outreach sent` → `First followup sent`
- `First followup sent` → `Second followup sent`
- After the second bump goes silent through its next-step date → offer `Outreach ignored` (`outcome_kind`: `no_reply`) rather than a fourth ping

Cadence reminder: ping → ~1 week → ping → ~2 weeks → final → stop.

## Replies and objections

Classify briefly (don’t argue into an intro):

- Loose connection after preempt → thank; `Outreach declined` + `loose_connection`; new contact if useful
- Timing / bandwidth → `timing` or stay In progress with a later Next Step Date
- Won’t intro → `wont_intro`
- Soft no → `soft_no`
- Stronger path / other name → `Introduced to another` + `introduced_elsewhere`; open a new conversation row if pursuing
- Premature process (apply / recruiting) → Phase 5 process-deflection draft; stay engaged
- Silence through cadence → `Outreach ignored` / `Outreach went cold` as appropriate

Draft replies in voice. Upsert Status / Next Step / Notes (outcome) on the Conversations row.

## Call prep

When a meeting is scheduled (or they’re about to book):

1. Goal for the chat (learn / HM path — not pitch).
2. 5–7 questions: easy → surprise → “if joining today” → “who else?”
3. 2–3 **conversation-only** Non-negotiables / sec-3 style probes from Profile (green/red flags).
4. After: thank-you <24h; new names <48h; update Status (`Meeting held`, then outcome or next intro).

## Outcomes (Complete)

When a thread ends, set Status + required outcome in Notes (`outcome_kind` + `reason` per **Notion state schema**). Clear Next Step / Next Step Date. Free capacity under `active_conversation_limit` → offer Phase 3/4/5 refill.

## Capacity

Count **In progress** conversations by company toward `active_conversation_limit` on Status. Don’t open new Sends past the limit without choosing what to pause or complete.

## When to leave

Due board clear (or deferred), and either a meeting is prepped, an outcome is logged, or they want to draft more first-touch (Phase 5) / refill Selects (Phase 3/4).

## When to return

Anything due, a reply landed, a meeting needs prep, or capacity freed for new outreach.

# Notion state schema

Mutable search state lives in the subject’s **Notion** pack. Phase playbooks and this schema are **public raw markdown** on [Fewer-public](https://github.com/mpetrovich/Fewer-public) (agents fetch; private git mirrors for edit workflow). After every confirm, upsert Notion.

Canonical shape: per-subject **Profile Pack** + **Databases**; shared phase/schema playbooks via raw GitHub URLs (see Agent Bootstrap).

## Pack layout (required)

Per-subject pack (`Fewer` / subject root / equivalent):

| Notion artifact | Parent | Purpose |
|---|---|---|
| **Status** page | **Profile Pack** | Current phase id, `active_conversation_limit` (default **5**), short operator notes |
| **Profile** page | **Profile Pack** | Who they are + how they work (markdown sections below) |
| **Voice** page | **Profile Pack** | Short writing-voice sample for outreach |
| **Search criteria** page | **Profile Pack** | Hard filters + soft heuristics for offline scrape/score |
| **Intro Blurb** page (optional) | **Profile Pack** | Third-person intro blurb for Phase 5 |
| **Companies** database | **Databases** | Scored / rated companies |
| **People** database | **Databases** | Contacts tied to companies |
| **Conversations** database | **Databases** | Outreach threads + next steps |

Shared playbooks (raw fetch — `https://raw.githubusercontent.com/mpetrovich/Fewer-public/main/<file>`):

| File | Purpose |
|---|---|
| `phase-0-onboarding.md` … `phase-6-conversations.md` | Method playbooks |
| `notion-state-schema.md` | This file — pack + DB property contract |
| `companies-schema.md` | Companies field rules |

Operator seeds the subject’s Profile Pack + Databases and invites the subject as a Notion **Member** (not Guest) with Can edit on their pack. Subject connects the Notion app in ChatGPT to the Fewer workspace before Phase 1 saves.

## Hard rules for ChatGPT

1. **Read** phase and state from Notion (Status + DBs). Do not invent rows.
2. **Write** only via Notion create/update (pages and DB rows). After the user confirms an artifact, upsert Notion and confirm the page/row URL or title changed.
3. Upsert only properties defined here (match the subject’s live pack DBs).
4. Do not store full message bodies in Notion properties. Short Notes / reasons only.
5. **Phase-move Status upserts:** update Phase (and Notes if needed). When confirming to the user, say only the new phase — never restate Active conversation limit unless the current phase playbook is enforcing capacity (Phases 3 / 5 / 6).

## How ChatGPT finds Status

- **Exact title:** `Status`
- **Path:** `Home` → `Profile Pack` → `Status`
- After Notion connect, open that page (search `Status`, or Profile Pack → Status). Verify Phase row present. Fallback: `Profile`. If missing, ask for the pack link and ping the operator — do not invent Status.

## Status page

Keep a short top section ChatGPT can update. Prefer a two-column table (matches the Pilot Template skeleton); bullets are fine if already present:

```markdown
# Status

| | |
|---|---|
| Phase | `0-onboarding` |
| Active conversation limit | 5 |

## Notes
```

Phase values: `0-onboarding` | `1-profile` | `2-search-criteria` | `3-companies` | `4-people` | `5-outreach` | `6-conversations`.

Detect phase from Status (and whether Profile / Voice / Search criteria / Companies rows exist). Default for a brand-new pack: `0-onboarding`.

`Active conversation limit` is a Status field the later phases enforce; it is not chat copy for every Status read or phase handoff.

## Profile / Voice / Search criteria pages

Same markdown shapes as the Phase 1–2 playbooks (and empty shells in `pack-pages/`). Upsert the **page body** after user confirm (create the page under **Profile Pack** if missing). Titles: `Profile`, `Voice`, `Search criteria`.

## Intro Blurb page (optional)

Third-person paste-ready blurb for Phase 5 intro requests. Empty shell in `pack-pages/intro-blurb.md`:

```markdown
# Intro Blurb

## Context

## Full Version

## Short Version

## Notes for the outreach chat
-
```

## Companies database

Companies properties. In chat, the subject still rates **Select** / **Reject** / **Unsure**; write those onto **Fit** + **Notes**:

| Chat rating | Notion `Fit` | `Notes` |
|---|---|---|
| Select | `Interesting` | Required reason (one or two lines) |
| Reject | `Not a fit` | Required reason |
| Unsure | *(empty)* | Starts with `Unsure:` + what evidence is missing |

| Property | Type | Rules |
|---|---|---|
| `Company Name` | title | Display name. |
| `Company ID` | text | Opaque stable id from the sourcing pipeline. Upsert by this key when present. |
| `Fit` | select | `Interesting` or `Not a fit` (see mapping above). |
| `Notes` | text | Required once the subject rates (reason). |
| `LinkedIn Connections` | url | 1st/2nd-degree LinkedIn people-search URL, or empty. **Never invent or rebuild.** |
| `Description`, `Website`, `LinkedIn`, `Location`, `Company Size`, `Stage`, `Industries`, `Review Rank` | various | Operator / pack fields. ChatGPT may read for judgment; do not invent. |
| `Company Contacts` | relation → People | Optional; keep in sync when useful. |

Operator loads unscored / proposed companies into this DB after Phase 2. Phase 3 refuses to invent companies: require existing Companies rows (or an operator “pack ready” note on Status).

## People database

People properties.

| Property | Type | Rules |
|---|---|---|
| `Name` | title | Required. Upsert by Name + Company when no stable person id exists. |
| `Company` | relation → Companies | Required for outreach targets; must point at a company with Fit = `Interesting`. |
| `Role/Title` | text | `""` if unknown. |
| `LinkedIn Profile URL` | url | Or empty. |
| `Notes` | text | **How you know them** (required for people chosen for outreach). |
| `Warmth` | select | `Cold` / `Lukewarm` / `Warm` when assessed; empty = unset. |
| `Is Hiring Manager` | checkbox | Optional. |
| `Connected To` / `Connected By` | relation → People | Optional path graph. |
| `Conversations` | relation → Conversations | Keep linked when a thread exists. |

**Pursue** (chat “Select” for a person) = non-empty Notes (how you know them) + Warmth set when known. **Skip** = omit creating a row, or note skip in Notes without opening outreach.

## Conversations database

Conversations **Status** options exactly.

| Property | Type | Rules |
|---|---|---|
| `Title` | title | e.g. `{Person} for {Company}`. |
| `Status` | status | Exactly one value from the list below. Default before send: `To outreach`. |
| `Recipient` | relation → People | The person messaged (upsert key with company via that person’s Company). |
| `Company Contact` | relation → People | Optional; target at the company when Recipient is a connector. |
| `Contact Method` | multi_select | `LinkedIn`, `Email`, and/or `SMS`. |
| `Next Step` | text | Short next action; clear when Complete. |
| `Next Step Date` | date | When a follow-up is dated; clear when Complete. |
| `Notes` | text | Freeform. When Complete, include outcome kind + one–two lines of what happened (see below). |
| `Last Updated` | last_edited_time | System-managed. |

One conversation per Recipient (person) for a given company path. Upsert the existing row; do not mint duplicates.

### Status groups

| Group | Statuses | Counts toward active limit? |
|---|---|---|
| To do | `To outreach` | No |
| In progress | `Outreach sent`, `First followup sent`, `Second followup sent`, `Outreach engaged`, `Meeting scheduled`, `Meeting held` | Yes (by company) |
| Complete | `Outreach declined`, `Outreach ignored`, `Outreach went cold`, `Not a good fit`, `Not hiring / No role`, `Introduced to another`, `Interview process started` | No |

### Outcome on Complete

Encode in **Notes** on Complete (the Conversations DB has no separate Outcome Kind property):

```text
outcome_kind: <kind>
reason: <one or two lines>
```

`outcome_kind` values: `loose_connection` | `timing` | `wont_intro` | `soft_no` | `no_reply` | `went_silent` | `not_a_fit` | `not_hiring` | `introduced_elsewhere` | `interview_started` | `other`

| Status | Typical `outcome_kind` |
|---|---|
| `Outreach declined` | `loose_connection`, `timing`, `wont_intro`, `soft_no`, or `other` |
| `Outreach ignored` | `no_reply` |
| `Outreach went cold` | `went_silent` |
| `Not a good fit` | `not_a_fit` |
| `Not hiring / No role` | `not_hiring` |
| `Introduced to another` | `introduced_elsewhere` |
| `Interview process started` | `interview_started` |

## Due board

Query Conversations where Status is In progress, ordered by Next Step Date ascending. Overdue = date before today; due today; missing date = needs a next step now.

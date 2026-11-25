# Phase 2 — Search criteria

Goal: produce a pack **Search criteria** page for the operator’s offline scrape + score run. Capture human-readable rules only — the operator maps them into sourcing/scoring. Do not invent companies. Do not start Phase 3 until Companies rows are in the pack (or Status says the pack is ready).

Enter Phase 2 **immediately** after Phase 1 confirm — no pause and no “ready for Phase 2?” ask.

## Start

1. Say you’re in Phase 2.
2. Read pack **Profile** (required). Use Positioning, Target seat, Proof, Edge, Not for, Working style, Energize/Drain patterns, and **Searchable** Non-negotiables. Ignore **Conversation-only** Non-negotiables for criteria. Treat Phase 1 searchable NNs as provisional until confirmed here.
3. Draft criteria from what’s already there; ask only for gaps.
4. Write Search criteria, read back once, confirm.
5. **Upsert** the pack Search criteria page. Update Status: `phase` → `2-search-criteria`, note waiting for offline pack. Confirm only the phase (and waiting-for-pack note) — never restate active conversation limit.
6. **Phase 0–2 summary PDF:** After criteria confirm, generate a **ChatGPT PDF** snapshot of Profile + Voice + Search criteria (nice, cross-platform, keepable). Say clearly: **the pack remains the live source of truth**; the PDF is a portable keepable, not a second SoT.
7. **CV review (only if they uploaded a CV):** Give a **short unsolicited gaps/misalignment list** vs Profile. Then **ask** if they want an updated CV generated — do **not** generate a rewritten CV unprompted. If no CV, skip this beat.
8. **Stop.** Tell them the operator will source/score offline and load companies into their Companies DB. After the PDF (+ optional CV) beat: only wait for that pack (and pack write help if needed) — no Phase 3 sneak-peek.

Set Status `phase` → `3-companies` only once Companies rows exist (or the operator marked pack ready). Same announce rule: phase only.

## Progressive Profile upserts

Whenever Phase 2 revises a prior **searchable** Non-negotiable (e.g. softens “fully remote” into a nuanced remote/distributed rule), **upsert Profile the same turn** so Searchable NNs stay aligned with criteria. One-line “what changed.” Avoid thrashing mid-answer; pack rewrite-in-place is fine. Do the same for other Profile fields if criteria clearly change understanding (seat, Not for, etc.).

## Interview pacing (hard rules)

- **Exactly one gap question per turn.** Never bundle industry + size + remote in one message.
- Prefer open questions; offer short examples only after a thin answer.
- **Conflict notes** get their own turn after hard filters are filled.

## Interview (fill gaps only)

Push for priorities and deal-breakers. Write rules in plain language (what to include, exclude, or prefer).

**Hard filters — ask what’s missing from the profile (one field per turn):**

- Industry / sector (≈3 primary max)
- Domain excludes (crypto, defense, gambling, …)
- Stage floor–ceiling
- Headcount / team size (ask for a **range**; note firm lower/upper bounds vs soft preference — e.g. “won’t go below ~20 eng” vs “prefer under 200”)
- Geography
- Remote / hybrid / on-site
- Business model / customer (if it matters)
- Funding model (VC-backed vs bootstrapped / profitable, if it matters — hard only when it can be judged from company materials; otherwise soft)
- Traction / product stage (if it matters)
- Engagement type (FT, fractional, either — affects how the operator sources)
- Comp or rate floor (if it matters)
- Other instant-no excludes

**Soft heuristics — derive, then confirm (one cluster per turn if asking):**

- **Reward** — from best-work problems, edge, energize patterns (what a good-fit company should look like on paper).
- **Penalise** — from drains, Not for, wrong-fit patterns.
- **Level / seat** — copy from Profile Target seat if present; confirm if missing. Use later for role talks, not company scrape filters. Weight soft tech/process signals (e.g. greenfield vs legacy) by seat: often matter more for IC/hands-on seats than for pure people-manager seats — ask once if unclear. Never invent **Also acceptable** seats — ask if missing; leave blank if none.
- Keep short. No essay.

Promote every **Searchable** Non-negotiable into Hard filters (or Soft if it’s preference-weighted, not binary). Honor hard vs prefer when Profile recorded it — and if the interview softens or hardens it, update both Search criteria and Profile.

**Conflict notes — always ask once** (its own turn after hard filters):

Where do their own criteria fight each other? Record the tension; do not silently pick a winner.

## Artifact: Search criteria (pack page)

```markdown
# Search criteria

## Hard filters
| Rule | Include / exclude |
|---|---|
| … | include / exclude |
| Domain excludes: … | exclude |
| Funding model: … | include / exclude / soft-if-unclear |

## Soft heuristics
### Reward
- …

### Penalise
- …
- Level/seat (if any): … — not a company scrape filter

## Conflict notes
- …

## Operator notes
- Offline: scrape with Hard filters, score with Soft heuristics + Conflict notes.
- Scored recommendations must be exactly: **Select**, **Reject**, or **Unsure**.
```

Keep the page small — plain-language rules the operator can map into scrape and score.

## Done when

- Search criteria page exists in the pack and the user confirms it.
- Profile searchable NNs (and any other revised Profile fields) match the confirmed criteria.
- Phase 0–2 **summary PDF** offered (pack stays live SoT).
- If a CV was uploaded: short gaps list delivered; updated CV only if they asked.
- Status phase is `2-search-criteria` (until the Companies pack lands).
- User knows: next step is offline operator pack into Companies → then Phase 3 select/rate in chat.
- Chat does **not** invent companies or start rating before the pack exists.

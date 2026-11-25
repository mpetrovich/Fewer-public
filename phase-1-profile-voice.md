# Phase 1 — Profile & voice

Goal: produce pack **Profile** and **Voice** pages only. Do not build search criteria here (that’s Phase 2). Keep both short. When both pages are confirmed, **continue straight into Phase 2** — no pause, no “come back later.”

## Start

1. Say you’re in Phase 1.
2. Confirm the workspace connector can open the subject’s pack (Status or Profile). If not connected, send them back to Phase 0 setup (trigger workspace connect card + connect) before drafting durable content. Skip Member/Guest checks.
3. Capture **identity** first (required): preferred name for outreach, then public LinkedIn profile URL — **separate turns**. Optionally ask them to paste LinkedIn About (or a short bio) if they have one — speeds later questions; the public URL / paste **seeds**, it does not replace the interview. Soft-optional: ChatGPT LinkedIn app for people lookup later — not own-profile seed.
4. After LinkedIn URL: offer **optional CV/resume upload** (beneficial for Proof/Edge seed and Phase 2 gap-check if present — not required). One turn; if they skip, continue.
5. Interview with the questions below. Skip any question already answered clearly by CV/URL/paste; if thin, still ask once in their words. Prefer open questions — no multiple-choice spoon-feeding. CV/LinkedIn may **pressure-test** answers (“your CV says X — still true?”) without A/B/C menus.
6. Draft the two pages (show in chat). Read them back in one short pass. When presenting **Voice**, include a **fictional but representative** “reach out to X at Y” sample (made-up person/company fitting their seat — tone check, not a real target). If it doesn’t sound like them, ask for real message samples (links preferred; auto-fetch) and revise. When they confirm, **upsert pack Profile + Voice** (create under the pack if missing). Confirm by page title/URL.
7. Update pack **Status**: `phase` → `1-profile` while working; → `2-search-criteria` when both pages are confirmed — then **start Phase 2 immediately** (no “ready for Phase 2?” ask). When confirming Status, say only the phase — never restate active conversation limit.

Build Profile **progressively**: if understanding changes mid-phase (or later in Phase 2), upsert Profile with a one-line “what changed.” Avoid thrashing mid-answer.

## Interview pacing (hard rules)

- **Exactly one question per turn.** Never stack topics. Wait for an answer (or skip) before the next.
- Prefer **open questions** in their own words. Do **not** lead with multiple-choice lists, emoji menus, or “pick A/B/C” unless they ask for options or a free-text answer was too thin — then one short clarifying follow-up is OK.
- After a thin answer, probe the **same** topic once (e.g. “what was the concrete result?”) before moving on.
- One assistant message per turn — no duplicate dumps of the same draft.

## Interview (ask only what you still need)

Order matters. Push for concrete picks when they hedge — still one question per turn.

1. **Identity (name)** — Preferred first name (how they want to appear in outreach) and full name if different.
2. **Identity (LinkedIn)** — Public LinkedIn profile URL (`linkedin.com/in/...`). Required before finishing Phase 1.
3. **Optional CV** — Invite upload once (beneficial, not required). If uploaded, use to seed/pressure-test later answers.
4. **Best work** — Open: walk through two or three stretches of best work in their words (company/context shape, problem they owned, **concrete result**). If they pasted LinkedIn or a CV, ask what’s missing or what they’d emphasize — don’t only summarize the file.
5. **Edge** — Open: what they can do that most people with their title can’t. **Required:** one elevator-pitch sentence. **Optional:** short detail bullets for important nuance that won’t fit cleanly in that sentence. Bullets do **not** replace the sentence.
6. **Target seat** — Ask early (before Not for / Non-negotiables). What seat are they targeting (e.g. IC, tech lead, EM, director, …)? Capture **primary**. **Always ask once** for backup / **Also acceptable** seats — never invent alternatives; leave blank if they have none. Wrong-seat filters belong under Not for.
7. **Not for** — Open: wrong *role or seat* / mis-hires they should turn down (not culture — that’s Non-negotiables). “What are you not?” works well.
8. **Energize** — Open, alone: when did time disappear at work? (problem type, team, pace — not life story.)
9. **Drain** — Open, alone (separate turn from Energize): what made Mondays dreaded? Keep distinct from Energize.
10. **Non-negotiables** — Dealbreakers they won’t compromise on (distinct from role **Not for**). For each one they give, classify:
   - **Searchable** — maps to a company field you can filter on (e.g. remote-only, geo, headcount cap). Mark **hard** vs **prefer** when they say. Treat searchable NNs as **provisional** until Phase 2 confirms or softens them. Phase 2 must promote these into hard (or soft) criteria and reconcile Profile if they change.
   - **Conversation-only** — only knowable by talking to people (e.g. trust, agency, ego/politics). Guide later employee/HM chats; do **not** pretend these are company-list filters.
11. **Working style** — Prefer: draft 2–4 lines from their best-work / energize answers, then ask them to correct. Only if still thin: ask how they like to work (pace, ownership, closeness to the work). Do not open with a long pick-list.
12. **How they write / Voice check** — Prefer: ask for links to messages, posts, or pages they wrote and like (URLs are enough). **Auto-fetch** once and store key excerpts in Voice — do **not** ask them to paste the writing. On fetch failure: keep the URL, flag Voice **thin** until retry, and continue. Else (no links): describe tone in a few words. Always include one **fictional “reach out to X at Y”** sample in Voice for tone check; if off, ask for real samples and revise.

Do **not** run a full targeting interview here — park industry/stage/geo/rate discovery for Phase 2 unless a dealbreaker already surfaced. If a Non-negotiable is searchable, record it now and ensure Phase 2 picks it up.

## Artifacts (pack page bodies)

### Profile

```markdown
# Profile

## Identity
- **Name:** Preferred first name (and full name if useful for intros)
- **LinkedIn:** https://www.linkedin.com/in/...

## Positioning
One sentence: who they help, with what, how.

## Target seat
- **Primary:** …
- **Also acceptable:** … (only if they said so — never invent; blank if none)

## Edge
One elevator sentence: what they can do that most people with their title can’t.
Optional short detail bullets if important nuance won’t fit in that sentence (bullets don’t replace the sentence).

## Proof
- 3–5 bullets max. Each: **context → problem → result** (one line each or one tight bullet).

## Working style
A few lines: pace, ownership, how close to the work, how they like to collaborate.

## Not for
Bullets: wrong role/seat / mis-hires.

## Non-negotiables
### Searchable
- Bullets that map to filterable company fields (remote, geo, size, …). Note hard vs prefer. Provisional until Phase 2 confirms/softens → hard/soft criteria + Profile upsert if revised.

### Conversation-only
- Bullets only knowable in people conversations (trust, ego, …). Probes for employee/HM chats; walk away if violated. Not company-list filters.
```

No bio essays, brand pyramids, or duplicate sections.

### Voice

```markdown
# Voice

## Tone
Short bullets (e.g. direct, warm, no hype, short sentences).

## Do / don’t
- Do: …
- Don’t: …

## Samples
1. Fictional but representative “reach out to X at Y” outbound (tone check — not a live target).
2. Optional fuller sample from linked writing the agent fetched (or real samples they provided after the tone check failed).
If only URLs exist and fetch failed: list URLs and mark **thin** until excerpts are retrieved.
```

Prefer rules + real/fetched samples over a long “voice document.” Distill from fetched writing; don’t invent a persona. Never require the user to paste when they gave a link. The fictional X@Y sample is required at read-back.

## Done when

- Both pack pages exist and the user confirms they’re good enough for outreach tone and “who I am.”
- Profile **Identity** has a preferred name and a real LinkedIn URL (not a placeholder).
- Profile has **Target seat** (primary at minimum); **Also acceptable** only if asked and answered (blank OK).
- Edge has the required elevator sentence (optional detail bullets OK).
- Status phase is `2-search-criteria`.
- **Continue straight into Phase 2** — turn this into hard/soft search criteria now.

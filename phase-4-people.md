# Phase 4 — People

Goal: for one or more **Select** companies, help the user pick who to contact. The user brings people from LinkedIn (or similar). Do not invent contacts. Default: **get one solid contact to outreach quickly**, then refill.

## Start

1. Say you’re in Phase 4.
2. Require at least one Notion Companies row with Fit = `Interesting` and a non-empty reason in Notes. If none, send them back to Phase 3.
3. Work one Select company at a time (usually the one they just chose in the bullets-before-cannons flow).
4. Update Status: `phase` → `4-people`. Confirm only the phase — do not mention active conversation limit.

## How to work

- From the Companies row, if `LinkedIn Connections` is set, give them that link first (one click to their 1st/2nd-degree LinkedIn connections at the company). Do not invent or rebuild the URL — see **Companies pack schema**. If it is missing, ask them to look up people on LinkedIn the usual way.
- Ask them to paste names, titles, and profile links for people they want to consider.
- For each person they add, ask **How do you know them?** (degree, shared context, history). That field is the useful signal — assume they’re only bringing people they actually know; if they don’t, it’ll show up here.
- Help them choose using:
  - **Warmth** — how likely they are to reply (from how they know them)
  - **Role** — useful vantage on the company (not only “most senior”)
  - **Path to hiring manager** — can this person pull the thread closer to the decision-maker?
- Prefer a real warm path over a cold “perfect title.” Aim toward the hiring manager over time; the first contact need not be the HM.
- User picks who to contact. **Upsert** Notion **People** rows per **Notion state schema**: Name, Company relation, Role/Title, LinkedIn Profile URL, Notes = how you know them, Warmth when known.
- Do **not** invent people, emails, or mutual connections.

## When to leave (first pass)

As soon as **one person** is chosen for outreach (Notes has how you know them) for the current company, **start Phase 5** (draft outreach) immediately — set Status and begin; no “ready for Phase 5?” ask. Don’t wait for a full org chart.

## When to return

Come back after sends or when starting another Select company. Same schema and rules; keep filling people so outreach doesn’t stall.

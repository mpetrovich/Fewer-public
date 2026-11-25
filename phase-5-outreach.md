# Phase 5 — Outreach

Goal: draft warm, low-pressure outreach in the user’s voice toward decision-maker conversations. Prefer a first real send over polishing forever. Templates below are **structure only**. Rewrite every draft into Notion Voice (and keep method rules).

Full coach detail also lives in **archived Outreach Chat Prompt (repo; optional harvest into Phase 5)**; this page is the playbook for the multi-phase project (Notion tracking + when to leave). Cold-direct patterns below are distilled from archived cold-outreach analysis and adapted to Fewer’s connector-first philosophy. The playbook itself is person- and role-agnostic: target whoever owns the relevant problem, across functions.

## Start

1. Say you’re in Phase 5.
2. Require a People row tied to a **Select** company with non-empty Notes (how you know them). If missing, send them to Phase 4 (or 3). For **cold direct** (no warm path), Notes should still name why this person (function / problem ownership) and the checkable company reason.
3. Read Notion Voice, Profile, optional Intro Blurb, the company reason (Notes), and how_you_know_them (People Notes). If Voice is missing or unconfirmed, calibrate voice first (3-5 real outbound samples), upsert Voice, before treating drafts as final.
4. Update Status: `phase` → `5-outreach`. Confirm only the phase on this upsert. Mention the conversation limit only when enforcing capacity (below).

## How to work

- **Default path:** **Intro request** to a connector who does **not** work at the company. Use **Post-intro** after an intro lands. Use **Direct (warm)** when the Select person already works at (or recently left) the company and there is a real relationship (or a warm intro just landed).
- **Parallel path (cold direct):** when warm/connector paths are missing, declined, or stalling after cadence, draft **Cold direct** to the **decision-maker who owns the problem** (founder, hiring manager, or function owner in product, engineering, ops, sales, or wherever the gap lives), not HR or a generic inbox. Keep low-pressure framing. Do not treat cold as the default when a usable connector exists.
- Ground drafts in: how they know the person (or why this decision-maker owns the gap), why this company (Select reason), and low-pressure framing (not expecting a role; want to learn).
- Never lead with hiring?, a referral demand, or “please see my resume.” No em/en dashes in drafts. Full sentences with subjects on softeners.
- Show a fenced paste-ready draft; let them edit.
- When they confirm they’ve sent it (or want it logged before send), **upsert a Conversations row** per **Notion state schema** (Recipient → People; Title like `{Person} for {Company}`). Status: `Outreach sent` when sent; `To outreach` only if they want the draft tracked first. Set Contact Method, and fill Next Step / Next Step Date when a bump or reply is planned (e.g. first follow-up ~1 week out). **Every send needs a dated next step before it goes out.**
- Bumps: move `Outreach sent` → `First followup sent` → `Second followup sent` (then typically `Outreach ignored` / `Outreach went cold` if silent). Replies → `Outreach engaged`; booked → `Meeting scheduled`; done → `Meeting held`. Slow replies happen; finish the cadence before writing a company off.
- Terminal / Complete statuses: put `outcome_kind` + `reason` in Notes (or Outcome Kind property if the pack has it). For `Outreach declined`, classify the kind (`loose_connection`, `timing`, `wont_intro`, `soft_no`, or `other`) from what they said. Don’t invent. Clear Next Step / Next Step Date when Complete.
- Respect `active_conversation_limit` on Status: don’t open new **in-progress** outreach past the limit without them choosing what to pause.

### Cold direct rules (when warm stalls)

Keep Fewer philosophy (warm first; resume still a closing document on warm/connector paths). Rules below apply across functions; pick the owner of the problem, not a default title.

1. **Decision-maker, not HR.** Prefer the person who owns the gap you care about (founder, or the function owner in product, eng, ops, sales, GTM, customer success, etc.). Generic inboxes mostly don’t reply.
2. **One specific, checkable reason.** Funding round, product launch, hiring post that reveals a plan, infra move, ops bottleneck, market or customer segment they’re opening. Not “exciting company.”
3. **Lead with the gap you can help with (or want to learn about), not the job title you want.** Match the gap to their function. Examples: a backlog or launch risk (product), reliability or platform debt (eng), a process or capacity crunch (ops), a territory or segment shortfall (sales/GTM). When Profile supports a concrete offer, use it; otherwise stay in learning mode with a concrete hook.
4. **One true thread of story that fits that company**, not the whole CV. Cut Profile/Edge to the piece that matches their world (shipped product, systems you’ve owned, ops you’ve run, customers you’ve opened, and so on).
5. **Name the obvious objection first** when it’s real (language, domain, stack, location, seniority mismatch). Turns a disqualifier into judgement.
6. **Ask for 15 to 20 minutes, not a role.** Same low-pressure line as warm drafts.
7. **Prepare 2 to 3 people per company** before the first send (primary + backups across the relevant function). After a champion appears, keep the thread moving through them; contact new names within ~48 hours and name the referrer.
8. **CV on first cold touch is optional, not default.** Warm/connector/direct-warm paths still leave resume off first touch. On cold direct only, a **company-named tailored CV** may ride along when the subject wants it. Still ask for a call; never “apply via this PDF.” Prefer conversation-first when unsure.
9. **Guess emails only from a verified pattern**, and label guesses as unverified in People Notes.
10. **After every call:** thank-you within 24 hours naming one thing they said; ask who else to speak with; follow new names within 48 hours.

## Templates

Fill brackets from Notion. Prefer Intro Blurb for the third-person blurb (swap in company name + low-pressure line); else build from Profile Positioning + Edge. For `[Subject LinkedIn URL]` and the subject’s name in drafts, use Profile **Identity**. Use **their** / **them** for pronouns unless the user specifies otherwise.

### Intro request (to a connector)

Outer message = user’s voice. Inner paste block = mutual’s voice to the target.

```text
Hey [Name]! I hope you're well. I'm currently exploring new opportunities and [Company] is on my short list. I noticed you're connected to [Target] ([Target LinkedIn URL]) there. Would you be open to making a quick intro?

Even if you don't know [Target] well, a short intro from you still helps a lot. The worst case is they don't reply. Or if you know someone else at [Company] better, an intro to them would be just as helpful. To make it easy, here's a message you can copy and send. Of course, edit it however you like:

Hi [Target], I'm connected with [Subject] and wanted to introduce you. [INTRO BLURB with company name + low-pressure line] Would you be open to connecting with them? [Subject LinkedIn URL]
Thanks, [Name]

Thank you, I really appreciate it!
```

### Post-intro / direct (warm)

```text
Hey [Name], [thanks for being open / thanks to Mutual for connecting us].

[1 to 2 specific sentences on why this company.]

Although I am in the job market, I'm not expecting that you know of a role or opening. I'm simply interested in learning more about your experience at [Company].

Would you have 15 to 20 minutes for a quick call sometime in the next week or two?
```

### Cold direct (decision-maker; no warm path)

Use when connector paths are missing or stalled. Rewrite into Voice. Same four beats as the archived successful cold pattern, without locking to a sales story: (1) edge + one proof point that fits their world, (2) one checkable company reason, (3) low-pressure line + ask how they are thinking about the gap they own, (4) 15 to 20 minute ask. Target the owner of the problem (any function), not HR. Optional company-named CV only if they choose it (see rules above).

```text
Hi [Name], [1 to 2 sentences: the edge or thread that fits their world, with one concrete proof point from Profile when you have it]. [Optional location.]

[Company] is on my short list because [one specific, checkable reason: their round, a launch, a posting, an infra or ops move you can name].

Although I am in the job market, I'm not expecting that there is an opening. I'd like to hear how you're thinking about [that gap they own: product / eng / ops / GTM / etc.].

Would you have 15 to 20 minutes in the next couple of weeks?
```


### Bump (follow-up)

```text
Hey [Name], I just wanted to bump this in case it got buried. I'm still very interested in connecting if the timing works. It's no worries if not.
```

Cadence: ping → ~1 week → ping → ~2 weeks → final → stop.

### Process deflection (apply / recruiting redirect)

```text
Thanks [Name]. I appreciate you wanting to loop me in.

Before getting into the formal process, would you have 20 minutes for a quick call first? I want to make sure there's a real fit on both sides before taking up your team's time. I'm happy to work around your schedule.
```

### Deliberately leave out

- Resume / portfolio as the *ask* on first touch (warm paths: no attachment; cold: optional tailored CV only as accompaniment, never the point)
- Explicit “are you hiring?” or forward-to-HR / generic people@ inboxes
- Long credential lists (one fitting thread + the blurb do that work)
- Easy-out closers that invite them to decline
- Em dashes / en dashes
- Cold blasts when a usable connector still exists
- Assuming a sales/commercial title when the gap lives in another function

If there’s an opening, they’ll often mention it. Don’t lead with that.

## When to leave (first pass)

Once at least one conversation is **Outreach sent** (or further), move into Phase 6 (due board / bumps / prep / outcomes) or return to Phase 3/4 to refill. No “ready for Phase 6?” ask. Momentum over a full outreach batch. If anything is already due on Next Step Date, prefer Phase 6 first.

## When to return

New Select people, post-intro drafts after an intro lands, cold-direct drafts when warm stalls, bumps, process deflection, or refill after capacity frees up.

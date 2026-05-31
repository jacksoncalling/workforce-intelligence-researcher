# /market-signal

A 5-minute post-session routine for coaches. Run this after any session where you noticed something about how the labor market is behaving — not about the coachee personally, but about what the market did to them or around them.

---

## Prompt

You are helping a career coach capture a market observation after a coaching session. Guide them through the following steps. Keep it conversational and quick — this should take 5 minutes maximum.

### Step 1: What did the market do?

Ask the coach:

"What did you notice about the labor market in this session? Not about your coachee personally — about how employers, platforms, or hiring processes behaved. Think about:
- How did employers respond (or not respond) to applications?
- What skills or qualifications were asked for that surprised you?
- What did the coachee report about salary, working conditions, or interview processes?
- Did anything contradict what you expected based on official data or prior experience?"

Wait for their response. If it is about the person (emotions, personal situation), gently redirect: "That is important for your coaching notes. For the market signal, focus on what the market DID — what behavior did you observe from the employer/platform/system side?"

### Step 2: Is this new or repeating?

Ask: "Is this the first time you have seen this, or have other coachees reported something similar? If similar — how many, and over what timeframe?"

This establishes confidence level:
- First time → Low confidence (single observation)
- 2-3 coachees → Low-Medium (emerging pattern)
- 4+ coachees over weeks → Medium (consistent pattern worth sharing)

### Step 3: Write the local entry

Write a market-intel entry to the coach's local workspace:

```
File: market-intel/eintraege/YYYY-MM-DD_[short-description].md

## Beobachtung: [one-line description]
Datum: YYYY-MM-DD
Branche: [industry]
Region: [city/region]
Anzahl Coachees: [how many reported similar]
Zeitraum: [over what period]

### Was ist passiert
[2-4 sentences — can include company names, specific details, context]

### Was bedeutet das fuer mein Coaching
[1-2 sentences — what will you do differently next time]
```

This entry stays PRIVATE in the coach's workspace. It can include names, companies, identifying details — it is for the coach's own pattern-building.

### Step 4: Share decision

Ask: "Is this observation worth contributing to the shared intelligence layer? Other coaches and the FuE team would see an anonymized version. You do not have to share — this is your choice."

If yes → run `/contribute-signal` next. The anonymized signal will be written directly to `G:\My Drive\workforce-intelligence-researcher\shared-intelligence\signals\` — the shared Google Drive folder visible to all coaches and the FuE researcher.
If no → done. The local entry still builds the coach's own market knowledge.

---

## Example interaction

**Coach:** "My coachee applied to 8 IT companies in Koeln. Got 3 first interviews within a week — really fast. But then after the second round at two of them, nothing. Total silence. She followed up twice, no response. The third one said 'we are restructuring the team' after she already did a case study for them."

**AI:** "That sounds like a hiring-funnel stall — fast start, then silence after round 2. Have you seen this before with other IT coachees?"

**Coach:** "Yes, actually. Two others in the last month. Both similar — fast interviews, then nothing."

**AI:** "Three coachees in one month with the same pattern gives this Medium confidence. Let me write your local entry..."

*[Writes entry to market-intel/eintraege/2026-05-28_it-funnel-stall-koeln.md]*

**AI:** "Done. This matches a pattern other coaches have also reported — there is already a sensing prompt about IT offer-stage stalls. Would you like to contribute an anonymized version to the shared layer?"

**Coach:** "Yes."

**AI:** "Running /contribute-signal..."

# /check-dashboard

A 1-minute morning routine for coaches. Shows the current state of the sensing network — what patterns are confirmed, what's emerging, what the FuE team is asking about, and where blind spots exist.

---

## Prompt

You are providing a coach with a quick intelligence briefing before their day starts. Read the latest pattern report from `shared-intelligence/patterns/` and any active sensing prompts from `shared-intelligence/sensing-prompts/`. Present a brief, scannable summary.

### Format

```
=== INTELLIGENCE DASHBOARD — [date] ===

CONFIRMED PATTERNS (act on these)
• [pattern 1 — one line + coaching implication]
• [pattern 2 — one line + coaching implication]

EMERGING (watch for these in your sessions)
• [pattern — one line + what to notice]

ACTIVE SENSING PROMPTS (FuE is asking)
• [prompt topic — what to ask your coachees]

BLIND SPOTS (sectors/regions we cannot see)
• [list of gaps]

YOUR CONTRIBUTION THIS MONTH: [X signals shared]
===
```

### Rules

- Maximum 20 lines. Coaches are between sessions — they have 60 seconds.
- Lead with what is actionable NOW (confirmed patterns affect today's sessions).
- Sensing prompts are invitations, not mandates. Frame as "if you see this, we'd love to know."
- Blind spots help coaches recognize when THEY are the only one sensing something — their observation is especially valuable.
- No jargon. No five-Ds labels unless the coach has asked for them. Plain language.

### Example output

```
=== INTELLIGENCE DASHBOARD — 2026-05-28 ===

CONFIRMED PATTERNS
• IT interviews go silent after round 2 — prepare coachees for longer timelines,
  help them maintain momentum during silence. (7+ coachees, 3 coaches)
• Nursing ghost-postings — verify positions are real before encouraging applications.
  Call Pflegedienstleitung directly. (5 coachees, 2 coaches)

EMERGING (watch for this)
• AI proficiency appearing in non-tech job descriptions (admin, marketing).
  If your coachee mentions this in interviews, we want to know.

FuE IS ASKING
• IT coaches: ask coachees about time-to-interview vs. time-to-offer.
  We see fast starts and stalled endings. Is this consistent?
  (Full prompt: sensing-prompts/2026-05_it-offer-stage.md)

BLIND SPOTS — we have ZERO signals from:
  Retail, Logistics, Green/Sustainability, Handwerk
  → If you have coachees in these sectors, any observation is valuable.

YOUR CONTRIBUTIONS THIS MONTH: 2 signals shared. Thank you.
===
```

---

## When to run

- Start of day (before first session)
- After receiving a notification that a new pattern report was published
- When starting with a coachee in a sector you haven't worked in before (check if there are relevant patterns or blind spots)

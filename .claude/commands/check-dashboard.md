# /check-dashboard

A 1-minute intelligence briefing. Run this to see the current state of the sensing network — confirmed patterns, emerging signals, active sensing prompts, and blind spots.

---

## Prompt

You are the Workforce Intelligence Researcher for DAA NRW FuE. Read the following in order:

1. The most recent pattern report in `shared-intelligence/patterns/`
2. All active sensing prompts in `shared-intelligence/sensing-prompts/`
3. Any signal files in `shared-intelligence/signals/` dated after the last pattern report

Then produce this briefing — maximum 20 lines, plain language, no jargon:

```
=== INTELLIGENCE DASHBOARD — [date] ===

CONFIRMED PATTERNS (act on these)
• [pattern — one line + coaching implication]

EMERGING (watch for these in sessions)
• [pattern — what to notice]

ACTIVE SENSING PROMPTS (FuE is asking)
• [topic — what coaches should ask coachees]

BLIND SPOTS (sectors/regions with zero signals)
• [list]

NEW SINCE LAST COMPOUND: [X signals]
===
```

Rules:
- Lead with what is actionable NOW.
- Sensing prompts are invitations, not mandates.
- Blind spots remind coaches that their lone observation is especially valuable.
- If new signals have arrived since the last compound, flag them: "X new signals waiting — run /compound to synthesize."

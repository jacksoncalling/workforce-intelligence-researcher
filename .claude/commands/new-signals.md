# /new-signals

Check what has arrived in the shared intelligence layer since the last compound. Run this before deciding whether to synthesize.

---

## Prompt

You are the Workforce Intelligence Researcher for DAA NRW FuE.

1. Find the most recent pattern report in `shared-intelligence/patterns/` and note its date.
2. Read all files in `shared-intelligence/signals/` dated after that report.
3. If no pattern report exists yet, treat all signals as new.

Then output:

```
=== NEW SIGNALS — [today's date] ===

[N] signals arrived since last compound ([last compound date])

1. [YYYY-MM-DD] [Signal title — one line summary] — [industry / region] — Confidence: [low/medium/high]
2. [YYYY-MM-DD] ...
...

READY TO SYNTHESIZE? Run /compound to generate a pattern report and update the dashboard.
===
```

If no new signals have arrived: "No new signals since [date]. Nothing to compound yet."

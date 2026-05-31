# Routines

Runnable research prompts. Each file is a self-contained prompt that can be:
- Copy-pasted into a Claude Project conversation
- Scheduled via Claude Code (`/schedule`)
- Triggered by a script, GitHub Action, or Power Automate flow

## How to use

Open the routine file. Copy the full text. Paste it as a message to the researcher. The prompt contains everything the agent needs — what to do, where to look, where to write output.

## Scheduled routines

| File | Frequency | Purpose |
|------|-----------|---------|
| `weekly-iab-scan.md` | Every Monday | Scan IAB for new publications relevant to the five Ds |
| `weekly-ba-check.md` | Every Monday | Check BA Statistik for labor market changes in NRW |
| `monthly-signal-compound.md` | 1st Monday of month | Synthesize all new coach signals into pattern report |
| `monthly-policy-scan.md` | 15th of month | Scan policy sources for regulatory changes |
| `quarterly-full-compound.md` | 1st week of quarter | Full review of what the system has learned |

## Event-triggered routines

| File | Trigger | Purpose |
|------|---------|---------|
| `new-signal-triage.md` | New signal arrives | Cross-reference against existing patterns |
| `project-landscape-scan.md` | New FuE project starts | Produce initial briefing from existing intelligence |
| `anomaly-deep-dive.md` | Coach flags something unusual | Investigate: local phenomenon or emerging trend? |

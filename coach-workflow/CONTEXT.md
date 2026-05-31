# Coach Workflow

How coaches interact with the sensing system. These files define the slash commands and routines that make signal contribution a 5-minute task, not a research project.

## Available workflows

| File | Trigger | Time | Purpose |
|------|---------|------|---------|
| `market-signal.md` | After a session with market observations | 5 min | Write a local market-intel entry + decide whether to share |
| `contribute-signal.md` | After local entry exists | 2 min | Anonymize and push a signal to the shared layer |
| `session-takeaway.md` | End of session | 3 min | Capture tips, corrections, resources for the coachee's personal folder |
| `check-dashboard.md` | Between sessions / start of day | 1 min | Read the current intelligence dashboard |

## How this connects to the sensing hierarchy

```
Coach finishes session
        ↓
/market-signal  →  writes to coach's local market-intel/eintraege/
        ↓                                    ↓
Coach decides: "Is this worth sharing?"    /session-takeaway  →  writes tips, corrections,
        ↓ (yes)                               resources to clients/[coachee]/takeaways/
/contribute-signal  →  anonymizes +           ↓
  writes to shared-intelligence/signals/    Over 2-5 sessions, takeaway folder fills up
        ↓                                    ↓
Researcher compound routine                /build-coachee-paket (Phase 2) →
        ↓                                    compiles into personal package
Pattern report + dashboard update            for coachee to keep
        ↓
Coach reads dashboard  ←  /check-dashboard
```

### Two directions from every session

- **Upward** (`/market-signal` → `/contribute-signal`): What the market is doing → shared intelligence → organizational learning
- **Downward** (`/session-takeaway`): What the coach gave → coachee's personal folder → their independent job search

## Principles

- Signal contribution is VOLUNTARY. No coach is required to share.
- The workflow guides anonymization — the coach makes the judgment call.
- 5 minutes maximum. If it takes longer, the workflow is broken.
- The coach's local entry (in their private workspace) keeps full context. Only the anonymized version goes shared.

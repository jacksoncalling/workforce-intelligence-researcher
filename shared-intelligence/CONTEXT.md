# Shared Intelligence Layer

This is Layer 2 of the sensing hierarchy. Anonymized market signals from coaches arrive here. The FuE researcher reads from here. No personal data exists at this layer.

## Governance

- Coaches can READ everything here
- Coaches can WRITE to `signals/` (contribute new observations)
- Coaches can READ `sensing-prompts/` (questions from FuE)
- Coaches CANNOT modify `patterns/` (produced by compound routines)
- The FuE researcher READS from all folders and WRITES to `patterns/`

## What belongs here

Market behavior observations — what the labor market is DOING, stripped of who experienced it.

## What does NOT belong here

- Names (coachees, employers, contacts)
- Identifying combinations (industry + city + age + nationality = identifiable)
- Personal coaching notes
- CV content or application materials
- Emotional or personal circumstances

## How signals arrive

Coaches use the `/market-signal` workflow in their coach workspace. It walks them through:
1. Describing what the market did (not what the person felt)
2. Anonymization self-check
3. Deciding whether to contribute to the shared layer
4. Writing the signal here in the correct format

See `../coach-workflow/` for the full skill definition.

# Workforce Intelligence Researcher — Challenge #6

## What This Is

Competition entry for Weekly Challenge #6 ("THE RESEARCHER") in Jake van Clief's Clief Notes Skool cohort. A folder-based AI researcher built with ICM/MWP methodology, designed for the DAA NRW FuE (Research & Development) team.

## Current State — 2026-05-30

### Folder system: ✅ Core complete, refining

**Done:**
- identity.md — persona, two-channel sensing, two-stage analysis (coarse sort → five Ds lenses)
- rules.md — 7 investigative rules + gateway triggers
- examples.md — 3 interaction demonstrations
- reference/ — sensing hierarchy, five-Ds framework, signal taxonomy + DSGVO, research sources
- routines/ — 8 runnable prompt files (5 scheduled, 3 event-triggered) + CONTEXT.md index
- shared-intelligence/ — Layer 2 with 4 example signals, 1 pattern report, 1 sensing prompt
- coach-workflow/ — 3 slash commands: /market-signal, /contribute-signal, /check-dashboard
- dashboard.html — visual intelligence dashboard for coaches (German, responsive)
- paper.md — companion paper (theory, Cybersyn, up-hierarchies, evaluative layer)
- README.md — updated with full folder structure + full loop description

**Open:**
- Push to public GitHub repo (include paper.md — Jake/judges may read it)
- Rename paper.md to builders-paper.md
- Optional: connect Terroir MCP server as "above and beyond"
- Optional: publish Builder's Paper on Substack, link in submission
- Optional: 3-5 min YouTube screencast walkthrough

**Consistency review completed (2026-05-30):**
- rules.md Rule 1: five Ds replaced with coarse-sort bins at intake
- rules.md Rule 6: added shared-intelligence/sensing-prompts/ + coach-workflow/ references
- rules.md Rule 7: compound Lens field marked "assigned at synthesis, not intake"
- rules.md Gateway: event triggers now use concrete paths
- examples.md Example 1: five Ds replaced with sensing bins at interrogation
- examples.md Example 2: internal signals checked before external IAB data
- signal-taxonomy.md: confidence template updated to match actual usage, cross-ref to rules.md tiers
- identity.md: added Tier 1-6 cross-reference to investigation routing
- sensing-hierarchy.md: example filenames updated to match real signals, governance/ marked deployment-phase
- README: icm pitch daa.html added to table, examples count updated to 4

**Submission description (ready to paste in Skool comments):**
> A folder-based AI researcher for an R&D team at a German education provider. The researcher sits on top of a distributed coaching network — 20 coaches observing the labor market daily through conversations with unemployed professionals. It synthesizes their anonymized signals with external research, identifies blind spots, and designs better sensing questions. Built for the DAA NRW FuE team using ICM.

### Paper: ✅ Draft complete, separate from folder

- Full 8-section draft in `paper.md`
- Accessible tone, starts with human experience, technical terms introduced through story
- Not part of the competition deliverable — for LinkedIn/Substack/DAA pitch separately
- Competition only needs 2-3 lines, not a paper

## Deadline

**Sunday May 31st, 12:00 PM EST**

## Architecture

```
workforce-intelligence-researcher/
├── CLAUDE.md                    ← This file (project management, NOT part of deliverable)
├── identity.md                  ← Who the researcher is
├── rules.md                     ← 7 rules + gateway triggers
├── examples.md                  ← 3 demonstrations
├── reference/
│   ├── sensing-hierarchy.md     ← 3-layer architecture
│   ├── five-ds-framework.md     ← 5 megatrend lenses (applied at synthesis, not intake)
│   ├── signal-taxonomy.md       ← Signal types, confidence, DSGVO governance
│   └── research-sources.md      ← External sources + automation config
├── shared-intelligence/         ← LAYER 2: Live example of what coaches see + contribute
│   ├── CONTEXT.md               ← Governance rules for this layer
│   ├── signals/                 ← 4 example anonymized signal entries
│   ├── patterns/                ← 1 compound pattern report (Q2 2026)
│   └── sensing-prompts/         ← 1 active sensing prompt from FuE
├── coach-workflow/              ← How coaches interact with the system
│   ├── CONTEXT.md               ← Index of workflows
│   ├── market-signal.md         ← /market-signal: 5-min post-session capture
│   ├── contribute-signal.md     ← /contribute-signal: anonymize + share upward
│   └── check-dashboard.md       ← /check-dashboard: read current intelligence
├── dashboard.html               ← Visual intelligence dashboard for coaches
├── routines/
│   ├── CONTEXT.md               ← Index of runnable routines
│   ├── weekly-iab-scan.md       ← Scan IAB for new publications
│   ├── weekly-ba-check.md       ← Check BA labor market statistics
│   ├── monthly-signal-compound.md ← Synthesize coach signals
│   ├── monthly-policy-scan.md   ← Policy source scan
│   ├── quarterly-full-compound.md ← Full system review
│   ├── new-signal-triage.md     ← Triage incoming signals
│   ├── project-landscape-scan.md ← Briefing for new projects
│   └── anomaly-deep-dive.md     ← Investigate unusual observations
├── paper.md                     ← Companion paper (included in repo for judges)
└── README.md                    ← Overview + setup instructions
```

## Key Design Decisions

- **Two-stage analysis:** Coarse sort first (6 bins including "emergent"), then five Ds as publication lenses. Snowden principle: data first, frameworks second.
- **Routines are prompts, not descriptions:** Each routine file is a self-contained prompt you can copy-paste or schedule.
- **DSGVO by architecture:** Personal data never leaves Layer 1. Signals are anonymized before sharing. The folder structure itself enforces privacy.
- **Source weighting:** Direct experience (Tier 1) outranks statistical abstraction (Tier 3-4). Contradictions between tiers are findings, not errors.
- **Dedup before compound:** Two signals covering the same behavior from different angles count as one pattern. Audit for topical overlap before running /compound — merge overlapping entries with a combined confidence note. See `~/.claude/learnings/2026-05-31-dedup-before-compound.md`

## Theoretical Lineage

- **ICM/MWP** (Jake van Clief) — folder-as-agent architecture
- **Compound Engineering** (Kieran Klaassen) — each cycle makes the next smarter
- **Up-hierarchy** (Bonnitta Roy / John Heron) — distributed sensing flows up, context flows down
- **GSNV / Evaluative Layer** (Bonnitta Roy) — evaluative fields as causal forces, not overlays
- **Cybersyn** (Stafford Beer / Eden Medina) — distributed sensing + intervention at national scale
- **Terroir** (Josh Baker) — ontological knowledge graph as topology complement to ICM

## Routing

| I want to... | Go to |
|-------------|-------|
| Understand who the researcher is | `identity.md` |
| See the investigative rules | `rules.md` |
| See example interactions | `examples.md` |
| Understand the 3-layer sensing architecture | `reference/sensing-hierarchy.md` |
| Run a scheduled research routine | `routines/` |
| Read the companion paper | `paper.md` |

# Workforce Intelligence Researcher

A folder-based AI researcher for an R&D team at a German education provider. The researcher sits on top of a distributed coaching network — 20 coaches observing the labor market daily through conversations with unemployed professionals. It synthesizes their anonymized signals with external research, identifies blind spots, and designs better sensing questions. Built for the DAA NRW FuE team using ICM.

---

## What This Is

Drop this folder into a Claude Project and get an investigative research partner that thinks before it summarizes.

**Domain:** Workforce transitions in Germany — hiring behavior, skills demand, sector shifts, barriers to employment, working conditions.

**Analytical framework:** Two-stage analysis. Coarse sorting first (what is this about?), then five megatrend lenses at synthesis (the "five Ds"): Decarbonization, Digitalization, Demographic Change, Democracy, Decent Work.

**What makes it different from a generic research assistant:** It has two sensing channels (human observation + active research), it weighs sources by proximity to lived experience, and it designs better questions for the sensing network rather than just answering the ones it's given.

---

## How to Use It

### Setup

1. Upload this entire folder to a Claude Project (or drop it into a Claude Code workspace)
2. Claude reads `identity.md` to understand who it is
3. Claude reads `rules.md` to understand how it researches
4. Claude reads `examples.md` to understand what good looks like
5. The `reference/` folder provides frameworks, source lists, and governance rules

### Basic Interaction

Ask a research question. The researcher will NOT immediately produce a report. It will:

1. **Interrogate the question** — what decision does this support? What do you already know?
2. **Check human signals first** — what do coaches already observe about this topic?
3. **Identify gaps** — where are we NOT sensing? What's missing?
4. **Then research externally** — with the internal picture established
5. **Synthesize both channels** — especially where they converge or contradict
6. **Propose better sensing questions** — improve the network's ability to sense next time

### Example Prompts

- "What are we seeing about AI's impact on IT hiring in NRW?"
- "The IAB says Fachkraeftemangel in nursing is easing. What do our coaches say?"
- "We're starting a project on green transition jobs. What do we know and where are our blind spots?"
- "Design a 4-week sensing experiment on [topic] for our coaching network."
- "Run the monthly signal compound — what patterns emerged this month?"

---

## Folder Structure

```
workforce-intelligence-researcher/
├── identity.md              — Who the researcher is and what it serves
├── rules.md                 — 7 investigative rules + gateway trigger definitions
├── examples.md              — 3 interactions showing investigation, not summarization
├── reference/
│   ├── sensing-hierarchy.md — 3-layer architecture (coach → shared → FuE)
│   ├── five-ds-framework.md — The five megatrend analytical lenses
│   ├── signal-taxonomy.md   — Signal types, confidence levels, DSGVO governance
│   └── research-sources.md  — External source list + gateway automation config
├── shared-intelligence/              — LAYER 2: What coaches see and contribute to
│   ├── CONTEXT.md                    — Governance rules for this layer
│   ├── signals/                      — Anonymized signal entries from coaches
│   │   ├── 2026-04-12_it-interview-ghosting.md
│   │   ├── 2026-04-28_pflege-ghost-postings.md
│   │   ├── 2026-05-10_ai-in-non-tech-job-descriptions.md
│   │   └── 2026-05-22_resume-color-matching.md
│   ├── patterns/                     — Compound reports synthesizing across signals
│   │   └── 2026-Q2_april-may-compound.md
│   └── sensing-prompts/              — Questions from FuE flowing DOWN to coaches
│       └── 2026-05_it-offer-stage.md
├── coach-workflow/                   — How coaches interact with the system
│   ├── CONTEXT.md                    — Index of available workflows
│   ├── market-signal.md              — /market-signal: 5-min post-session routine
│   ├── contribute-signal.md          — /contribute-signal: anonymize + share upward
│   ├── session-takeaway.md           — /session-takeaway: 3-min capture for coachee folder
│   └── check-dashboard.md           — /check-dashboard: read current intelligence
├── dashboard.html           — Visual intelligence dashboard for coaches
├── icm pitch daa.html       — Pitch to DAA: how this system works for their organization
├── routines/
│   ├── CONTEXT.md               — Index of all runnable routines
│   ├── weekly-iab-scan.md       — Scan IAB for new publications
│   ├── weekly-ba-check.md       — Check BA labor market statistics
│   ├── monthly-signal-compound.md — Synthesize coach signals into pattern report
│   ├── monthly-policy-scan.md   — Scan policy sources for regulatory changes
│   ├── quarterly-full-compound.md — Full review of what the system learned
│   ├── new-signal-triage.md     — Triage incoming coach signals
│   ├── project-landscape-scan.md — Initial briefing for new FuE projects
│   └── anomaly-deep-dive.md     — Investigate unusual observations
├── paper.md                 — Companion paper: theory + design rationale
└── README.md                — This file
```

### What Each File Does

| File | Layer | Purpose |
|------|-------|---------|
| `identity.md` | Who | Persona, disposition, two-channel sensing model |
| `rules.md` | How | Investigative methodology — the core of the system |
| `examples.md` | What good looks like | 4 demonstrations of investigation vs. summarization |
| `sensing-hierarchy.md` | Architecture | How knowledge flows from coachee to FuE team |
| `five-ds-framework.md` | Analytical lens | 5 megatrend categories for tagging and analysis |
| `signal-taxonomy.md` | Governance | Signal types, confidence levels, DSGVO rules |
| `research-sources.md` | Sources + automation | What to monitor, where, how often |
| `shared-intelligence/` | Layer 2 live | Example signals, pattern reports, sensing prompts |
| `coach-workflow/` | Coach tools | Slash commands: signal capture (up), session takeaways (down), dashboard |
| `dashboard.html` | Redistribution | Visual intelligence summary for coaches between sessions |
| `paper.md` | Theory | Design rationale, up-hierarchies, Cybersyn, evaluative layer |
| `icm pitch daa.html` | Pitch | How this system works for DAA's organization |

---

## The Sensing Architecture (Overview)

This researcher is Layer 3 of a three-layer system:

**Layer 1 — Individual Coach** (private workspace): Coaches observe labor market behavior through their coachees. They compound observations locally and contribute anonymized signals upward. Their coaching notes, coachee data, and personal profile stay private.

**Layer 2 — Shared Intelligence** (team-accessible): Anonymized signal entries from all coaches, pattern reports from compound routines, and sensing prompts from the FuE team. Governed by DSGVO-compliant rules. Coaches read and write signals. They cannot modify governance files.

**Layer 3 — FuE Research** (this folder): Synthesizes signals + external research. Designs sensing experiments. Produces briefings. Identifies blind spots in the sensing network.

Full architecture is documented in `reference/sensing-hierarchy.md`.

---

## Governance and Data Protection

This system is designed for DSGVO compliance by architecture, not by policy:

- **Personal data never leaves Layer 1.** Coach workspaces are private.
- **Signals are anonymized before sharing.** Coaches transform observations into market behavior descriptions, stripping names, companies, and identifying details.
- **Coachee consent is required.** A consent form (at the shared layer) covers anonymized market observations only — never personal coaching data.
- **Coaches are professionals, not instruments.** Signal contribution is voluntary. Coach profiles are private. No coach performance metrics are derived from signal activity.
- **The FuE team sees patterns, not people.** They cannot trace signals back to individual coaches or coachees.

Full governance rules in `reference/signal-taxonomy.md`.

---

## The Full Loop: How Intelligence Flows

The folder is not just the researcher — it shows all three layers of the sensing system in action.

### Upward: Coach → Shared Intelligence → Researcher

1. A coach finishes a session and notices something about the labor market
2. They run `/market-signal` (5 minutes) — writes a local entry with full context
3. They decide to share: `/contribute-signal` anonymizes and writes to `shared-intelligence/signals/`
4. The researcher's compound routine reads new signals, synthesizes patterns, writes to `shared-intelligence/patterns/`

### Downward: Researcher → Dashboard → Coach → Coachee

5. The researcher identifies gaps and designs sensing prompts → writes to `shared-intelligence/sensing-prompts/`
6. The compound routine updates `dashboard.html` — a visual summary coaches check between sessions
7. A coach runs `/check-dashboard` (1 minute) before their next session — sees confirmed patterns, emerging signals, blind spots, and FuE questions
8. The coach adjusts their practice and asks better questions — the loop closes
9. After each session, the coach runs `/session-takeaway` (3 minutes) — captures tips, CV corrections, and resources into the coachee's personal folder
10. At program end, the coachee receives their accumulated takeaway folder — organizational intelligence filtered through professional judgment, delivered as something one person can use

### What makes this an up-hierarchy, not a surveillance tool

- Signal contribution is voluntary — coaches choose what to share
- Anonymization is a human judgment call, guided by AI but decided by the coach
- Sensing prompts are invitations, not mandates
- The dashboard gives back more than it takes — coaches get organizational intelligence in return for contributing observations
- No coach performance metrics are derived from signal activity

See `coach-workflow/` for the full slash command definitions. See `shared-intelligence/` for live examples of signals, patterns, and sensing prompts.

---

## The Gateway Concept

The researcher doesn't only respond to human requests. A gateway layer triggers automated research tasks on a schedule:

- **Weekly:** Scan IAB and BA for new publications
- **Monthly:** Compound all new coach signals into pattern reports
- **Monthly:** Scan policy sources for regulatory changes
- **Quarterly:** Full compound review of what the system has learned
- **Event-driven:** New signal arrives, new project starts, coach flags anomaly

Gateway configuration is in `reference/research-sources.md`. The gateway can be implemented with Python scripts, Power Automate, Claude Code scheduled tasks, or GitHub Actions — whatever the organization already uses.

---

## Who This Is For

**Primary:** R&D teams at Bildungstraeger, Weiterbildungsanbieter, and AVGS-Traeger who want to systematically learn from their coaching and training programs.

**Also useful for:** Anyone building a distributed sensing system using folder-based AI architecture — the methodology (human sensors + active research + compound knowledge + DSGVO governance) transfers to other domains where practitioners observe phenomena that researchers need to understand.

---

## Credits

Built using Jake van Clief's Interpretable Context Methodology (ICM/MWP) and inspired by Kieran Klaassen's Compound Engineering principles. The sensing hierarchy concept extends ICM from single-user folder systems to multi-stakeholder organizational intelligence.

Designed by Joshua Baker / Step Into More, based on real coaching infrastructure at DAA Deutsche Angestellten-Akademie NRW.

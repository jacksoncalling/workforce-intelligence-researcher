# Sensing Hierarchy: Three-Layer Architecture

This document describes how workforce intelligence flows through the organization — from individual coaching sessions to organizational research. It is the backbone of the distributed sensing system.

---

## The Three Layers

```
Layer 3: FuE Research Team          ← synthesizes, designs experiments
         reads from: shared layer + external research
         writes to: research outputs, sensing prompts, policy briefings

Layer 2: Shared Intelligence        ← anonymized signals, cross-coach patterns  
         reads from: coach contributions
         writes to: pattern reports, compound summaries
         
Layer 1: Individual Coach           ← observes, compounds locally, contributes upward
         reads from: coachee sessions
         writes to: local market-intel, anonymized signals to shared layer
```

---

## Layer 1: The Individual Coach

**Location:** Personal OneDrive or local filesystem (private to each coach)

**What lives here:**
- `coach-profile.md` — the coach's style, expertise, quality standards, AI delegation rules
- `clients/` — individual coachee folders with session notes, CV drafts, protocols (NEVER shared)
- `market-intel/eintraege/` — raw market observations from coachee conversations

**How it compounds:** After each session, the coach runs a market learning routine (5-minute structured conversation). This captures what the coachee is experiencing in the labor market — not their personal story, but the market behavior they observe. Over 10-20 coachees, the coach builds a picture of their local/industry labor market from first-hand accounts.

**What flows upward:** The coach decides when a market observation is worth sharing. They write an anonymized signal entry — stripping names, specific companies, identifying details — and contribute it to the shared layer. This is an active choice, not automatic extraction.

**What stays private:** Everything in `clients/`. Session notes, personal coachee data, individual protocols. These never leave the coach's workspace. The DSGVO consent form covers only the anonymized market observation, not the personal coaching relationship.

**Coach autonomy:** Each coach owns their `coach-profile.md`. They define their style, their AI rules, their quality standards. The organization provides templates but does not mandate content. The coach is a professional, not a data collection instrument.

---

## Layer 2: Shared Intelligence

**Location:** SharePoint Team Site or shared OneDrive folder (accessible to all coaches in a division + FuE team read access)

**What lives here:**
```
shared-intelligence/
├── CONTEXT.md                    ← rules for this layer: what goes here, what stays private
├── signals/                      ← individual anonymized signal entries from coaches
│   ├── 2026-04-12_it-interview-ghosting.md
│   ├── 2026-04-28_pflege-ghost-postings.md
│   ├── 2026-05-10_ai-in-non-tech-job-descriptions.md
│   └── ...
├── patterns/                     ← compound reports synthesizing across signals
│   └── 2026-Q2_april-may-compound.md
├── sensing-prompts/              ← questions the FuE team asks coaches to investigate
│   └── 2026-05_it-offer-stage.md
└── governance/                   ← (deployment phase: added when system goes live at DAA)
    ├── consent-template.md       ← DSGVO-compliant consent form for coachees
    ├── anonymization-rules.md    ← how to strip identifying information
    ├── coach-rights.md           ← what coaches can and cannot change at this layer
    └── data-retention.md         ← how long signals are stored, when they are archived
```

**Governance at this layer:**
- Coaches can READ everything in the shared layer
- Coaches can WRITE to `signals/` (contribute new observations using `/contribute-signal`)
- Coaches can READ `sensing-prompts/` (research questions from FuE)
- Coaches CANNOT modify `governance/` files — these are set by the organization
- Coaches CANNOT modify `patterns/` — these are produced by the FuE team or by scheduled compound routines
- The FuE team can READ everything but does not see Layer 1 data

**Why this layer matters:** It is where individual observations become organizational knowledge. One coach seeing ghosting in IT is an anecdote. Five coaches across three cities seeing the same pattern is intelligence.

---

## Layer 3: FuE Research Team

**Location:** FuE team SharePoint or dedicated research workspace

**What lives here:** This researcher folder. The FuE team uses the researcher AI to:
- Synthesize signals from the shared layer
- Cross-reference with external research (IAB, BA, EU sources)
- Design sensing experiments (new questions for coaches)
- Produce briefings for organizational leadership
- Identify blind spots in the sensing network

**What the FuE team sees:**
- Anonymized signals and pattern reports from the shared layer
- External research they conduct themselves
- Compound knowledge from previous research sessions

**What the FuE team does NOT see:**
- Individual coach profiles (unless the coach shares voluntarily)
- Coachee personal data (never — by design and by law)
- Which coach contributed which signal (signals can be attributed to region/industry but not to individual coaches, preserving coach autonomy)

---

## How Knowledge Flows

```
Coachee tells coach:        "I applied to 12 companies, got 4 interviews,
                             but all 4 went silent after the second round."

Coach observes pattern:      This is the 3rd IT coachee this month reporting
                             interview ghosting after second round.

Coach writes local entry:    market-intel/eintraege/2026-05-20_it-ghosting.md
                             (includes coachee context, specific companies — private)

Coach writes shared signal:  shared-intelligence/signals/2026-05-20_it-ghosting-pattern.md
                             (anonymized: "Multiple IT-sector coachees in NRW report...")

FuE researcher reads signal: Cross-references with BA data on IT vacancies.
                             BA says IT vacancies are rising.
                             Coaches say interviews happen but offers don't.
                             Contradiction = finding.

FuE produces briefing:       "IT hiring funnel is breaking at the offer stage.
                             Possible causes: budget freezes, AI uncertainty,
                             compliance-driven posting. Recommend: sensing prompt
                             to coaches asking about offer-stage stalls specifically."

FuE writes sensing prompt:   shared-intelligence/sensing-prompts/2026-06_it-offer-stalls.md
                             Coaches read this and ask their next IT coachees
                             specifically about offer-stage behavior.
```

The loop closes. Each cycle makes the system smarter.

---

## Technical Implementation Options

### Option A: OneDrive + SharePoint (Recommended for DAA)

- Coaches already have Microsoft 365
- Personal OneDrive = Layer 1 (private by default)
- SharePoint Team Site = Layer 2 (shared with permissions)
- SharePoint permissions enforce governance (coaches can't edit governance/ folder)
- FuE team gets read access to shared layer via SharePoint permissions
- No new tools required

### Option B: Git-based (More Technical, Better Audit Trail)

- Private repos per coach (Layer 1)
- Shared repo for division (Layer 2) with branch protection
- Pull request model: coach "submits" a signal, DSGVO review before merge
- Full version history, diff-able changes
- Requires technical comfort most coaches won't have

### Option C: Hybrid

- Coaches work in OneDrive (familiar)
- Monthly compound script exports anonymized signals to a Git repo
- FuE team works from the Git repo
- Best of both worlds but requires a bridge script

The right choice depends on the organization's technical maturity and the coaches' comfort level. For DAA, Option A is the realistic starting point. Option C is the target state.

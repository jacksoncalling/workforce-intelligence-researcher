# Signal Taxonomy and DSGVO Governance

This document defines what a signal is, how signals are classified, and what governance rules protect personal data at every layer of the sensing hierarchy.

---

## What Is a Signal

A signal is an anonymized, structured observation about labor market behavior derived from coaching interactions. It is NOT:
- A case study of a person
- A session summary
- A data point about a coachee
- An opinion or prediction

A signal describes what the market is DOING, as observed through the experience of people navigating it.

**Good signal:** "Three coachees in IT-Consulting (NRW) report that second-round interviews are being cancelled or going silent, despite positive first rounds. Pattern emerged in Q1 2026."

**Bad signal:** "Maria K., 34, software developer from Syria, applied to SAP and got ghosted." (This is personal data, not a market signal.)

---

## Signal Classification

### By Type

| Type | Description | Example |
|------|------------|---------|
| Hiring behavior | How employers act during the hiring process | "Ghosting after second round," "unpaid Probearbeiten requests" |
| Skills demand | What qualifications or competencies are being asked for | "AI tool proficiency in non-tech job descriptions" |
| Platform behavior | How job platforms and intermediaries function | "Indeed algorithm favoring recent uploads," "Xing declining vs. LinkedIn" |
| Salary signal | What compensation looks like in practice vs. posting | "Posted salaries 15-20% below actual negotiation outcomes" |
| Sector shift | Movement of work between industries or roles | "Marketing professionals moving into sustainability communications" |
| Barrier pattern | Systematic obstacles certain groups face | "Credential recognition taking 8+ months for nursing" |
| Condition signal | Working conditions as reported by those experiencing them | "Befristung as default in academia even for senior positions" |

### By Confidence Level

| Level | Criteria | Minimum Evidence |
|-------|----------|-----------------|
| Low | Single coach, single observation | 1 signal from 1 coach |
| Medium | Multiple observations from one coach OR single observations from multiple coaches | 3+ consistent signals |
| High | Multiple coaches across locations reporting consistent pattern | 5+ signals from 3+ coaches |
| Confirmed | Corroborated by both human sensing AND external research | Human + statistical alignment |

Confidence levels classify the strength of coach-contributed signals. For how to weigh signals against external research sources (academic papers, statistics, policy documents), see the Tier 1–6 source hierarchy in `rules.md` Rule 3.

### By Freshness

| Age | Status | Action |
|-----|--------|--------|
| < 3 months | Current | Active use in research |
| 3-6 months | Aging | Verify before citing |
| 6-12 months | Historical | Context only, not current evidence |
| > 12 months | Archived | Move to archive, flag if still being cited |

---

## DSGVO Governance Rules

### Principle: Privacy by Architecture

The folder structure itself enforces data protection. Personal data exists only at Layer 1 (coach's private workspace). By the time information reaches Layer 2 (shared intelligence), it has been transformed into anonymized market observations. Layer 3 (FuE research) sees only patterns, never people.

### Coachee Consent

Before any market observation can be contributed to the shared layer, the coachee must have signed the consent form (see `governance/consent-template.md` at the shared layer).

The consent covers:
- Anonymized observations about their labor market experience may be shared within the organization
- Their name, employer names, and identifying details will NOT be shared
- They can withdraw consent at any time (signals already contributed remain, as they contain no identifying information)
- The purpose is organizational learning to improve coaching quality for future participants

The consent does NOT cover:
- Sharing personal coaching notes
- Sharing CV content or application materials
- Sharing personal circumstances (family, health, financial)
- Any external sharing outside the organization

### Anonymization Rules

When a coach transforms a local observation into a shared signal, they must:

1. **Remove names** — coachee, employers, contacts, references
2. **Generalize geography** — "NRW" not "Aachen-Eilendorf," unless the region is large enough
3. **Generalize demographics** — "international candidate with engineering background" not "Syrian engineer, 34, arrived 2021"
4. **Aggregate where possible** — "3 of my recent IT coachees" not individual descriptions
5. **Focus on market behavior** — what the market did, not what the person experienced emotionally
6. **Self-check** — "Could someone reading this identify the person?" If yes, generalize further.

### Coach Privacy

Coaches are professionals contributing to organizational learning. They are NOT being monitored.

- Signal contributions are voluntary, not mandatory
- Coaches choose WHAT to share and WHEN
- Signal entries at the shared layer can be attributed to region/industry but NOT to individual coaches (unless the coach chooses to sign their contribution)
- Coach-profile.md remains private to each coach — the organization provides templates, not mandates
- The FuE team sees patterns, not coach performance metrics
- No coach should feel that the sensing system is a surveillance tool

### Data Retention

- Active signals: retained as long as they are current (< 12 months)
- Archived signals: moved to `signals/archiv/`, retained for trend analysis
- Pattern reports: retained indefinitely (they contain no personal data)
- Coachee consent forms: retained at Layer 1 (coach's workspace) per DSGVO retention requirements
- Right to erasure: a coachee can request that their consent be withdrawn and any signal entries reviewed. Since signals are anonymized, the coachee's identity cannot be connected to specific entries — but the coach can verify and remove if needed.

---

## Signal Entry Template

This template is for coach-contributed signals. For researcher-produced compound entries after a research session, see `rules.md` Rule 7.

```markdown
## Signal: [one-line description of the market behavior observed]

**Date:** YYYY-MM-DD
**Region:** [NRW / Ruhrgebiet / Rheinland / national / EU]
**Industry:** [IT / Pflege / Manufacturing / Retail / Administration / ...]
**Type:** [hiring-behavior / skills-demand / platform-behavior / salary-signal / sector-shift / barrier-pattern / condition-signal]
**Lens:** [which of the five Ds — assigned at synthesis, can be multiple]
**Confidence:** [low / medium / high] (brief evidence note: e.g. "3 coaches, 7 coachees")

### Observation
[2-4 sentences describing the pattern. No identifying details. Focus on what the market is doing.]

### Context
[What makes this noteworthy? Is it new? Does it confirm or contradict existing patterns?]

### Coaching Implication
[How should this affect coaching practice? What should coaches do differently?]
```

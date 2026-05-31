# Research Sources and Automated Channels

This document configures the researcher's external sensing — the active research channel that complements the human sensing network. It defines what to monitor, where to find it, and how often to check.

---

## Channel A: Human Sensing (Internal)

These are not sources you search. They arrive as signal entries from coaches.

| Source | Location | Freshness |
|--------|----------|-----------|
| Coach signal entries | `shared-intelligence/signals/` | Continuous (as coaches contribute) |
| Pattern reports | `shared-intelligence/patterns/` | Monthly (compound synthesis) |
| Prior research outputs | FuE research archive | As produced |

**Action:** Read new signal entries before every research session. Always check internal signals before searching externally.

---

## Channel B: Active Research (External)

### Labor Market Statistics

| Source | URL | Frequency | What to Look For |
|--------|-----|-----------|-----------------|
| BA Arbeitsmarktbericht | statistik.arbeitsagentur.de | Monthly | Unemployment rates, vacancy trends, sector shifts by region |
| BA Fachkraefteengpassanalyse | arbeitsagentur.de/arbeitsmarktdaten | Quarterly | Which professions are shortage vs. surplus |
| IAB Forschungsportal | iab.de | Weekly | New Kurzberichte, Forschungsberichte touching the five Ds |
| IAB Stellenerhebung | iab.de/stellenerhebung | Quarterly | Job opening dynamics, hiring difficulty indicators |
| Destatis Arbeitsmarkt | destatis.de | Monthly | Long-term structural trends, demographic data |

### Policy and Regulation

| Source | URL | Frequency | What to Look For |
|--------|-----|-----------|-----------------|
| BMAS (Bundesministerium fuer Arbeit) | bmas.de | As published | New legislation, Buergergeld changes, Fachkraefteeinwanderung updates |
| EU Employment Policy | ec.europa.eu/social | Monthly | European Pillar of Social Rights developments |
| EUR-Lex | eur-lex.europa.eu | Monthly | AI Act workforce provisions, Green Deal employment measures |
| Bundesgesetzblatt | bgbl.de | As published | New laws affecting labor market, education, migration |

### Applied Research

| Source | URL | Frequency | What to Look For |
|--------|-----|-----------|-----------------|
| BIBB (Bundesinstitut fuer Berufsbildung) | bibb.de | Monthly | New Ausbildungsberufe, qualification framework changes |
| DGB Gute-Arbeit-Index | index-gute-arbeit.dgb.de | Annual | Working conditions trends, sector comparisons |
| WSI (Wirtschafts- und Sozialwissenschaftliches Institut) | wsi.de | Monthly | Wage trends, Tarifvertraege, inequality data |
| Bertelsmann Stiftung | bertelsmann-stiftung.de | As published | Social cohesion, education system, labor market integration |
| IAQ Duisburg | iaq.uni-due.de | Quarterly | Working conditions research, flexible employment |

### Sector-Specific

| Source | URL | Sectors | Frequency |
|--------|-----|---------|-----------|
| Bitkom | bitkom.org | IT, Digital | Monthly |
| VDMA | vdma.org | Manufacturing, Engineering | Quarterly |
| DKG (Deutsche Krankenhausgesellschaft) | dkgev.de | Healthcare | Monthly |
| HDE (Handelsverband Deutschland) | einzelhandel.de | Retail | Quarterly |
| UBA (Umweltbundesamt) | umweltbundesamt.de | Green Economy | Quarterly |

### Academic (for deeper investigations)

| Source | URL | Use Case |
|--------|-----|----------|
| Google Scholar | scholar.google.com | Keyword searches on specific phenomena |
| SSRN | ssrn.com | Working papers on labor economics, AI + work |
| arXiv (cs.CY, econ) | arxiv.org | AI labor market impact preprints |
| IZA Discussion Papers | iza.org | Labor economics research |
| OECD Employment Outlook | oecd.org | International comparative data |

---

## Gateway Configuration

The gateway is the automated trigger layer. It defines WHEN research tasks run and WHAT they do.

### Scheduled Tasks

```yaml
weekly_iab_scan:
  schedule: "every Monday 08:00"
  action: "Search IAB Forschungsportal for publications from the past 7 days. Filter for relevance to the five Ds. Write summary of relevant findings to research-feed/weekly/"
  sources: [iab.de]

weekly_ba_check:
  schedule: "every Monday 08:00"
  action: "Check BA Statistik for updated monthly reports. Note any significant changes in NRW data. Flag for FuE team if change exceeds 5% from prior period."
  sources: [statistik.arbeitsagentur.de]

monthly_signal_compound:
  schedule: "first Monday of month"
  action: "Read all new signal entries from shared-intelligence/signals/ since last compound. Identify patterns, contradictions, and gaps. Write pattern report to shared-intelligence/patterns/. Propose new sensing prompts if gaps found."
  sources: [shared-intelligence/signals/]

monthly_policy_scan:
  schedule: "15th of month"
  action: "Scan BMAS, EU Employment, and Bundesgesetzblatt for new developments. Assess impact on coaching programs and coachee populations. Write policy brief if significant."
  sources: [bmas.de, ec.europa.eu, bgbl.de]

quarterly_full_compound:
  schedule: "first week of quarter"
  action: "Full compound review: synthesize all signals, patterns, external research from past quarter. Identify what the system learned, what questions were answered, what new questions emerged. Update five-Ds-framework.md if new patterns warrant it."
  sources: [all]
```

### Event-Triggered Tasks

```yaml
new_signal_arrived:
  trigger: "new file in shared-intelligence/signals/"
  action: "Read new signal. Cross-reference against existing patterns and last 3 months of signals. Flag if it confirms, contradicts, or is novel. Notify FuE team if novel or contradicting."

new_fue_project:
  trigger: "manual — FuE team starts new project"
  action: "Landscape scan: what existing signals, patterns, and external research are relevant to this project? Produce initial briefing within 24 hours."

anomaly_report:
  trigger: "manual — coach flags something unusual"
  action: "Deep dive: is this a local phenomenon or emerging trend? Check all channels. Respond within 48 hours."
```

### Technical Implementation Notes

These gateway tasks can be implemented as:
- **Claude Code scheduled tasks** (`/schedule` skill) for AI-driven tasks
- **Python scripts** with `schedule` library for web scraping / API calls
- **Power Automate** flows for OneDrive/SharePoint file watching
- **GitHub Actions** for Git-based workflows

The researcher folder defines the methodology. The gateway infrastructure is separate and can be implemented with whatever tools the organization already uses. Start simple (manual triggers), automate as trust builds.

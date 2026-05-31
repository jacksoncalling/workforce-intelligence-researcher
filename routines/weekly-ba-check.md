# Weekly BA Statistik Check

**Schedule:** Every Monday, 08:00
**Output:** `research-feed/weekly/YYYY-MM-DD_ba-check.md`

---

## Prompt

Check statistik.arbeitsagentur.de for updated monthly Arbeitsmarktberichte. Focus on:

- Unemployment rates by region, with special attention to NRW
- Vacancy trends by sector (IT, Pflege, Manufacturing, Retail, Administration)
- Any significant changes from the prior reporting period

Flag for the FuE team if any indicator changes by more than 5% from the previous period.

Cross-reference against current coach signals: are coaches reporting what the statistics show, or is there a divergence? If there is a divergence, describe it — this is a finding, not an error.

Write the output to `research-feed/weekly/` with today's date in the filename.

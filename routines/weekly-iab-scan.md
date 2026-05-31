# Weekly IAB Scan

**Schedule:** Every Monday, 08:00
**Output:** `research-feed/weekly/YYYY-MM-DD_iab-scan.md`

---

## Prompt

Search the IAB Forschungsportal (iab.de) for publications from the past 7 days. Focus on:

- Kurzberichte and Forschungsberichte
- Any publication touching the five Ds: Decarbonization, Digitalization, Demographic Change, Democracy, Decent Work
- Special attention to NRW-specific data or findings

For each relevant publication found:

1. Note the title, date, and authors
2. Write a 2-3 sentence summary of the key finding
3. Tag it with the relevant D(s) from the five-Ds framework
4. Note whether it confirms, contradicts, or is unrelated to current coach signals

If nothing relevant was published this week, say so — a null result is still a result.

Write the output to `research-feed/weekly/` with today's date in the filename.

At the end, check: does anything found this week suggest a new sensing prompt for coaches? If yes, draft the prompt.

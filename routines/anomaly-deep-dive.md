# Anomaly Deep Dive

**Trigger:** A coach flags something unusual or unexpected
**Output:** `research-feed/anomaly-reports/YYYY-MM-DD_[topic].md`
**Turnaround:** Within 48 hours

---

## Prompt

A coach has flagged an anomaly: [DESCRIPTION — fill in before running]

This needs investigation. The question is: is this a local phenomenon, or the first sign of an emerging trend?

**Step 1 — Understand the observation:**
- What exactly did the coach observe?
- How many coachees are involved?
- What region and industry?
- How confident is the coach that this is unusual?

**Step 2 — Check internal signals:**
- Has any other coach reported something similar in the past 6 months?
- Does this fit any existing pattern — or does it break one?
- If it breaks a pattern, which one, and what does that mean?

**Step 3 — Check external sources:**
- Do labor market statistics show anything consistent with this observation?
- Has any research institution published on this topic recently?
- Are there policy changes that could explain this?

**Step 4 — Assess:**
- **Local phenomenon:** Explainable by regional or industry-specific factors. Note it, but no action needed beyond monitoring.
- **Early signal:** Consistent with broader trends but not yet confirmed. Issue a sensing prompt to other coaches.
- **Emerging trend:** Multiple data points converging. Escalate to FuE team for deeper investigation.

**Step 5 — Respond:**
- Write the anomaly report with your assessment and evidence
- If early signal or emerging trend: draft a sensing prompt for the coaching network
- If emerging trend: recommend whether this warrants a full research project

Write the report to `research-feed/anomaly-reports/` with today's date and topic in the filename.

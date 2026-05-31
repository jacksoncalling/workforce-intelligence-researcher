# /contribute-signal

Takes a local market-intel entry and anonymizes it for the shared intelligence layer. Run after `/market-signal` when the coach decides to share.

---

## Prompt

You are helping a coach anonymize a market observation for the shared intelligence layer. The coach has already written a local entry with full context. Your job is to transform it into a signal that protects privacy while preserving the intelligence value.

### Step 1: Read the local entry

Read the coach's most recent market-intel entry (or the one they specify).

### Step 2: Anonymization checklist

Walk through each item with the coach:

- [ ] **Names removed** — no coachee names, no employer names, no contact names
- [ ] **Geography generalized** — "NRW" or "Rheinland" rather than specific neighborhoods. Cities are OK if large enough (Koeln yes, Aachen-Eilendorf no)
- [ ] **Demographics generalized** — "IT professional with 5+ years experience" not "34-year-old Syrian developer who arrived in 2021"
- [ ] **Aggregated where possible** — "3 coachees in IT-sector" not individual descriptions
- [ ] **Focused on market behavior** — what the system/employers/platforms DID, not what the person felt
- [ ] **Self-check passed** — "Could someone reading this identify the person?" If yes, generalize further.

If any check fails, propose a more general phrasing and ask the coach to confirm.

### Step 3: Format as shared signal

Transform into the standard signal format:

```markdown
## Signal: [one-line description of the market behavior]

**Date:** YYYY-MM-DD
**Region:** [NRW / Ruhrgebiet / Rheinland / national]
**Industry:** [sector]
**Type:** [hiring-behavior / skills-demand / platform-behavior / salary-signal / sector-shift / barrier-pattern / condition-signal]
**Lens:** [which of the five Ds — can be multiple]
**Confidence:** [low / medium / high — based on number of observations]

### Observation
[2-4 sentences. Anonymized. Focus on market behavior.]

### Context
[What makes this noteworthy? Confirms/contradicts existing patterns?]

### Coaching Implication
[How should other coaches respond to this? What to do differently?]
```

### Step 4: Write to shared layer

Save the signal to `G:\My Drive\workforce-intelligence-researcher\shared-intelligence\signals\YYYY-MM-DD_[short-slug].md`

This is the shared Google Drive folder — all coaches and the FuE researcher have access to this location. Writing here makes the signal immediately available to the full network.

Confirm with the coach: "Signal contributed. Other coaches will see this in the shared layer, and it will be included in the next monthly compound. Thank you."

### Step 5: Check for existing sensing prompts

Check `shared-intelligence/sensing-prompts/` — does this signal relate to an active sensing prompt? If yes, note the connection: "This responds to sensing prompt [name]. The FuE team is actively investigating this pattern."

---

## Privacy safeguards

If the AI detects potential identifying information that the coach missed:

"I notice this description might identify someone — [explain why]. Can we generalize to [proposed alternative]?"

The coach makes the final call. The AI flags, the human decides. This is a collaborative anonymization process, not an automated extraction.

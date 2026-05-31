# Monthly Signal Compound

**Schedule:** First Monday of each month
**Output:** `shared-intelligence/patterns/YYYY-MM_signal-compound.md`

---

## Prompt

Read all new signal entries from `shared-intelligence/signals/` that have arrived since the last compound report.

For each signal, note:
- Type (hiring behavior, skills demand, platform behavior, salary signal, sector shift, barrier pattern, condition signal)
- Region and industry
- Which of the five Ds it touches
- Confidence level

Then synthesize across all new signals:

1. **Patterns:** What themes recur across multiple signals? Where do 3+ signals point in the same direction?
2. **Contradictions:** Where do signals disagree with each other, or with the last pattern report? Do not resolve contradictions — surface them.
3. **Gaps:** Which industries, regions, or signal types are underrepresented? Where are we NOT sensing?
4. **Freshness check:** Are any signals from the previous compound now older than 6 months? Flag them as aging.
5. **External cross-reference:** Do any patterns align with or contradict recent BA/IAB data from the weekly scans?

Write the pattern report to `shared-intelligence/patterns/` with the month in the filename.

End with: propose 1-3 new sensing prompts for coaches based on gaps or emerging patterns. Write these to `shared-intelligence/sensing-prompts/`.

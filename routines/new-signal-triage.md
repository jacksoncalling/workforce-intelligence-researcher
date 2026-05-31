# New Signal Triage

**Trigger:** A new signal file appears in `shared-intelligence/signals/`
**Output:** Annotation on the signal file + notification if needed

---

## Prompt

A new coach signal has arrived. Read it now.

1. **Classify:** What type is it? (hiring behavior, skills demand, platform behavior, salary signal, sector shift, barrier pattern, condition signal)
2. **Tag:** Which of the five Ds does it touch?
3. **Cross-reference:** Compare against the last 3 months of signals and the most recent pattern report.
   - Does it **confirm** an existing pattern? Note which one.
   - Does it **contradict** an existing pattern? This is important — flag it.
   - Is it **novel** — something we haven't seen before? Flag it for attention.
4. **Confidence:** Given existing signals, what is the confidence level? (low = first time seeing this, medium = 3+ consistent signals, high = 5+ from multiple coaches)

If the signal is **novel or contradicting**, notify the FuE team with a short note explaining why it matters.

If the signal suggests a sensing prompt (something coaches should ask about more specifically), draft one.

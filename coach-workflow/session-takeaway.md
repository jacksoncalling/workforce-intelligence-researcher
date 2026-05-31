# /session-takeaway

A 3-minute end-of-session routine for coaches. Captures what you gave the coachee today — tips, corrections, resources, insights — so it accumulates into their personal takeaway folder over the course of the program.

---

## Prompt

You are helping a career coach capture what they shared with a coachee during today's session. This is not about what the coach observed (that is `/market-signal`). This is about what the coachee should walk away with.

### Step 1: Which coachee?

Ask: "Which coachee was this session with, and which module?" (e.g., "Anna M., Modul 02 — Standortbestimmung")

Use this to determine the save location: `clients/[coachee]/takeaways/YYYY-MM-DD_modul-XX.md`

### Step 2: What did you share today?

Ask the coach to think through these categories — not all will apply every session:

- **CV / Bewerbung:** Corrections, formatting suggestions, phrasing improvements, structural changes
- **Interview-Vorbereitung:** Questions to prepare for, how to frame certain experiences, body language notes
- **Markt-Tipps:** Specific companies to look at, sectors to explore, platforms to use, networking approaches
- **Selbstpräsentation:** How to tell their story, elevator pitch adjustments, strengths framing
- **Ressourcen:** Links, tools, contacts, reading recommendations shared during the session
- **Nächste Schritte:** What the coachee committed to doing before the next session

Guide the conversation naturally — don't run through categories like a checklist. Ask: "What was the most useful thing you told them today?" and build from there.

### Step 3: Write the takeaway entry

Format:

```markdown
# Session-Takeaway: [Coachee Vorname] — [Datum]

**Modul:** [which module]
**Schwerpunkt heute:** [one-line summary of what the session focused on]

## Was wir heute erarbeitet haben

### [Category 1, e.g., Lebenslauf]
- [specific tip or correction]
- [specific tip or correction]

### [Category 2, e.g., Markt-Tipps]
- [specific recommendation]

## Deine nächsten Schritte
- [ ] [action item 1]
- [ ] [action item 2]
- [ ] [action item 3]

## Notiz vom Coach
[One personal sentence — encouragement, observation, reminder. This is what makes it human, not a report.]
```

Save to: `clients/[coachee]/takeaways/YYYY-MM-DD_modul-XX.md`

### Step 4: Confirm and preview

Show the coach the entry. Ask: "Anything to add or change before I save this?"

The entry is written in language the COACHEE can understand — not coach jargon, not AI-speak. Second person: "Du hast..." / "Dein Lebenslauf..." This is THEIR document.

---

## How this builds into the Coachee-Paket

Over 2-5 sessions, the takeaway folder fills up:

```
clients/anna-m/
├── profil.md                          ← coachee profile
├── protokolle/                        ← session protocols
│   ├── 2026-05-15_modul-01.md
│   └── 2026-05-29_modul-02.md
└── takeaways/                         ← what the coachee keeps
    ├── 2026-05-15_modul-01.md         ← "Here's what we worked on"
    ├── 2026-05-29_modul-02.md
    └── ...
```

At program end, the coach runs `/build-coachee-paket` (Phase 2) which compiles all takeaways + relevant market intelligence into one clean package — a personal document the coachee keeps for their independent job search.

The coachee-paket is the down-hierarchy made tangible: organizational intelligence, filtered through professional coaching judgment, delivered as something one person can actually use.

---

## Example interaction

**Coach:** "Session with Thomas, Modul 3 — Bewerbungsstrategie."

**AI:** "Got it. What was the most useful thing you shared with Thomas today?"

**Coach:** "We rewrote his Anschreiben opening. He was starting with 'Hiermit bewerbe ich mich...' — we changed it to lead with his project management experience at the solar company. Also told him to stop applying through Indeed and go directly to company career pages. And I showed him the color-matching trick for his documents."

**AI:** "Good — so Anschreiben restructuring, platform strategy, and visual customization. Anything on next steps for him?"

**Coach:** "He should rewrite three Anschreiben with the new structure before next week. And set up a LinkedIn profile — we talked about that but didn't get to it today."

**AI:**

```
# Session-Takeaway: Thomas — 29.05.2026

**Modul:** 03 — Bewerbungsstrategie
**Schwerpunkt heute:** Anschreiben und Bewerbungswege optimieren

## Was wir heute erarbeitet haben

### Anschreiben
- Einstieg geändert: Nicht "Hiermit bewerbe ich mich..." sondern direkt
  mit deiner Projektmanagement-Erfahrung bei der Solarfirma einsteigen.
  Zeig sofort, was du mitbringst.
- Der neue Aufbau: Erfahrung → was du suchst → warum diese Firma.

### Bewerbungswege
- Indeed hat niedrigere Rücklaufquoten als direkte Bewerbungen
  über Karriereseiten der Unternehmen. Ab jetzt: direkt bewerben.

### Dokumente
- Bewerbungsunterlagen farblich an die Markenfarben des
  Zielunternehmens anpassen — erhöht nachweislich die Einladungsquote.

## Deine nächsten Schritte
- [ ] 3 Anschreiben mit dem neuen Aufbau umschreiben
- [ ] LinkedIn-Profil anlegen (machen wir nächste Woche zusammen)

## Notiz vom Coach
Du hast heute einen großen Schritt gemacht — der neue Einstieg in
deinem Anschreiben klingt wie ein anderer Mensch. Weiter so.
```

**AI:** "Saved to clients/thomas/takeaways/2026-05-29_modul-03.md. Anything to change?"

---

## Language

Takeaway entries default to German (the coachee's working language for applications). Switch to English if the coachee's job search is English-language. The coach decides — ask if unclear.

## Privacy

Takeaway files stay in the coach's private workspace (Layer 1). They contain personal coaching content and are NEVER shared to the shared intelligence layer. The coachee receives their folder at the end of the program — the coach decides the format (email, USB, shared folder, printed).

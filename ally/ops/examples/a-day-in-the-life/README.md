# A Day in the Life

**Source:** "A Day in the Life," Lennon/McCartney, *Sgt. Pepper's Lonely Hearts Club Band* (1967).

## Why this example

A rich test corpus for *atomic-day* modeling. The song stresses:

- **Nested narratives** — narrator reads news → news contains a story → story contains a person → person dies in a scene. Four levels of `NarrativeHolon` containment.
- **External events crossing into private experience** — news items, "4,000 holes in Blackburn, Lancashire." Canonical pattern for any data source crossing the DomainGraph boundary.
- **Affect as annotation** — "oh boy." Where does felt emotional tone live? See `CANDIDATES.md` → `affect-representation`.
- **Underspecified references** — *"I'd love to turn you on"* — the referent of "you" is indeterminate. See `CANDIDATES.md` → `underspecified-references`.
- **Scene identity with chronology bracketed** — what makes a scene a scene when we aren't relying on time order?

## Framing decisions (from setup session, 2026-04-23)

- **One actor, one day.** Even where the song fuses Lennon's and McCartney's voices, we treat it as one narrator's day. This brackets compositional-authorship questions.
- **Chronology bracketed.** Scenes are not ordered by time in our modeling. Scene *identity* is the question, not sequence.
- **Lyrics as description, not music.** We model what the lyrics describe. We do not model orchestral swirls, bridges-as-events, or the song's musical structure.

## What this example does NOT stress

- Longitudinal continuity (days, months, years)
- Proficiency growth over time
- Cross-day identity coherence
- Loss, revision, changing relationships

A second example will be chosen for those — see `ops/examples/README.md`.

## To be built (next session)

- `description.md` — the day as prose, extracted from the lyrics
- `modeled.trig` — TTL modeling under `models/baseline/` (or a `models/vNN-*/` if the modeling forces a change)
- Per-stress-test modelings that reuse or diverge from the base modeling

## License note

Lyrics are quoted here as scholarly fair-use for the purpose of architectural analysis. Source attribution: Lennon/McCartney, Northern Songs, 1967.

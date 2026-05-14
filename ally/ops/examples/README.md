# examples/

Worked examples. Each example is a corpus of personal-context-shaped data we model in TTL to exercise specific stress tests.

## Conventions

Each example lives in its own directory and contains:

- `README.md` — what the example is, why we chose it, what it stresses, what it doesn't
- `description.md` — the source content as prose (lyrics reformatted as description, journal text, etc.)
- `modeled.trig` — the TTL modeling (or pointers into `models/vNN-*/` where the modeling is canonical)

Examples are referenced from stress tests via `ops/stress-tests/NNN-*/references.md`.

## Current examples

- `a-day-in-the-life/` — A Day in the Life (Lennon/McCartney, 1967). Single actor, one day, chronology bracketed. Atomic-day stress test.
- _longitudinal example TBD_ — Criteria: same actor across years, multiple relationships, explicit change or loss. See a-day-in-the-life README for why a second example is needed.

## What good examples have in common

- Grounded in real human experience (not toy data)
- Compact enough to model fully (not an entire life)
- Surface a specific set of representational challenges
- Tell a story — so findings can be narrated to Kurt

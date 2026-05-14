# ops/

Narrative. **Markdown only.** If it's a `.ttl`, it belongs in `models/`.

## Structure

- `stress-tests/` — individual stress tests. Each: rationale, hypothesis, findings, references.
- `mapping/` — how Ally's three spaces map to HGA's four layers. The primary test harness.
- `examples/` — worked examples (day-in-the-life, etc.) that stress tests reference.
- `notes-for-kurt/` — running document, eventually shared upstream.

## Discipline

- No `.ttl` files here. TTL is authoritative code; it belongs in `models/`.
- No prose inside TTL comments beyond what's strictly needed for the file to make sense standalone. Rationale lives here.
- Every stress test references specific `models/vNN-*/` and `examples/*/` artifacts. Traceability both ways.

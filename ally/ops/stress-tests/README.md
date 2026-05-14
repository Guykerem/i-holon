# stress-tests/

Each stress test is a self-contained probe of whether HGA can represent a specific pattern of Integrated Individual Information (III).

## Protocol

1. **Identify** a pattern that strains the architecture. Add it to `CANDIDATES.md` if it isn't already there.
2. **Instantiate** a new directory `NNN-<kebab-name>/` by copying `TEMPLATE/`.
3. **Hypothesise** in `hypothesis.md`: what we expect. What would vindicate HGA? What would break it?
4. **Model** against a specific `models/` version (baseline or a `vNN`). Record which in `references.md`.
5. **Validate** with SHACL where applicable.
6. **Record** in `findings.md`: what actually happened. Was the hypothesis confirmed? What was unexpected?
7. **Propagate**:
   - If the test produced a model change, create `models/vNN-*/` and link from `references.md`.
   - If the test surfaces something Kurt should see, append to `ops/notes-for-kurt/`.

## Numbering

- Numbers are assigned in creation order. Never reordered.
- Descriptors are short kebab-case.
- Example: `003-multi-parent-holons/`, `007-affect-representation/`.

## What makes a good stress test

- Starts from a **real** pattern of personal context (not a toy). Cite the example or the real-world source.
- Has a **specific** expected outcome, not just "let's see what happens."
- Is **falsifiable** — we can tell whether it passed or failed.
- Produces **one of**: confirmation, a model change, a notes-for-Kurt entry, or all three.

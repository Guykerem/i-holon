# Ally Entities as Holons

## Purpose

Translate Ally's kernel entity types (from `kernel.yaml` in the main Ally repo, `~/git/ally/ally/spec/kernel/`) into HGA vocabulary. This exercise tests whether Ally's 12 kernel entities can be expressed natively in HGA, or whether the Kernel requires constructs HGA does not offer.

This is the bridge between our two schemas. If the translation is clean, adoption is straightforward. If it strains, the strain points are exactly what we need to document for both Kurt and the Ally Kernel design.

## Status

TBD. To be populated after the first few stress tests have clarified which HGA constructs we actually rely on. Populating this now would be premature — we'd encode guesses into the bridge.

## Expected structure (once we start filling it)

For each Ally kernel entity:

- **Ally name & role** — e.g., "Moment — capture unit"
- **Candidate HGA mapping** — under Reading A (see `three-spaces-to-layers.md`): which space, which holon class?
- **Required HGA constructs** — the minimum vocabulary used
- **Fit assessment** — clean / strained / requires extension
- **Linked stress tests** — which NNN-* probed this mapping

## Related

- `three-spaces-to-layers.md` — the overall mapping framework this document instantiates
- `~/git/ally/ally/spec/kernel/` — authoritative Ally kernel spec (the source side of the bridge)

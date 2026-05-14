# models/

Authoritative semantic artifacts. **TTL only.** If it's Markdown, it belongs in `ops/`.

## Structure

- `baseline/` — verbatim pin of upstream. Never modified in place. See `baseline/PIN` for the commit hash.
- `vNN-<kebab-name>/` — a specific semantic experiment.

Each `vNN-*/` directory contains:
- modified TTL files (only the files that changed relative to `baseline/`)
- `rationale.md` — short, in-place pointer to the originating stress test (full rationale lives in `ops/stress-tests/NNN-*/rationale.md`)
- `changes.diff` — regenerable at any time: `diff -u baseline/ vNN-*/`

## Naming

- Version numbers are assigned in creation order (`v01-`, `v02-`, ...) and are never reordered.
- Descriptors are short kebab-case: `v01-multi-parent`, `v02-portal-as-policy`, etc.
- Do **not** use names that imply a verdict ("v03-fixed-portal"). Names describe *what was tried*, not whether it worked.

## Relationship to ops/

Every `models/vNN-*/` is referenced from exactly one `ops/stress-tests/NNN-*/references.md`. The rationale lives in ops; the artifact lives here.

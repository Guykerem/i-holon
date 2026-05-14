# ally/ — HGA stress test as candidate Kernel substrate

## What this is

A stress-testing harness for Kurt Cagle's Holonic Graph Architecture (HGA), applied to the requirements of Personal Context Management (PCM) as realised in Ally.

The output we care about is twofold:
1. **A decision about adoption.** Does HGA become Ally's Kernel substrate — the long-term rigorously-governed, RDF-rooted foundation for the Personal Context Graph?
2. **Notes back to Kurt.** What works, what strains, what we'd propose. A real-world example of HGA applied to a non-trivial domain.

## The primary question

Does the 3×4 combination of **Ally's three spaces** and **HGA's four layers** constitute a **MECE** (mutually exclusive, collectively exhaustive) decomposition of **III** — the *Integrated Individual Information* we aim to unify, govern, and project?

- ME: every piece of III has a single primary home. No ambiguity.
- CE: every piece of III has *a* home. No gaps.

Where the decomposition holds, HGA is vindicated. Where it breaks — overlap, gaps, forced ambiguity — we have the notes for Kurt and the requirements for Ally's Kernel.

The live framing lives in `ops/mapping/three-spaces-to-layers.md`.

## Ally's three spaces

| Space | Meaning |
|---|---|
| **Self** | Who the individual is — identity, traits, values, priors, ongoing dispositions. |
| **World** | What exists beyond the individual — entities, other actors, environments, facts, events. |
| **Experience** | Moments of encounter — scenes, feelings, relations. Where Self meets World. |

## HGA's four layers (upstream)

| Layer | Class | Role |
|---|---|---|
| L1 | `SceneGraph` | interior / immanent |
| L2 | `DomainGraph` | boundary / normative (≅ Markov blanket) |
| L3 | `ContextGraph` | relational / situational |
| L4 | `HolonicGraph` | meta / compositional |

## How we work here

### Two subtrees, two disciplines
- `ally/models/` — **code**. TTL only. Our evolution of upstream semantic artifacts.
- `ally/ops/` — **narrative**. Markdown only. Rationale, stress tests, mapping documents, examples, notes-for-Kurt.

If you catch yourself putting `.md` in `models/` or `.ttl` in `ops/`, stop and reconsider.

### Model versioning
Every semantic change to upstream lives as a numbered directory under `ally/models/`:
- `baseline/` — verbatim pin of upstream. Never modified in place. See `PIN`.
- `v01-<kebab-name>/` — a specific semantic experiment. Contains modified TTL + `rationale.md` + regenerable `changes.diff`.

### Stress-test protocol
Each stress test lives in `ally/ops/stress-tests/NNN-<kebab-name>/` and contains:
- `rationale.md` — why this test exists; what pattern of III strains HGA
- `hypothesis.md` — what we expect; what would vindicate, what would break
- `findings.md` — what actually happened
- `references.md` — which `models/` version, which `examples/`

Use `ops/stress-tests/TEMPLATE/` as the starting scaffold. See `ops/stress-tests/CANDIDATES.md` for the in-flight list.

### Upstream discipline
Kurt's files are never modified in place. To propose an upstream change:
1. Build the change as `models/vNN-*/`
2. Document in `ops/stress-tests/NNN-*/`
3. Note rationale for upstream in `ops/notes-for-kurt/`

Only after all three — and after explicit decision — do we consider an upstream PR.

## Relationship to Ally proper

This repo is registered as `story=ally, role=experiment`. HGA is a *candidate* substrate for Ally's Kernel — not yet adopted. The adoption decision is downstream of the stress-test findings.

If HGA passes → `src/memory/pcg/` in the main Ally repo converges toward HGA semantics.
If it fails → we keep what we learn; Ally's Kernel remains pragmatically custom.

## Tooling

We defer to HGA's conventions. Kurt's canonical stack:
- **Apache Jena** for SHACL validation (`shacl validate --shapes ... --data ...`)
- **rdf-validate-shacl (Node)** for lightweight examples

The tooling is also under test — does it deliver the features HGA assumes (RDF 1.2 triple terms, SHACL 1.2 conditional shapes, `sh:reifierShape`)? Tooling-adequacy findings go in `ops/notes-for-kurt/`.

Python (pySHACL, rdflib) is *not* canonical to HGA. If downstream Ally needs Python integration, that's handled at the Ally-side bridge, not inside this fork.

## Anti-goals

- We do not re-implement HGA. We use it as given; we propose deltas with rationale.
- We do not optimize for performance or indexing. We test *representational adequacy* first.
- We do not model the audio/musical structure of songs used as examples. Lyrics-as-descriptions; songs-as-songs are out of scope.
- We do not invent new spaces beyond Self / World / Experience *unless* a stress test forces it. That's a finding, not a starting assumption.

## Open — being brainstormed in parallel (as of 2026-04-23)

- Precise placement of affect (Self-L1 vs. Experience-L3 vs. Damasio split). See `CANDIDATES.md` → `affect-representation`.
- Whether interpersonal relationships fit MECE-ly in Experience, or suggest a fourth space (Covenant/Bond). See mapping doc.
- Selection of a longitudinal example (criteria in `ops/examples/a-day-in-the-life/README.md`).
- Skill loadout for this project — `witt`, `visualize`, `ask`/`recommend`; possibly a semantic-web-practitioner skill to be built with `skill-creator`.

## Starting a session here

1. Read this file.
2. Check `ops/stress-tests/CANDIDATES.md` for in-flight and pending tests.
3. Refer to `ops/mapping/three-spaces-to-layers.md` for the current mapping state.
4. New tests instantiate from `ops/stress-tests/TEMPLATE/`.
5. New model versions copy from `models/baseline/`.

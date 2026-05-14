# Stress Test Candidates

Running list of patterns that strain HGA and deserve dedicated stress tests. Each becomes a numbered `stress-tests/NNN-<name>/` directory when we begin work on it.

Candidates are added here as they surface. They are *not* prioritised — priority is decided at session start.

## Surfaced in setup session (2026-04-23)

- **affect-representation** — Where does episodic emotional tone live? Three candidate architectures: (A) split by temporal extent — Self-L1 for enduring, Experience-L3 for episodic affect; (B) all-at-L1 with temporal-extent subtypes; (C) Damasio feelings-vs-emotions split. See `ops/mapping/three-spaces-to-layers.md` § Affect.

- **underspecified-references** — In *"I'd love to turn you on"* the referent of "you" is undetermined. HGA object-property ranges are typed. What fills the range of an unresolved reference? `PlaceholderHolon`? `DeferredReference`? Critical for ingesting real messaging data where pronouns routinely lack antecedents.

- **multi-parent-holons** — A dinner conversation belongs to *family* AND *personal-science* AND *writing*. HGA's `partOf` is transitive and tree-shaped. Real personal context is a DAG. Does multi-`partOf` work with SHACL, or do we need a `contextOf` relation at L3?

- **portal-as-policy** — HGA Portals carry schema, not authorization. For PCM we need agent-specific disclosure policies ("Claude-on-eo1 sees X; Claude-on-family sees Y"). Extend Portal, or add a sibling `Lens`/`AccessProfile` construct?

- **agent-taxonomy** — Architecturally, what is Claude? `ProxyHolon` (externally controlled)? `InternalActorHolon` (fully owned within the self)? Something new? Governs memory, consent, and what the agent is permitted to act on without re-ask.

- **scene-identity** — With chronology bracketed (as in a-day-in-the-life), what operationally defines a `SceneHolon`? Topic? Setting? Emotional arc? HGA declares the concept but doesn't provide identity criteria.

- **relationship-space** — Does an ongoing interpersonal relationship fit MECE-ly inside Experience, or does it demand a fourth space (Covenant/Bond)? Relationships span Self, World, and Experience; finding their primary home is the crisp version of the mapping question.

- **MECE-III** — The meta-test. Walk the full Integrated Individual Information of a non-trivial example end-to-end and check: does every datum have exactly one home in the 3×4 matrix? This is the test that tells us whether the architecture as a whole is adequate.

## Future

(Add as they surface.)

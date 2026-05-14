# Three Spaces × Four Layers — the MECE test over III

**Status:** v0 hypothesis (2026-04-23). Under active revision.

## The primary question

Does the 3×4 combination of Ally's three spaces and HGA's four layers yield a **MECE decomposition** of **Integrated Individual Information (III)** — every piece of III has one primary home, and nothing falls through the cracks?

- **ME (mutually exclusive).** For any piece of III, exactly one cell is its primary home. Appearances in other cells are *principled projections*, not duplicate state.
- **CE (collectively exhaustive).** Every piece of III has *a* home. Nothing is invisible to the architecture.

Where the decomposition holds, HGA is vindicated. Where it fails — overlap, gaps, forced ambiguity — we learn where Kurt's architecture needs extension and where Ally's Kernel needs care.

## Revision log

- **v0 (2026-04-23)** — Initial framing. Two candidate readings of the 3×4 matrix laid out below; neither adopted.

## The three spaces (as Ally defines them)

| Space | Meaning |
|---|---|
| **Self** | Who the individual is — identity, traits, values, priors, ongoing dispositions. |
| **World** | What exists beyond the individual — entities, other actors, environments, facts, events. |
| **Experience** | Moments of encounter — scenes, feelings, relations. Where Self meets World. |

## The four layers (from upstream HGA)

| Layer | Class | Role |
|---|---|---|
| L1 | `SceneGraph` | interior / immanent |
| L2 | `DomainGraph` | boundary / normative (≅ Markov blanket) |
| L3 | `ContextGraph` | relational / situational |
| L4 | `HolonicGraph` | meta / compositional |

## Two candidate readings of the 3×4 matrix

Two fundamentally different ways to read "spaces × layers." Each has different MECE implications.

### Reading A — Spaces as holon *types*; layers as internal structure of each holon

Each of Self, World, and Experience is a **type of holon**. Every holon of any type has the same four-layer internal structure. Layers are MECE *within* a holon (Kurt's intent). Spaces are the top-level partition of III-holons.

| | L1 SceneGraph | L2 DomainGraph | L3 ContextGraph | L4 HolonicGraph |
|---|---|---|---|---|
| **Self** (one or more `SelfHolon`s) | enduring traits, dispositions, priors | consent policies, integrity invariants, sovereignty boundary | relations with past and aspirational selves | composition of the self across time |
| **World** (many `WorldHolon`s: people, places, things, events) | intrinsic facts about the entity | schema / type / what defines it | its relations to other world entities | how it composes into larger world-structures |
| **Experience** (many `ExperienceHolon`s: scenes, moments) | felt interior state at the moment *(contested — see Affect)* | preconditions / permissions that made this experience possible | relational positioning: self↔world, self↔self, world↔world | how moments compose into arcs, days, life |

**MECE strengths of Reading A:**
- Clean separation: each datum belongs to a holon *of one type*, and to one layer *within* that holon.
- Layers inherit MECE from Kurt's design; spaces add a higher-level partition.
- Composition (L4) at each space can be nested independently — self-holarchy, world-holarchy, experience-holarchy.

**MECE tensions of Reading A:**
- *Relationships.* An ongoing friendship. Is it an ExperienceHolon (lived in moments) that references a WorldHolon (the friend)? Or a SelfHolon-L3 (my relations)? Or all of the above? → `relationship-space` stress test.
- *Affect.* "Oh boy" while reading the news. ExperienceHolon-L1 (felt interior)? Or does Self-L1 absorb it? → `affect-representation` stress test.
- *Agents operating on the self.* Claude working in eo1. A WorldHolon (external actor)? Or an InternalActorHolon living inside the Self? → `agent-taxonomy` stress test.

### Reading B — Spaces as orthogonal axes; every datum has coordinates in both

There is no holon-type partition. Every holon has all four layers (Kurt), *and* every holon's content is tagged with which of the three spaces it speaks to. A single holon can speak to multiple spaces — e.g., a shared meal is simultaneously Self (what I was like at that meal) and World (other people were there) and Experience (the meal as moment).

**MECE strengths of Reading B:**
- Matches the lived reality that content is often cross-space (a shared meal, a relationship, an argument with oneself).
- No forced classification of holons into space-types.

**MECE tensions of Reading B:**
- Weakens MECE substantially. If a holon can be in multiple spaces, ME is sacrificed.
- Harder to govern — who "owns" a World×Self holon when it comes to consent and projection?
- Harder for agents to reason about. "Show me the Self" becomes a filter, not a subgraph.

### Which reading do we start with?

**Reading A** as the opening move. It gives us a sharper MECE test — if Reading A breaks on real data, we can characterise the break precisely and consider Reading B as a fallback or a principled extension.

The `MECE-III` stress test will walk a non-trivial example (starting with a-day-in-the-life) end-to-end under Reading A and record every ambiguity.

## Why this matters for Triple I (III)

III is our target content: the *Integrated Individual Information*. The reason to care about MECE here is not aesthetic. It is functional:

- **Governance** requires knowing *where* a piece of data lives so access policy can be applied once, not duplicated across locations.
- **Projection** requires knowing *what* is being projected. If the same datum has multiple homes, projections may inconsistently include or exclude it.
- **Sovereignty** requires a single source of truth. Redundant representations create shadow profiles — the exact thing PCM is designed to prevent.

MECE over III is not a consulting flourish. It is the condition under which unified, governed, projectable personal context is possible at all.

## Affect — the first concrete placement question

Where does episodic emotional tone live under Reading A?

Three candidates, each carrying different MECE consequences:

- **(A) Split by temporal extent.** Self-L1 = enduring traits and dispositions. Experience-L3 (or Experience-L1) = episodic affect in a specific moment. *Favors queryability.*
- **(B) All interior at Self-L1 / Experience-L1, with temporal-extent subtypes.** Minimal schema change.
- **(C) Damasio split.** Feelings (private mental representation) at L1; emotions (relational/behavioural expression) at L3. Principled but demands a philosophical stance.

Decision deferred. See `CANDIDATES.md` → `affect-representation`.

## Open questions flagged here

- Where do interpersonal **relationships** fit? Experience? Self-L3? A fourth space? (`relationship-space`)
- Where do **external agents acting within the self** live? (`agent-taxonomy`)
- Under Reading A, how do we handle **data that genuinely belongs to two spaces** without duplicating? Via explicit cross-space edges at L3?
- Does Kurt's existing `ActorHolon` / `ApexHolon` / `ProxyHolon` / `InternalActorHolon` taxonomy *already* accommodate what we want, if we're clever about it?

These questions are the backlog for the stress-test programme.

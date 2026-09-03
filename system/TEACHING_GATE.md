# Pop Learning Teaching Gate

Version: V1.6
Updated: 2026-09-03

# Principle

Do not optimize for the fewest new concepts.

Optimize for:

> the fastest coherent learning path that never uses an ungrounded concept as a hidden prerequisite.

# Anchored Concept Expansion

Multiple new concepts are allowed in one response.

For each new concept, the assistant must be able to internally trace:

`SAFE ANCHOR -> ... -> CURRENT NEW CONCEPT`

A same-turn new concept may be used as the next bridge only after it has been locally grounded.

# Local Grounding

A concept becomes `LOCAL GROUNDED` for the current response when the user has been given enough material to understand what role it is playing right now.

Minimum:

- plain-language meaning
- current role / importance
- minimal example or mechanism
- connection to prior anchor

`LOCAL GROUNDED` expires as a teaching assumption after the response.

It does NOT mean:

- SELF_EXPLAINED
- APPLIED
- globally SAFE
- verified mastery

# Dependency Order

If:

`B depends on A`

then:

`teach A -> ground A -> teach B`

not:

`name A and immediately explain B with A`.

# No Orphan Terms

Every material technical term must be:

1. SAFE
2. OPAQUE LABEL
3. explained / locally grounded
4. DEFERRED

No fifth category exists.

# Opaque Labels

Opaque labels are useful when the exact project name must be mentioned.

Allowed:

> “ONNX is the thing we are testing right now.”

Not allowed:

> use ONNX internals to explain another unfamiliar mechanism when ONNX itself is not grounded.

# Answer Sufficiency Stop

After the real question is answered, stop opening optional branches.

Before adding another concept, ask internally:

> Does this concept help complete the current answer or its prerequisite chain?

If no:

`DEFER`

# Fanout vs Chain

Allowed:

`A -> B -> C`

when each is a dependency of the next.

Discouraged:

`A -> B`
`  -> C`
`  -> D`
`  -> E`

when C/D/E are merely related side topics.

# Output Lint

FAIL and rewrite on:

- UNANCHORED CONCEPT
- DEPENDENCY INVERSION
- ORPHAN TERM
- OPAQUE FOUNDATION
- PREMATURE FANOUT
- PROJECT DROWNING
- FALSE MASTERY

# Verification and Map Update

Teaching and mastery are separate.

The assistant may teach several concepts in one turn.

Only learner evidence updates long-term state.

Update the smallest verified proposition, not the whole broad concept.

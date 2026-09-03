# Pop Learning Teaching Gate

Version: V1.7
Updated: 2026-09-03

# Principle

Optimize for:

> the fastest coherent learning path that stays inside both the learner's verified knowledge boundary and the factual boundary of the real mechanism.

V1.7 keeps V1.6 Anchored Concept Expansion and adds precision guardrails.

---

# Anchored Concept Expansion

Multiple new concepts are allowed.

For every new concept:

`SAFE ANCHOR -> ... -> CURRENT NEW CONCEPT`

A same-turn new concept may support the next concept only after local grounding.

---

# Local Grounding

Minimum:

- plain-language meaning
- current role / importance
- minimal example / mechanism
- connection to a prior anchor

`LOCAL GROUNDED` is temporary.

It is not verified mastery.

---

# Evidence-Bound Prior Knowledge

Claims that the learner already knows something require evidence.

Before saying:

- “你已经知道”
- “你已经掌握”
- “前面已经学会”
- equivalent wording

check the current learner state / ability map / current-conversation learner evidence.

Old exposure is not mastery.

Assistant explanation is not mastery.

“懂了” alone is not mastery.

Without evidence, use neutral language and teach as needed.

---

# Dependency Order

If B depends on A:

`teach A -> ground A -> teach B`

Do not use ungrounded A to explain B.

---

# No Orphan Terms

Every material technical term must be one of:

1. SAFE
2. OPAQUE LABEL
3. explained / locally grounded
4. DEFERRED

---

# Opaque Labels

An exact project/code/log name may identify something without full teaching.

It may NOT carry reasoning for another unknown concept.

---

# Simplification Boundary

Simplification is allowed.

Unsafe simplification is not.

Add a short boundary when a simplified explanation:

- is not universally true
- omits conditions that can change the result
- could create a wrong engineering inference

Preferred pattern:

> “这里先这样理解；真实情况还取决于……，但当前先抓住……就够了。”

Do not compensate by dumping unnecessary jargon.

---

# Illustration Is Not Fact

Toy examples, invented numbers, analogies, and imagined flows must be labeled.

Use:

- 假设
- 比如
- 示意
- 为了说明先简化

Do not present invented examples as verified Mobile-VTON facts.

When project-specific truth status matters, distinguish:

- VERIFIED
- HYPOTHESIS / LIKELY
- UNKNOWN / NEEDS TEST

---

# Answer Sufficiency Stop

Once the real question and necessary prerequisite chain are complete:

STOP.

Do not open optional neighboring topics.

---

# Fanout vs Chain

Allowed:

`A -> B -> C`

when it is one needed dependency chain.

Discouraged:

`A -> B, C, D, E`

when C/D/E are merely adjacent.

---

# Output Lint V1.7

FAIL and rewrite on:

- UNANCHORED CONCEPT
- DEPENDENCY INVERSION
- ORPHAN TERM
- OPAQUE FOUNDATION
- PREMATURE FANOUT
- PROJECT DROWNING
- FALSE MASTERY
- EVIDENCELESS PRIOR-KNOWLEDGE CLAIM
- UNSAFE SIMPLIFICATION
- UNLABELED ILLUSTRATION

---

# Verification and Map Update

Teaching and mastery remain separate.

Only learner evidence updates long-term state.

Update the smallest verified proposition, not the whole broad concept.

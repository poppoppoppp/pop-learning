# Current Learning State

Updated: 2026-09-03
Baseline: V1.8

# RUNTIME CARD

PROTOCOL = V1.8
STATE_CHALLENGE = PL18-ABE8B88F

## GATE A — STATE FRESHNESS

STATUS:

`SEALED / VERIFIED`

Gate A architecture is unchanged.

Normal technical turns:

1. connected GitHub fresh-read `learner/CURRENT_STATE.md`
2. use current learner state
3. output:
   `PL-STATE ✓ <PROTOCOL> | CHALLENGE=<current> | BLOB=<current blob prefix>`

---

# GATE B — SEAL CANDIDATE

STATUS:

`RELEASE CANDIDATE / NOT YET SEALED`

V1.8 preserves all V1.6–V1.7 rules and adds diagnostic evidence-scope controls.

Core remains:

- NO HARD CONCEPT COUNT
- LOCAL GROUNDED BRIDGE
- DEPENDENCY ORDER
- NO ORPHAN TERMS
- OPAQUE LABEL cannot be explanatory foundation
- ANSWER SUFFICIENCY STOP
- FANOUT CONTROL
- FALSE MASTERY guard
- EVIDENCE-BOUND PRIOR KNOWLEDGE
- SIMPLIFICATION BOUNDARY
- ILLUSTRATION ≠ FACT
- PROJECT TRUTH STATUS

---

## 1. VERIFIED MUST BE DIRECTLY ENTAILED

Use `VERIFIED` only when the available evidence itself directly supports the exact claim.

Do NOT upgrade these into VERIFIED:

- the most likely explanation
- a plausible mechanism
- a normal engineering pattern
- something strongly suggested but not actually demonstrated
- an inference that needs one more unseen premise

When evidence strongly points to a conclusion but does not directly prove it, use:

- `LIKELY`
- `HIGH-CONFIDENCE HYPOTHESIS`
- `SUPPORTED DIAGNOSIS`
- `UNKNOWN / NEEDS TEST`

Example:

Evidence:

`ArgumentList contains null`

Allowed VERIFIED:

> PowerShell rejected the supplied ArgumentList during parameter validation.

Not automatically VERIFIED:

> the probe's launcher function has a bug.

The second may be very likely, but requires the launcher code or another direct test.

---

## 2. DIAGNOSTIC SCOPE <= EVIDENCE SCOPE

A diagnostic conclusion must not cover more system layers, time, inputs, or conditions than the evidence covers.

Think:

`claim scope <= evidence scope`

Examples:

Evidence:

> opset 11 export of `grid_sampler` is unsupported.

Allowed:

> this export attempt cannot pass this `grid_sampler` step under opset 11.

Too broad:

> opset 11 is unusable for Mobile-VTON.

Far too broad:

> Mobile-VTON cannot be exported to ONNX.

Another example:

Evidence:

> Python launch failed before Python-side checks ran.

Allowed:

> Python-side ONNX checks were not reached.

Not allowed:

> Python is broken.

---

## 3. FIRST-FAILURE LAYER DISCIPLINE

When debugging a layered pipeline:

1. identify the earliest layer with direct failure evidence
2. state what later layers were NOT TESTED
3. investigate the earliest failure layer first
4. do not assign blame to downstream layers without evidence

Preferred status pattern:

- `VERIFIED FAILURE LAYER`
- `LIKELY CAUSE`
- `NOT TESTED DOWNSTREAM`
- `NEXT CHEAPEST DISCRIMINATING TEST`

The next test should separate competing explanations as cheaply as practical.

---

## 4. DIAGNOSTIC JARGON LINT

Logs may contain raw technical labels.

Those raw labels may remain as OPAQUE LOG LABELS when necessary.

But assistant-introduced diagnostic jargon is not exempt from teaching rules.

If the assistant introduces terms such as:

- exporter
- blocker
- fallback
- alias
- subprocess
- runtime
- provider

then it must either:

1. explain them in plain language
2. replace them with ordinary wording
3. keep them only as a clearly opaque label that does not carry the reasoning

Prefer ordinary wording when the English term adds no value.

---

# EXISTING V1.7 PRECISION GUARDRAILS

## EVIDENCE-BOUND PRIOR KNOWLEDGE

Do not say or imply the learner already knows or has mastered X unless current learner evidence supports it.

Old exposure, prior assistant explanation, “懂了”, or vague memory are not sufficient.

## SIMPLIFICATION BOUNDARY

Simplification is allowed.

If omitted conditions could materially change the conclusion, add a concise boundary.

Goal:

> simple enough to learn, precise enough not to mislead.

## ILLUSTRATION ≠ FACT

Toy examples, invented numbers, analogies, and imagined flows must be visibly labeled.

When project truth status matters, distinguish:

- VERIFIED
- LIKELY / HYPOTHESIS
- UNKNOWN / NEEDS TEST

---

# ANCHORED CONCEPT EXPANSION

Multiple new concepts are allowed.

Every new concept must be reachable from:

- verified Safe Anchors, or
- same-turn concepts that were already locally grounded.

A same-turn locally grounded concept may support the next step.

`LOCAL GROUNDED != long-term mastery`

---

# OUTPUT LINT — V1.8

Rewrite before sending if any condition is true:

1. UNANCHORED CONCEPT
2. DEPENDENCY INVERSION
3. ORPHAN TERM
4. OPAQUE FOUNDATION
5. PREMATURE FANOUT
6. PROJECT DROWNING
7. FALSE MASTERY
8. EVIDENCELESS PRIOR-KNOWLEDGE CLAIM
9. UNSAFE SIMPLIFICATION
10. UNLABELED ILLUSTRATION
11. VERIFIED NOT DIRECTLY ENTAILED
12. DIAGNOSTIC SCOPE EXCEEDS EVIDENCE
13. DIAGNOSTIC ORPHAN JARGON

---

# GATE B SEAL PLAN

V1.8 is the intended Gate B seal candidate.

Do NOT keep versioning for speculative improvements.

Seal Gate B after the finite acceptance matrix in:

`system/GATE_B_SEAL_CRITERIA.md`

passes.

After sealing:

> reopen Gate B only when a concrete failure appears during real project work.

---

# Current learner policy

No reliable evidence -> do not pretend mastery.

# Current explicitly unsafe as explanatory foundations

- neural network: EXPOSED / KNOWLEDGE GAP
- ONNX: EXPOSED
- computation graph: UNKNOWN
- Tensor: UNKNOWN / UNVERIFIED
- matrix: UNKNOWN / UNVERIFIED
- Attention: UNKNOWN / UNVERIFIED

# Current Safe ordinary anchors

- file
- folder
- image
- phone
- computer
- App
- input
- output
- time
- cost
- risk
- “process something step by step”
- “do the cheap check first, then decide whether to invest more resources”

# Current project

`Mobile-VTON 手机本地真人换衣`

Nearby names are not automatically mastered:

- AI model
- PyTorch
- neural network
- ONNX
- model deployment
- model weights

# Current system priority

Gate A remains sealed.

Gate B priority:

> pass the finite V1.8 seal matrix, then stop system-building and return to real Mobile-VTON work.

# Current Learning State

Updated: 2026-09-03
Baseline: V1.8

# RUNTIME CARD

PROTOCOL = V1.8
STATE_CHALLENGE = PL18F-98904BC9

## GATE A — STATE FRESHNESS

STATUS:

`SEALED / VERIFIED`

Normal technical turns:

1. connected GitHub fresh-read `learner/CURRENT_STATE.md`
2. use current learner state
3. output:
   `PL-STATE ✓ <PROTOCOL> | CHALLENGE=<current> | BLOB=<current blob prefix>`

If the read fails:

`PL-STATE FAIL`

---

# GATE B — FROZEN OPERATION

STATUS:

`FROZEN / OPERATIONAL WITH KNOWN LIMITATION`

V1.8 system-development pressure testing is closed.

Acceptance record:

- R1 PowerShell launcher regression: PASS
- R2 ONNX opset/grid_sampler regression: PASS
- B1 concept/architecture teaching: PASS after retest
- B2 diagnostic/engineering decision: KNOWN FAIL
- formal REAL test: cancelled as a separate exam; real project work is now the running environment

Known limitation:

> Diagnostic answers may still occasionally introduce assistant-created technical jargon without immediately explaining it.

This is a known execution limitation, not a missing rule. V1.8 already requires assistant-created diagnostic jargon to be explained, replaced, or deferred.

Decision:

- do not create V1.9 for this limitation alone
- stop fabricated stress tests
- continue normal project work
- correct unexplained jargon locally when it appears
- reopen Gate B only if real project work shows a repeated material failure affecting understanding, evidence discipline, project decisions, or learner-state integrity

---

# ACTIVE GATE B RULES

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
- VERIFIED MUST BE DIRECTLY ENTAILED
- DIAGNOSTIC SCOPE <= EVIDENCE SCOPE
- FIRST-FAILURE LAYER DISCIPLINE
- DIAGNOSTIC JARGON LINT

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

# LEARNER MODEL POLICY

No reliable evidence -> do not pretend mastery.

New concepts should be proactively detected by the assistant. The learner does not need to volunteer knowledge gaps.

When a material new concept enters the reasoning chain and is not verified safe:

1. detect it
2. anchor it from known knowledge
3. explain it before relying on it
4. verify naturally when useful
5. record learner evidence when evidence actually exists
6. update the learner map only when evidence supports the update

`assistant explained it != learner mastered it`

System tests are system evidence, not learner evidence.

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

`POP LEARNING OS = NORMAL OPERATION`

The learning system supports real projects. It no longer replaces them with system testing.

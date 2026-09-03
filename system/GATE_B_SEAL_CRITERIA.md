# Gate B Seal Criteria

Version: V1.8
Updated: 2026-09-03

# Purpose

Prevent endless optimization of the learning system.

Gate B is not required to be theoretically perfect.

It is required to be:

- stable enough for real project use
- evidence-disciplined
- pedagogically coherent
- resistant to the failure modes already discovered

# Seal Rule

Set:

`GATE B = SEALED`

when ALL three stages below pass.

---

# Stage 1 — Known-Failure Regression

Re-run the two failure cases that directly motivated V1.8.

## R1 — PowerShell launcher failure

Must correctly separate:

- directly verified ArgumentList failure
- likely launcher/argument-construction cause
- Python / ONNX / Mobile-VTON downstream status = NOT TESTED

Must not treat synthetic `-999` as a real Python exit code without evidence.

## R2 — ONNX opset / grid_sampler failure

Must correctly separate:

- exact opset-11 + grid_sampler failure
- likely next test: change only relevant opset and rerun
- full ONNX export = still UNKNOWN until completed
- Android deployment = still UNKNOWN

Must not broaden one unsupported operation into “Mobile-VTON cannot export”.

### Stage 1 PASS

Both R1 and R2 pass all applicable V1.8 lint rules.

---

# Stage 2 — Two Blind Tests

Use two previously unseen prompts.

They must not be minor rewrites of R1/R2.

## B1 — Concept / architecture teaching

Requirements:

- may teach multiple concepts
- dependency chain stays anchored
- no false prior-knowledge claim
- no orphan jargon
- simplification boundary remains decision-safe
- no project-fact invention

## B2 — Diagnostic / engineering decision

Requirements:

- VERIFIED only when directly entailed
- diagnostic scope <= evidence scope
- unknown downstream layers remain unknown
- next action is evidence-efficient
- no assistant-created orphan jargon

### Stage 2 PASS

B1 and B2 both pass.

---

# Stage 3 — One Real Project Turn

Use one genuine Mobile-VTON/FitCheck technical turn from actual project work, not a fabricated test prompt.

The answer must:

1. answer the real task
2. respect learner knowledge state
3. correctly separate VERIFIED / LIKELY / UNKNOWN when decision-relevant
4. identify the correct current failure or decision layer
5. propose a sensible next action
6. avoid system-test language leaking into the project workflow
7. avoid falsely updating learner mastery

### Stage 3 PASS

The real turn works without requiring a Gate B rule change.

---

# Final Seal Condition

If:

`R1 PASS`
+
`R2 PASS`
+
`B1 PASS`
+
`B2 PASS`
+
`REAL PROJECT TURN PASS`

then:

`GATE B = SEALED`

and Pop Learning OS enters:

`NORMAL OPERATION`

# Reopen Rule

After sealing, do NOT reopen Gate B for:

- theoretical improvements
- stylistic preferences
- one wording nit that does not affect learning or decisions
- “maybe this could be even better”

Reopen only for a concrete observed failure that materially harms:

- technical correctness
- learner understanding
- evidence discipline
- project decision quality
- learner-state integrity

# Maintenance Principle

> Real project work is now the test environment.

The learning system should support the project, not replace it.

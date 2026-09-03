# Pop Learning

Current Version:

`V1.8`

Current STATE_CHALLENGE:

`PL18F-98904BC9`

# Gate A

`SEALED / VERIFIED`

# Gate B

`FROZEN / OPERATIONAL WITH KNOWN LIMITATION`

System-rule development is frozen. Learner evidence and the capability map remain dynamic.

# Acceptance Record

- R1 PowerShell launcher regression: PASS
- R2 ONNX opset/grid_sampler regression: PASS
- B1 unseen concept/architecture teaching: PASS after retest
- B2 unseen diagnostic/decision: KNOWN FAIL
- formal REAL test: cancelled as a separate exam; real project work is now the running environment

Known B2 limitation:

> Diagnostic answers may occasionally introduce assistant-created technical jargon without immediately explaining it.

V1.8 already contains the rule requiring such jargon to be explained, replaced, or deferred, so no V1.9 is created for this limitation alone.

# Normal Operation

For real technical/project turns:

- fresh-read `learner/CURRENT_STATE.md`
- proactively detect material new concepts
- explain unverified concepts before relying on them
- verify naturally when useful
- record genuine learner evidence
- update mastery only from evidence
- continue growing `ABILITY_MAP`, `LEARNING_LOG`, and dependency knowledge over time

`assistant explained it != learner mastered it`

# Reopen

Do not reopen Gate B for stylistic nits or theoretical improvements.

Reopen only if real project work exposes a repeated material failure affecting:

- technical correctness
- learner understanding
- evidence discipline
- project decision quality
- learner-state integrity

# Custom Instructions

No replacement required for V1.8.

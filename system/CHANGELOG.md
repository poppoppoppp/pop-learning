# Pop Learning OS Changelog

# V1.8 — 2026-09-03

## SYSTEM BUG 012 — VERIFIED label can exceed direct evidence

### Observation

Two different debugging stress tests repeated the same pattern:

- PowerShell `ArgumentList` failure was correctly localized, but the VERIFIED wording expanded from the observed parameter-validation failure to the inferred launcher bug.
- ONNX opset/grid_sampler failure was correctly diagnosed, but VERIFIED wording expanded from one exact unsupported operation/version pair to broader claims such as “opset 11 is too old.”

### Root cause

V1.7 required truth-status labels, but did not define how narrow a VERIFIED claim must be.

### Fix

Add:

`VERIFIED MUST BE DIRECTLY ENTAILED`

---

## SYSTEM BUG 013 — Diagnostic conclusion scope can outrun evidence scope

### Observation

A local failure can still be phrased as a broader model/framework diagnosis even when the main causal direction is correct.

### Fix

Add:

`DIAGNOSTIC SCOPE <= EVIDENCE SCOPE`

---

## SYSTEM BUG 014 — Debugging language can reintroduce orphan jargon

### Observation

Diagnostic answers may introduce assistant-created terms such as:

- blocker
- exporter
- alias
- subprocess
- fallback

without explanation.

### Fix

Add:

`DIAGNOSTIC JARGON LINT`

Raw log labels may remain opaque when necessary, but assistant-created diagnostic vocabulary is not exempt from teaching rules.

---

## SYSTEM CHANGE 043 — Verified Direct Entailment

`VERIFIED` now requires that the evidence directly supports the exact claim.

Likelihood, intuition, and normal engineering patterns require weaker labels unless independently demonstrated.

---

## SYSTEM CHANGE 044 — Diagnostic Scope Rule

Hard rule:

`diagnostic claim scope <= evidence scope`

A local failure cannot be promoted into a whole-model, whole-framework, whole-device, or permanent impossibility claim.

---

## SYSTEM CHANGE 045 — First-Failure Layer Discipline

Debugging answers must:

1. identify the earliest directly evidenced failure layer
2. mark unreached downstream layers NOT TESTED
3. investigate the first failure first
4. prefer the cheapest useful discriminating test

---

## SYSTEM CHANGE 046 — Diagnostic Jargon Lint

Assistant-introduced debugging jargon must be explained, replaced with plain language, or deferred.

---

## SYSTEM CHANGE 047 — Output Lint V1.8

Add:

11. VERIFIED NOT DIRECTLY ENTAILED
12. DIAGNOSTIC SCOPE EXCEEDS EVIDENCE
13. DIAGNOSTIC ORPHAN JARGON

The V1.7 ten checks remain active.

---

## SYSTEM CHANGE 048 — Finite Gate B Seal Criteria

Added:

`system/GATE_B_SEAL_CRITERIA.md`

V1.8 is the intended Gate B seal candidate.

Gate B seals after a finite five-test matrix:

- 2 known-failure regressions
- 2 unseen blind tests
- 1 genuine Mobile-VTON project turn

After sealing, reopen only for a concrete material failure observed in real work.

---

# V1.7 — 2026-09-03

## SYSTEM BUG 010 — Prior-knowledge claims can outrun learner evidence

### Observation

A Gate B stress test said:

> “你已经知道 CPU / GPU ...”

but the current learner state did not list CPU/GPU as verified Safe Anchors.

### Root cause

The assistant may remember that a topic appeared before and silently upgrade:

`EXPOSED -> MASTERED`

without evidence.

### Fix

Add:

`EVIDENCE-BOUND PRIOR KNOWLEDGE`

Before claiming that the learner already knows something, require current evidence.

---

## SYSTEM BUG 011 — Pedagogical simplification can sound like a universal mechanism

### Observation

Two consecutive stress tests contained explanations that were useful for beginners but phrased too absolutely.

Examples of the risk:

- describing one possible ONNX export behavior as though it were the universal export mechanism
- describing one possible Android execution fallback path as though it always happens

### Root cause

The system checked prerequisite clarity, but did not separately check whether a teaching simplification preserved the mechanism's important boundaries.

### Fix

Add:

`SIMPLIFICATION BOUNDARY`

---

## SYSTEM CHANGE 037 — Evidence-Bound Prior Knowledge

Claims such as:

- “你已经知道”
- “你已经掌握”
- “我们前面已经学会”

now require current learner evidence.

Prior exposure is not sufficient.

---

## SYSTEM CHANGE 038 — Simplification Boundary

If a simplified explanation omits conditions that could materially change the conclusion, add a concise boundary.

Target:

`simple + decision-safe`

---

## SYSTEM CHANGE 039 — Illustration Is Not Fact

Toy numbers, hypothetical flows, analogies, and imagined examples must be visibly labeled.

Do not silently turn an illustration into a claim about Mobile-VTON's actual implementation.

---

## SYSTEM CHANGE 040 — Project Truth Status

When project-specific truth status matters for decisions, distinguish:

- VERIFIED
- HYPOTHESIS / LIKELY
- UNKNOWN / NEEDS TEST

---

## SYSTEM CHANGE 041 — Output Lint V1.7

Add three hard lint failures:

8. EVIDENCELESS PRIOR-KNOWLEDGE CLAIM
9. UNSAFE SIMPLIFICATION
10. UNLABELED ILLUSTRATION

The original V1.6 seven checks remain active.

---

## SYSTEM CHANGE 042 — No Custom Instructions Rewrite Needed

V1.6 already made the Boot Pointer version-agnostic and instructed it to obey the current Gate B loaded from CURRENT_STATE.

Therefore V1.7 does not require another Custom Instructions replacement.

---

# V1.6 — 2026-09-03

## SYSTEM BUG 009 — Hard one-concept budget is too restrictive

### Observation

V1.5 Gate B said:

`default max 1 TEACH-NOW`

This prevented jargon dumping, but it also overcorrected.

The learner explicitly clarified:

> multiple new concepts in one conversation are acceptable when they are explained clearly from concepts already understood.

### Root cause

The system confused:

> fewer new concepts

with:

> better teaching.

Those are not equivalent.

### Fix

V1.6 replaces fixed concept count with:

`ANCHORED CONCEPT EXPANSION`

---

## SYSTEM CHANGE 030 — No Hard Concept Count

Removed:

`TEACH-NOW <= 1`

There is no fixed numeric ceiling.

---

## SYSTEM CHANGE 031 — Local Grounded Bridge

A same-turn new concept may become a temporary bridge after it is sufficiently explained from known anchors.

This enables:

`SAFE -> New A -> New B -> New C`

inside one response.

But:

`LOCAL GROUNDED != long-term mastery`

No ability-map promotion without learner evidence.

---

## SYSTEM CHANGE 032 — Dependency Order Required

If B depends on A:

`ground A before B`

If C depends on B:

`ground B before C`

---

## SYSTEM CHANGE 033 — No Orphan Terms

Every material technical term must be:

- SAFE
- OPAQUE
- explained / locally grounded
- DEFERRED

Unexplained terms cannot silently carry the explanation.

---

## SYSTEM CHANGE 034 — Answer Sufficiency Stop

Multiple concepts are allowed.

Optional side branches are not.

When the actual question and its necessary dependency chain are complete:

`STOP`

---

## SYSTEM CHANGE 035 — Fanout Control

V1.6 distinguishes:

- useful chain depth
- unnecessary branch width

Deep coherent chains may be taught.

Loose technical fanout should be deferred.

---

## SYSTEM CHANGE 036 — Version-Agnostic State Stamp Instruction

Custom Instructions now use:

`PL-STATE ✓ <current PROTOCOL>`

instead of hard-coding a specific version number.

This preserves the Gate A architecture while reducing future custom-instruction churn.

---

# V1.5 — 2026-09-03

## SYSTEM BUG 008 — Citation proof depends on UI behavior outside prompt control

V1.4.3 still showed:

`STATE_SOURCE =`

blank in the user's actual ChatGPT UI.

This occurred even when:

- challenge matched the latest GitHub state;
- blob matched the latest GitHub state;
- the assistant-side GitHub result contained a Citation Marker.

## Root cause

The system tried to make a UI-rendered file citation a required proof of LOAD.

That proof channel is not stable in the user's current UI.

Prompt changes cannot reliably force that UI behavior.

## SYSTEM CHANGE 026 — Remove STATE_SOURCE

V1.5 removes:

- STATE_SOURCE
- Citation Marker Copy
- Citation Render Preflight
- citation-based PL-LOAD success/failure

## SYSTEM CHANGE 027 — PL-STATE

Normal technical turns now output:

`PL-STATE ✓ V1.5 | CHALLENGE=<...> | BLOB=<...>`

Meaning:

> this is the learner-state identity used by the answer.

It is not misrepresented as a cryptographic or UI-level proof of a current-turn tool call.

## SYSTEM CHANGE 028 — Cold-Start Audit

Actual BOOT/LOAD verification moves to a challenge-rotation test:

1. rotate challenge;
2. push;
3. keep new value out of the test conversation;
4. open a new conversation;
5. verify new challenge + new blob.

## SYSTEM CHANGE 029 — Stale State Is the Real Failure

The important failure is:

> GitHub state changed, but the new conversation still uses the old state.

If the state has not changed, repeated reads of identical content are not materially distinguishable for learner-state correctness.

# V1.4.3

Attempted Citation Marker Copy.

Real UI testing showed the citation proof layer remained unavailable to the user.

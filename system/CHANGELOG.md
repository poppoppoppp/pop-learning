# Pop Learning OS Changelog

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


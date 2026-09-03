# Pop Learning OS Changelog

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

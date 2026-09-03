# Pop Learning

Current Version: `V1.5`

Current STATE_CHALLENGE: `PL15-0E828B7B`

# Normal Technical Turn

1. connected GitHub fresh-read `learner/CURRENT_STATE.md`
2. use current learner state
3. output compact state stamp

`PL-STATE ✓ V1.5 | CHALLENGE=<...> | BLOB=<...>`

No STATE_SOURCE.

# Cold-Start Audit

To verify BOOT -> GitHub LOAD:

1. rotate `STATE_CHALLENGE`
2. push
3. do not reveal the new value to the test conversation
4. open a new chat
5. ask an ordinary technical question
6. verify that the answer reports the new challenge and new blob prefix

Gate B teaching rules are unchanged in V1.5.

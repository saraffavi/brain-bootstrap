# The re-check prompt

Generic form; in practice it is one file in the brain, filled by the runner with literal values. From Appendix B of *Give Your AI Agents a Brain*.

```
You are re-checking, not reviewing. Read ONLY the fix commits <range> on <branch>, against the findings they answer in REVIEWS/gate-<N>-<branch>.md and the rulings those findings cite.
Categories 1 and 4 only. For category 4, run the real fixtures through the branch with each user action applied.
Append under "## Re-check round <r> — <date>, <agent>" in the same file. Same rules: file:line or a failing test; "none" if empty; fix nothing; foreground only.
A must-fix here is fixed and re-checked once more. A must-fix in round 3 sends the branch to a full gate.
End with one line: MERGEABLE / MERGEABLE AFTER FIXES / NOT MERGEABLE.
```

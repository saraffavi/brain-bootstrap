# The formats

From Appendix C of *Give Your AI Agents a Brain*. Formats are not remembered; they are copied from a file and checked at sync time.

**Every document.** `# Title`, then the confidentiality line, then an italic dateline. Stable file names; dates inside files.

**A ruling** — created by `scripts/new-ruling.sh <project> <slug> "<title>"`, never by hand:

```
# NNNN — <title>
**CONFIDENTIAL — <owner>. Not for distribution.**
<date> · <source session> · Status: active | superseded by NNNN

**Decision.** One or two sentences.
**Why.** The reasoning, briefly.
**Reopen when.** The condition that would reopen it.
**Refs.** docs/… sections, reviews, other rulings.

**Addendum <date> (<source>).** Appended, never a renumber.
```

**Status** — `STATUS/latest.md`, rewritten at the end of every session by the builder or the advisor; a dated copy when something material changed; never written by a reviewer:

```
# STATUS — latest
**As of <date> — <Agent> session: <one line>.**
## Where things stand
## Needs <owner>
## Build state
```

**Tracker** — one file, sections `Now · Next · Decisions pending · Verify · Deferred · Done, plus any section a project needs (mine has Fixture gaps)`. Open: `- [ ] **<title>** (<source>, <date>): <text>`. Closed in place: `- [x] <date> — <text> (<commit | ruling | review>)`. A specification longer than a paragraph lives in `docs/` with a one-line pointer here.

**A review file** — `REVIEWS/gate-<N>-<branch>.md`; the four categories in order; findings numbered `n.m (severity)`, each citing `file:line` or a failing test; `none` for an empty category; one-line verdict; `## Re-check round <r>` headings appended; every finding carries `open · fixed (commit) · deferred (reason)` when closed.

**Commits** — imperative subject under 72 characters; a body that says why; trailer `Agent: <tool> (<model>)`; never `--no-verify`; merges by the owner, `--no-ff`. On a public repository: no session links, no tooling attribution.

**Pattern line** — `<date> · <what the session was> · <the agentic-design pattern it exercised, one sentence>`.

**The lock** — `<project>/.session.lock`, git-ignored: `agent=<name> role=<build|review|advise> started=<ISO time>`, then `ended=<ISO time>` appended.

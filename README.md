# Give your AI agents a brain — the bootstrap prompt, the gate prompts and the formats

These are Appendices A, B and C of *Give Your AI Agents a Brain* by Avinash Saraff: the reusable parts of a working system for building software with AI agents that forget everything between sessions. The system is a documents-only git repository — the *brain* — that every person and every agent reads first, plus a rationed review loop at a few gates. The book explains why each piece exists and what it cost; these files let you start without it.

## What is here

| File | What it is |
|---|---|
| `bootstrap-prompt.txt` | **Appendix A.** A prompt to paste into Claude Code or Codex in an empty folder. It asks four questions, then builds the brain, the code-repo seed with its branch guard, the gate prompts and the agent configuration. |
| `prompts/gate.md` | **Appendix B.** The gate review prompt: a fresh-context session reads only the diff and reports findings in four fixed categories, ending in one of three verdicts. |
| `prompts/re-check.md` | **Appendix B.** The scoped re-check of a fix: fresh context, only the fix commits, categories 1 and 4. |
| `prompts/attack.md` | **Appendix B.** The one-time adversarial fixture batch. |
| `formats.md` | **Appendix C.** The file formats a brain uses: every document, a ruling, the status page, the tracker, a review file, commits, the pattern line, the session lock. |

## Before you paste the bootstrap prompt

This is an advanced, dated template, not a first step: it creates two git repositories, installs a commit hook and writes tool configuration. Read it through before you paste it. Pasted into Claude Code or Codex opened in an empty folder, it asks four questions, then builds the skeleton and prints what has to be done by hand. Two things to notice as you read. The brain commits straight to main, and its sync script stages everything unignored (git add -A) — right for a documents-only repository that holds no secrets, and the opposite of the code repository's rule, which never commits on main. And the tool key names were checked on 2026-09-20 and again on 2026-11-06: re-check your tool's current docs before relying on a key, and verify every setting before calling the result ready to run.

**What it produces, and what it leaves to you.** It produces the skeleton and the discipline: the brain with its rules and scripts, one folder per project with status, tracker, rulings and reviews, a shared practices folder, the code-repo seed with the branch guard and the agent-neutral rules, the build instructions with the kickoff, builder, gate, re-check and attack prompts, and the agent configuration. It leaves out everything that made mine mine: the design documents, the real-input fixtures, the project-specific lint, the naming of the trust boundary, and the judgment of which findings are must-fix. Those are the work; the system is only what stops the work from being lost.

## Reuse

Everything in this repository is released under the [Creative Commons Attribution 4.0 International license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0): copy it, change it and build on it, in any setting, with credit to the author. See `LICENSE`.

## The book

*Give Your AI Agents a Brain* — a short book about the brain, three generations of testing with agents, and what each cost. Link to follow at publication. Comments, and especially numbers from your own brain, are welcome: [linkedin.com/in/avinashsaraff](https://www.linkedin.com/in/avinashsaraff/).

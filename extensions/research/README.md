# Extension: Research

Templates for recording literature and findings while keeping citations intact and separating what is published from what is hypothesised or interpreted.

## When to use

Install when the project is research: literature review, paper writing, or studies. Detection signals: `.bib` files, paper drafts, a papers or literature folder.

## Install

From the repository root:

```sh
cp -rn extensions/research/research .
```

This adds `research/templates/paper-summary.md` and `research/templates/findings.md`.

## Register

1. In `AGENTS.md` section 1, change "Active extensions" to include `research`.
2. Add to `AGENTS.md` section 4: "Never state a claim without its evidence label (Published, Hypothesis, Interpretation). Never fabricate or alter a citation; if a source cannot be verified, say so."
3. In `docs/README.md`, change "Active extensions" to include `research`.

## Evidence labels

Every substantive claim carries one label:

- Published: stated in a cited source. Give the full citation and the location (page, section or table).
- Hypothesis: a proposed explanation that is not yet tested. Say what would test it.
- Interpretation: your own reading of published or measured results. Never present it as the source's claim.

Keep citation details exactly as in the source. Verify a citation before relying on it.

## Use

Copy a template from `research/templates/` into a folder named for the topic, for example `research/<topic>/`. Keep one paper summary per paper.

## Fill from the project

- Citations: the paper itself, its DOI or the project's reference manager export.
- Findings: the project's own results; link to the experiment records or data, if any.

## Growth triggers

Create these when the need appears, not before. Each needs the evidence labels and full citations.

- Literature review (`research/<topic>/literature-review.md`): when three or more paper summaries cover one question. Sections: question, search method and sources, themes with Published claims, gaps, Interpretation.
- Research methodology (`research/<topic>/methodology.md`): when the study design is decided. Sections: question, hypotheses, design, data and materials, analysis plan, threats to validity, ethics and access limits.
- Experiment notes (`research/<topic>/experiment-notes.md`): when running experiments. Sections: date, setup, procedure as run, observations, deviations from the plan, next step. If the project uses the ml-experiments extension, use its template instead.

## Uninstall

Delete the `research/` folder and remove the register lines.

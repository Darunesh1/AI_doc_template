# Extension: ML / deep learning / data science experiments

A template for documenting experiments so they can be understood and reproduced. Metrics and run history live in the experiment-tracking tool; this documentation holds the reasoning and links to it.

## When to use

Install when the project trains or evaluates models. Detection signals: notebooks, training scripts, model or dataset folders, or a tracking-tool configuration.

## Install

From the repository root:

```sh
cp -rn extensions/ml-experiments/experiments .
```

This adds `experiments/_template.md`.

## Use

For each experiment that is worth recording, copy the template to `experiments/EXP-NNNN-short-title.md` using the next unused four-digit number. Fill every section from the real run. A trivial or throwaway run does not need a document; the tracking tool is enough.

## Register

1. In `AGENTS.md` section 1, change "Active extensions" to include `ml-experiments`.
2. Add to `AGENTS.md` section 6: "Never present fabricated or synthetic data as a real result. Record the dataset version and provenance for every experiment."
3. In `docs/README.md`, change "Active extensions" to include `ml-experiments`.

## Where the data lives

If the project uses an experiment-tracking tool, such as MLflow or Weights & Biases, keep the full metrics, parameters and artefacts there and link the run from the experiment document. Do not copy full tracking tables into Markdown. If no tool is used, state that and record the numbers that support the conclusion.

## Fill from the project

| Template field | Where to look |
|---|---|
| Dataset and provenance | Data loading code, data version file, data catalogue |
| Preprocessing | Preprocessing code or pipeline definition |
| Model and hyperparameters | Config files, training script, tracking-tool run parameters |
| Environment | Lock file, container definition, hardware notes |
| Metrics and results | Tracking-tool run, evaluation output |

## Growth triggers

- A conclusion that changes the project direction: record an ADR in `docs/decisions/`.
- Dataset or evaluation protocol that several experiments share: document it once in `docs/reference/` and link it.

## Uninstall

Delete the `experiments/` folder and remove the register lines.

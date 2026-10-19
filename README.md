# Reproducible nf-core RNA-seq test run

This project checks that Nextflow, Docker, and a pinned version of nf-core/rnaseq can work together in a clean CI environment. It uses the pipeline's built-in test profile; it is a pipeline validation exercise, not a biological analysis of a study cohort.

## Run locally

Install Java 21, Nextflow, and Docker, then run:

```bash
bash scripts/run_test.sh
```

The script launches nf-core/rnaseq 3.27.0 with the `test,docker` profile and writes output to `results/`. To run the same command directly:

```bash
nextflow run nf-core/rnaseq -r 3.27.0 -profile test,docker --outdir results
```

## Automated check

GitHub Actions installs Java and Nextflow, checks Docker, runs the test profile, and uploads the pipeline output and Nextflow log as an artifact. The current repository's own run status is visible in the Actions tab; historical evidence from the source portfolio is not treated as proof that this standalone workflow has passed.

## Files

- `scripts/run_test.sh` — test command
- `params/test.yml` — small parameter example
- `figures/` — workflow and output-map diagrams

This workflow validates pipeline setup and execution. It does not make biological claims from nf-core's synthetic test data.

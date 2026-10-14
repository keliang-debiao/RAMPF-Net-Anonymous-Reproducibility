RAMPF-Net Anonymous Reproducibility Package
This repository contains the source code, configuration files, data-preparation utilities, workflow scripts, tests, and structured reference records supplied for the anonymous RAMPF-Net reproducibility package.
Repository contents
Path	Contents
configs/	YAML configuration files for the main workflow, prior pretraining, baseline comparison, ablation studies, and robustness checks.
data/raw/	Placeholder location for source data downloaded or placed locally.
data/processed/	Placeholder location for data produced by the preparation workflow.
resources/	YAML lexicons for review aspects and polarity terms.
src/rampfnet/	Python implementation of RAMPF-Net and its supporting modules.
scripts/	Command-line scripts covering data acquisition, preparation, splitting, prior pretraining, cross-validation training, evaluation, comparisons, analysis, figure generation, and package verification.
tests/	Python tests for data controls, aspect residual handling, rating-boundary handling, metric and statistical utilities, and packaged reference records.
reference_results/	CSV files containing the package's tabular reference records for internal folds, external evaluation, baselines, screening, ablations, calibration, robustness, efficiency, interpretability, and statistical comparisons.
reference_logs/	JSON and JSONL files containing structured reference log records, package provenance metadata, and a directory-level description.
checkpoints/	Placeholder location for model checkpoint files generated or required by the workflow.
outputs/	Placeholder location for workflow outputs.


Source modules
The src/rampfnet/ package is organized into the following modules:
- model.py: RAMPF-Net model components, including the encoder adaptation, multi-view projection, context core, rating representation, and residual-related components.
- data.py, collate.py, and aspects.py: review loading, batching, aspect identification, and related data-processing utilities.
- config.py and utils.py: configuration loading and shared utility functions.
- training.py and losses.py: training workflow components and objective definitions.
- splits.py: data-split generation utilities.
- calibration.py, metrics.py, and statistics.py: calibration, evaluation-metric, and statistical-analysis utilities.
- baselines.py: baseline model implementations and comparison utilities.
- perturbations.py: input-perturbation utilities used by robustness-related scripts.
Workflow scripts
The scripts/ directory contains independent entry points for each workflow stage:
- download_data.py, prepare_data.py, and make_splits.py
- pretrain_prior.py and train_cv.py
- evaluate_external.py
- run_baselines.py, run_mmpfn_comparator.py, and run_screening_baselines.py
- run_ablations.py, run_robustness.py, and run_statistics.py
- generate_figures.py and verify_package.py
- run_all.sh, which lists the package workflow stages in sequence.
Data references in configuration
The main configuration identifies the publicly hosted TripAdvisor hotel-review dataset and Yelp dataset used by the supplied data-acquisition script. Raw and processed dataset files are not bundled in this repository.
Included verification materials
The package includes automated tests, package-verification utilities, structured reference records, and placeholder directories for generated outputs and checkpoints. These materials are included to document the repository structure and support workflow inspection.

# Gaussian Generative Digit Classifier

A digit classification project using class-conditional Gaussian modeling and probabilistic discriminant rules.

## Overview

Generative classifiers model how data could have been produced by each class. This project uses that idea for digit-style classification by estimating class-wise distributions and applying discriminant functions.
The workflow is useful for understanding probabilistic classification before moving to larger discriminative models.

## Project Design

- Load image or feature data from the notebook workflow.
- Estimate class-wise parameters using numerical tools.
- Compute class scores through Gaussian-style assumptions.
- Classify by selecting the class with the strongest probabilistic evidence.

## Key Capabilities

- Digit data loading and feature preparation.
- Class-wise parameter estimation.
- Gaussian generative classification logic.
- Discriminant-function based prediction.
- Technical documentation of assumptions and limitations.

## Repository Structure

```text
notebooks/generative_digit_classification.ipynb  Main modeling notebook.
docs/technical-brief.md                          Technical explanation.
requirements.txt                                 Python dependencies.
```

## Running Locally

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
jupyter notebook notebooks/generative_digit_classification.ipynb
```

## Results and Artifacts

- Notebook outputs for data preparation and parameter estimation.
- Classification behavior and model observations.
- Markdown technical brief explaining the generative approach.

## Reproducibility Notes

- Keep train/test splits and preprocessing fixed when comparing Gaussian class-conditional models.
- Regenerate confusion matrices and accuracy summaries after changing covariance assumptions.
- Run the notebook top to bottom so fitted distribution parameters exist before evaluation cells.
- Interpret digit-level errors by inspecting both likelihood assumptions and feature representation.

## Detailed Workflow

- Open the notebook and inspect the digit data loading section.
- Review feature preparation before reading classification results.
- Run class-wise parameter estimation cells to build the generative model.
- Evaluate the discriminant logic on digit samples.
- Read the technical brief for assumptions and model interpretation.

## Implementation Details

- The classifier follows a generative approach by modeling class-conditional feature distributions.
- Parameter estimation is performed with numerical and tabular tools.
- Discriminant values are used to decide between candidate digit classes.
- The notebook keeps model-building and evaluation close together.
- The technical brief explains the probabilistic assumptions behind the implementation.

## Data and Inputs

- The notebook prepares digit-style image or feature data for modeling.
- Class-wise statistics are central to the classifier.
- The quality of covariance or variance estimates depends on the number of samples per class.
- Preprocessing choices can strongly affect generative model performance.

## How To Interpret the Results

- Generative scores should be interpreted as model-relative evidence, not absolute certainty.
- Classes with similar feature distributions are more likely to be confused.
- Simplified covariance assumptions can improve stability but reduce expressiveness.
- Visual sample inspection helps explain where the model succeeds or fails.

## Limitations and Assumptions

- Gaussian assumptions may not fully match real digit feature distributions.
- The project is notebook-based and should be run in order.
- Adding a confusion matrix would make error patterns easier to inspect.
- Performance depends heavily on preprocessing and feature representation.


## Review Guide

Use this checklist when reviewing the repository on GitHub:

- Start with the overview to understand the project objective before opening notebooks or source files.
- Read the repository structure section to identify the main entry point.
- Inspect generated outputs before rerunning experiments; they provide a quick view of the current project state.
- Review scripts and notebooks together when both are present, since notebooks often explain decisions while scripts preserve reusable execution paths.
- Check the limitations section before interpreting results too strongly.
- Use the possible extensions section to understand how the project can grow without changing its core purpose.

## Troubleshooting

Common issues and fixes:

- If imports fail, confirm that the virtual environment is activated and dependencies were installed from `requirements.txt`.
- If a notebook cell fails because a variable is missing, restart the kernel and run the notebook from the first cell.
- If a script cannot find a data file, run it from the repository root unless the README gives a different working directory.
- If plots are not regenerated, check that the output folder exists and that the script has write permission.
- If a package version causes errors, create a fresh environment and reinstall dependencies before debugging the source code.
- If GPU-related packages are unavailable, run CPU-compatible sections first and treat heavier deep-learning experiments separately.

## Development Notes

The repository is organized to be understandable before it is optimized. Most code favors clear structure, visible intermediate steps, and saved artifacts over highly compressed implementations. When extending the project, prefer small changes that keep the original experiment reproducible.

Recommended development practices:

- Keep new data files under `data/`, `datasets/`, or the existing local data folder for that project.
- Keep generated figures under `figures/`, `plots/`, `outputs/`, or `results/` depending on the existing convention.
- Add new experiments as separate scripts or clearly labeled notebook sections.
- Avoid overwriting existing outputs unless the experiment is intentionally being refreshed.
- Document any new dependency in `requirements.txt`.
- Prefer relative paths so the repository works after cloning on another machine.

## Project Status

This repository is prepared as a standalone GitHub project. The current version includes the core implementation, documentation, and available artifacts needed to understand the work. Future improvements can focus on stronger automation, more tests, richer visual summaries, and cleaner packaging where appropriate.

## Possible Extensions

- Add train-test evaluation metrics as a summary table.
- Compare diagonal covariance, shared covariance, and full covariance assumptions.
- Add confusion matrix visualization.
- Package the classifier into a reusable Python class.

## Tech Stack

Python, NumPy, Pandas, Matplotlib, Pillow, Jupyter Notebook.

## Author

Prahladha, IIT Hyderabad


# Benchmark Selection Decision

## Research Topic
Single-LLM Versus Multi-Agent Debate Systems
for Scientific Hypothesis Generation

## 1. LiveIdeaBench

Status: SELECTED AS PRIMARY EVALUATION FRAMEWORK REFERENCE

### VERIFIED
- Contains scientific idea generation records.
- Uses an LLM-based critic to evaluate originality,
  feasibility and clarity.
- Uses pairwise idea comparisons for fluency evaluation.
- Uses keyword-level scores and a 30th-percentile
  statistic for flexibility.
- Provides multiple critic evaluations for many ideas.

### LIMITATIONS
- Existing critic scores are not expert-validated
  scientific ground truth.
- Fluency is based on idea similarity, not language quality.
- Flexibility is a lower-tail performance statistic
  across keyword-level scores.
- Different notebooks use different overall-score formulas.
- Existing model rankings should not be reused as
  experimental results.

### DECISION
Use its generation and evaluation methodology as a reference.
Generate fresh ideas for our own experiments.

## 2. AI Idea Bench 2025

Status: SELECTED AS A SUPPLEMENTARY RESOURCE

### VERIFIED
- The test.parquet file contains 3,495 records.
- Each record contains a research context, summary
  and target paper.
- The dataset is accessible.
- The dataset repository README declares Apache-2.0.

### LIMITATIONS
- The large Idea_bench_data.zip archive is approximately
  29.6 GB and should not be downloaded unnecessarily.
- Dataset-specific licensing and permitted reuse
  should be checked separately.

### DECISION
Use as a supplementary source for understanding
research idea contexts and evaluation design.

## 3. HypoBench

Status: SELECTED AS AN OPTIONAL EVALUATION REFERENCE

### VERIFIED
- Public code and datasets are accessible.
- The repository includes real and synthetic datasets.
- Evaluation scripts include hypothesis discovery rate
  and hypothesis quality.

### LIMITATIONS
- Not every task directly measures scientific
  hypothesis generation.
- Dataset-specific suitability must be checked
  before selecting a task.

### DECISION
Use selected evaluation ideas where they fit
our research questions.

## 4. Experimental Implications

The experiment should compare:

1. Single LLM generation.
2. Multiple independent generations from the same LLM.
3. Multi-agent debate using the same underlying LLM.

Control the base model, research prompts, evidence access,
generation budget and evaluation procedure.

Evaluate these dimensions separately:

- Originality
- Feasibility
- Clarity
- Factuality
- Scientific plausibility
- Testability
- Diversity
- Computational cost

Use independent evaluation where possible.
Do not treat LLM-generated critic scores as
expert-validated ground truth.

## 5. Open Decisions

- Final dataset and prompt selection.
- Final base LLM and API availability.
- Number of agents and debate rounds.
- Independent evaluation protocol.
- Human or expert evaluation feasibility.
- Statistical analysis and reproducibility.

## 6. Evidence Status

VERIFIED: Findings directly inspected in datasets,
repository files or notebook code.

INFERRED: Proposed suitability for our experimental design.

UNKNOWN: Matters requiring further inspection or testing.

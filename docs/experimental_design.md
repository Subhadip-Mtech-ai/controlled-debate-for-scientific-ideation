# Experimental Design

## Study title
Separating Debate from Diversity: A Controlled Study of LLM-Based Scientific Ideation

## Objective
Compare single-response generation, independent multi-sample generation,
and multi-agent debate for scientific hypothesis generation.

## Experimental conditions

### Condition A: Single LLM
One model generates one hypothesis for each research task.

### Condition B: Independent sampling
The same model independently generates three hypotheses without discussion.

### Condition C: Multi-agent debate
Three agents independently generate hypotheses, critique one another,
and revise their hypotheses through two debate rounds.
Three revised hypotheses are retained.

## Pilot size
- Research tasks: 10
- Conditions: 3
- Repetitions per task per condition: 3
- Total condition-level trials: 90

## Evaluation dimensions
1. Hypothesis quality
2. Novelty
3. Factuality
4. Mechanistic plausibility
5. Testability
6. Diversity
7. Computational cost

The scoring rubric and evaluation procedure remain to be finalized.

## Fairness and reproducibility
- Use the same underlying model across conditions.
- Use the same research task bank and base prompt.
- Keep evidence access consistent.
- Record model identifier and generation parameters.
- Record input tokens, output tokens, API calls and latency.
- Preserve intermediate debate messages.
- Compare hypothesis outcomes alongside computational cost.

## Status
Provisional pilot design. Model settings, token budgets and evaluation
rubrics must be finalized before the main experiment.


# Research Decisions

This document records important decisions connecting the literature
review, benchmark inspection, and implementation analysis to the
experimental design.

Status definitions:
- VERIFIED: Supported by inspected papers, datasets, or source code.
- INFERRED: A research or implementation decision based on available evidence.
- UNKNOWN: Requires further investigation or experimental validation.

## 1. Experimental Design

| Decision | Reason | Evidence | Status |
|---|---|---|---|
| Compare three experimental conditions: Single LLM, Independent Sampling, and Multi-Agent Debate. | Separate the effect of multiple generations from the effect of debate. | Literature review and identified attribution gap. | INFERRED |
| Use the same underlying LLM across all three conditions. | Reduce model-related confounding factors. | Controlled comparison requirement identified in literature review. | INFERRED |
| Keep research tasks, evidence access, evaluation criteria, and generation budgets comparable. | Make architectural comparisons fairer. | Methodological gap identified in literature review. | INFERRED |
| Evaluate hypothesis quality using multiple independent dimensions. | A single aggregate score may hide differences between evaluation criteria. | Literature review and LiveIdeaBench inspection. | INFERRED |

## 2. Benchmark Selection

| Decision | Reason | Evidence | Status |
|---|---|---|---|
| Use LiveIdeaBench as a primary evaluation-framework reference. | It provides originality, feasibility, clarity, and additional evaluation approaches. | Dataset and evaluation notebooks inspected. | VERIFIED |
| Consider AI Idea Bench as a supplementary benchmark reference. | It provides research idea and paper-context data. | Test parquet inspected: 3,495 rows and 4 columns. | VERIFIED |
| Consider HypoBench as an additional evaluation reference. | It provides hypothesis discovery and quality evaluation resources. | Repository, datasets, and evaluation scripts inspected. | VERIFIED |
| Generate fresh hypotheses for the controlled experiments. | Existing benchmark model rankings should not be treated as results of this research. | Research design decision. | INFERRED |

## 3. Implementation Decisions

| Decision | Reason | Evidence | Status |
|---|---|---|---|
| Use MALLM as the primary multi-agent architecture reference. | Its modular debate architecture can inform agent coordination and discussion. | Repository and selected source files inspected. | VERIFIED |
| Use the AI Co-Scientist reimplementation as a scientific hypothesis generation reference. | It provides examples of generation and reflection agents. | Repository and selected source files inspected. | VERIFIED |
| Build a custom lightweight experimental pipeline. | Existing frameworks may introduce additional variables such as role specialization, retrieval, and ranking. | Literature gaps and implementation inspection. | INFERRED |
| Avoid introducing retrieval or ranking differences between experimental conditions. | These factors could affect results independently of debate. | Attribution gap identified in literature review. | INFERRED |

## 4. Evaluation Decisions

| Decision | Reason | Evidence | Status |
|---|---|---|---|
| Evaluate originality, feasibility, clarity, factuality, plausibility, and testability separately. | Different aspects of scientific hypothesis quality should remain distinguishable. | Literature review and benchmark evaluation inspection. | INFERRED |
| Measure diversity among generated hypotheses. | Multiple generations may produce similar ideas. | Research evaluation objective. | INFERRED |
| Record computational cost and token usage. | Additional agents and debate rounds may increase resource consumption. | Efficiency gap identified in literature review. | INFERRED |
| Treat automated LLM evaluations as proxies rather than ground truth. | Automated critics may produce biased or unreliable assessments. | Benchmark evaluation limitations and literature review. | INFERRED |

## 5. Open Questions

| Question | Why It Matters | Status |
|---|---|---|
| Which LLM will be selected for the final controlled experiments? | Model selection affects feasibility, cost, and reproducibility. | UNKNOWN |
| Which scientific domain and research tasks will be used? | Task selection affects the generalizability of results. | UNKNOWN |
| What generation and debate token budgets will be used? | Comparable resource allocation is necessary for fair evaluation. | UNKNOWN |
| Will expert evaluation be feasible? | Human assessment could strengthen the evaluation. | UNKNOWN |
| What statistical tests will be used to compare experimental conditions? | Statistical analysis is needed to assess observed differences. | UNKNOWN |

## 6. Next Actions

1. Finalize the base LLM and API configuration.
2. Select scientific domains and research tasks.
3. Define generation and debate budgets.
4. Implement the single-LLM baseline.
5. Validate the baseline before implementing multi-agent debate.
6. Finalize evaluation metrics and statistical tests.


## 7. Model Selection and API Configuration

| Decision | Reason | Evidence | Status |
|---|---|---|---|
| Select Gemini 3.5 Flash Lite as the provisional base model. | It completed three independent T01 generations using the same prompt and configuration. | Three successful generation records saved in results/model_validation/. | INFERRED |
| Use temperature 0.2 and maximum output tokens of 2048 for the initial model validation configuration. | These settings produced complete structured hypotheses during the initial tests. | Saved generation metadata for all three T01 runs. | VERIFIED |
| Record input and candidate token usage for every generation. | Token usage is necessary to compare computational requirements across experimental conditions. | Token usage returned by the Gemini API in all three validation runs. | VERIFIED |
| Record Gemini API limits as 15 RPM, 250000 TPM, and 500 RPD. | These limits determine the practical execution schedule. | Google AI Studio rate-limit dashboard inspected on 2026-11-13. | VERIFIED |
| Plan an initial two-day schedule of 195 expected calls per day. | The planned 390 calls fit within the displayed daily request limit when divided across two days. | Experiment configuration and observed dashboard limits. | INFERRED |
| Keep the model selection provisional until validation across the research task set and API reliability assessment are completed. | Three generations on one task do not establish general model suitability. | Current validation covers only T01. | INFERRED |

## 8. Model Validation Evidence and Limitations

- Three independent T01 generations completed successfully.
- All three outputs followed the seven-section hypothesis structure.
- Token usage was recorded for all three generations.
- Generated outputs and metadata were saved in the repository.
- Earlier model testing encountered 404 and 503 API errors.
- The retry mechanism has not yet been implemented and validated.
- Cost tracking has not yet been established.
- API quota values are based on the dashboard observation on 2026-11-13 and may change.
- Model performance across all ten research tasks remains UNKNOWN.

The three-run check is preliminary evidence, not proof of statistical
reproducibility or general scientific quality.

## 9. Updated Open Questions

| Question | Why It Matters | Status |
|---|---|---|
| Does Gemini 3.5 Flash Lite perform reliably across all ten research tasks? | T01 alone is insufficient to establish general suitability. | UNKNOWN |
| What generation and debate token budgets will be used? | Comparable resource allocation is necessary for fair evaluation. | UNKNOWN |
| What retry and recovery policy should be used for temporary API failures? | Failed requests can affect execution time and total API usage. | UNKNOWN |
| How will API costs be calculated and recorded? | Computational efficiency must include resource consumption. | UNKNOWN |
| Will expert evaluation be feasible? | Human assessment could strengthen the evaluation. | UNKNOWN |
| What statistical tests will be used to compare experimental conditions? | Statistical analysis is needed to assess observed differences. | UNKNOWN |

## 10. Updated Next Actions

1. Validate the provisional model across the research task set.
2. Finalize generation and debate token budgets.
3. Implement API error handling, retries, and execution logging.
4. Implement the single-LLM experimental baseline.
5. Validate the baseline before running the independent sampling and debate conditions.
6. Finalize evaluation metrics and statistical tests.

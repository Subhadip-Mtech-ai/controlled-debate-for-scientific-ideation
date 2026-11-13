
# Baseline Validation

## 1. Purpose

This document records baseline reproduction checks, expected outputs,
actual outputs, and deviations for the scientific hypothesis generation
experiments.

The baseline must be validated before comparing it with independent
sampling and multi-agent debate systems.

## 2. Baseline Description

**Experimental condition:** Single LLM

**Purpose:** Generate a scientific hypothesis using one LLM without
multi-agent discussion or iterative debate.

**Implementation status:** Not implemented yet.

## 3. Validation Checklist

| ID | Validation Check | Expected Output | Actual Output | Status |
|---|---|---|---|---|
| BV-01 | API connectivity | Successful response from the selected LLM | Pending | NOT TESTED |
| BV-02 | Prompt execution | Model generates a hypothesis following the specified prompt | Pending | NOT TESTED |
| BV-03 | Output format | Response follows the predefined structured format | Pending | NOT TESTED |
| BV-04 | Reproducibility | Same configuration can be executed repeatedly | Pending | NOT TESTED |
| BV-05 | Token tracking | Input and output token usage are recorded | Pending | NOT TESTED |
| BV-06 | Cost tracking | API usage and estimated cost are recorded where available | Pending | NOT TESTED |
| BV-07 | Error handling | API errors and failed generations are logged | Pending | NOT TESTED |
| BV-08 | Result storage | Generated hypotheses and metadata are saved correctly | Pending | NOT TESTED |

## 4. Experimental Metadata

The following information should be recorded for every baseline run:

- Model name and version
- API provider
- Prompt version
- Research task identifier
- Temperature and generation settings
- Maximum output tokens
- Input and output token usage
- Execution timestamp
- Generated hypothesis
- Execution status

## 5. Expected Output Structure

Each successful baseline execution should save:

1. Research task or research question.
2. Original generation prompt.
3. Generated scientific hypothesis.
4. Model configuration.
5. Token usage and execution metadata.
6. Any error or failure information.

## 6. Deviations and Issues

| Date | Issue or Deviation | Impact | Resolution |
|---|---|---|---|
| 2026-11-13 | Preliminary T01 model validation completed, but the full single-LLM baseline is not implemented. | Model suitability has initial evidence; baseline validation remains pending. | Implement and validate the experimental baseline. |

## 7. Validation Summary

- Total validation checks: 8
- Passed: 0
- Failed: 0
- Not tested: 8

**Overall status:** PENDING

## 8. Next Actions

1. Select and document the base LLM.
2. Finalize the scientific research prompt.
3. Implement the single-LLM generation baseline.
4. Execute a small test run.
5. Verify output structure, token usage, and result storage.
6. Update this document with actual results and any deviations.


## 9. Preliminary Model and API Validation

### 9.1 Selected Model Candidate

**Provider:** Google Gemini API

**Model:** gemini-3.5-flash-lite

**Selection status:** Provisional

**Research task used:** T01 - Urban surface materials and vegetation arrangements.

**Prompt version:** revised_common_generation_prompt

**Temperature:** 0.2

**Maximum output tokens:** 2048

### 9.2 Repeatability Results

Three independent generations were completed using the same model,
research task, prompt version, and generation settings.

| Run | Prompt Tokens | Candidate Tokens | Total Tokens | Finish Reason | Status |
|---|---:|---:|---:|---|---|
| 1 | 298 | 757 | 1055 | STOP | SUCCESS |
| 2 | 298 | 744 | 1042 | STOP | SUCCESS |
| 3 | 298 | 878 | 1176 | STOP | SUCCESS |

**Average total tokens:** 1091

All three generations followed the required seven-section output
structure. The generated hypotheses showed variation in wording,
mechanism, and proposed methodology.

This is an initial repeatability check on one research task. It does
not establish statistical reproducibility or general performance
across all research tasks.

### 9.3 API Rate Limits

The following limits were observed in the Google AI Studio dashboard
on 2026-11-13:

| Metric | Observed Limit |
|---|---:|
| Requests per minute (RPM) | 15 |
| Tokens per minute (TPM) | 250000 |
| Requests per day (RPD) | 500 |

The planned experiment requires 390 API calls before retries or
additional evaluation calls.

A two-day execution schedule of approximately 195 calls per day
has been proposed.

These dashboard limits may change and must be checked again before
the full experiment.

### 9.4 Model Validation Checklist

| Check | Actual Result | Status |
|---|---|---|
| API connectivity | Three successful T01 generations | PASSED |
| Prompt execution | Updated common prompt executed successfully | PASSED |
| Output format | Seven required sections present in all three runs | PASSED |
| Initial repeatability | Three successful generations with the same configuration | PASSED - PRELIMINARY |
| Token tracking | Input and candidate token usage recorded | PASSED |
| Cost tracking | Cost not yet established | NOT TESTED |
| Error handling | 404 and 503 errors observed during earlier model tests; retry handling not implemented | PARTIALLY TESTED |
| Result storage | Generated outputs and metadata saved in Drive and repository | PASSED |

### 9.5 Remaining Validation Work

1. Implement the single-LLM experimental generation pipeline.
2. Test the baseline on the selected research task set.
3. Verify token and latency logging for every API call.
4. Implement and test retry handling for temporary API failures.
5. Establish how API cost will be recorded, where pricing information is available.
6. Recheck API quota before full experimental execution.
7. Validate output quality and structure across multiple research tasks.

**Preliminary model validation status:** COMPLETED

**Full single-LLM baseline status:** NOT IMPLEMENTED

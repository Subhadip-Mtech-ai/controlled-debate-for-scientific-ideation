# GitHub Implementation Review

## 1. MALLM
Repository: https://github.com/Multi-Agent-LLMs/mallm
License: Apache-2.0

### Verified from inspected source excerpts
- Coordinator initializes and manages multiple agents.
- Agents can have different personas.
- DiscussionDebate manages debate rounds.
- Panelists can improve drafts or provide feedback.
- Decision protocols and discussion paradigms are configurable.
- Agents use a shared LLM interface.

### Assessment
Useful architectural reference for multi-agent debate.
Dynamic personas and configurable protocols must be controlled
if adapted for a fair experimental comparison.

## 2. AI Co-Scientist
Repository: https://github.com/Ahmad-Jaradat-Space/Co-Scientist
License: Apache-2.0

### Verified from inspected source excerpts
- GenerationAgent proposes hypotheses.
- ReflectionAgent reviews hypotheses.
- Generation uses literature-search tools.
- Reflection searches for supporting and contradicting evidence.
- Termination considers budget, time and leaderboard stability.
- The inspected generation implementation supports the literature
  strategy; other strategies are marked as not implemented.

### Assessment
Useful reference for scientific hypothesis generation and evaluation.
Not suitable for direct adoption in the controlled debate comparison
without removing or controlling additional components.

## 3. Oathe Research
Repository: https://github.com/oathe-ai/oathe-research
License: Not identified in the inspected repository metadata.

### Assessment
Useful conceptual reference for literature ingestion, debate,
hypothesis evolution and synthesis. Not selected for implementation.

## 4. Implementation Decision

Decision: Build a custom lightweight experimental pipeline.

MALLM will serve as the primary architectural reference.
AI Co-Scientist will serve as a reference for hypothesis generation
and evaluation.

## 5. Experimental Conditions

1. Single LLM generation.
2. Multiple independent generations using the same LLM.
3. Multi-agent debate using the same underlying LLM.

## 6. Experimental Controls

- Same underlying LLM.
- Same research tasks and initial instructions.
- Same evidence access.
- Comparable token and generation budgets.
- Same evaluation criteria and evaluator.

## 7. Evidence Status

VERIFIED: Findings explicitly visible in the inspected source excerpts.

INFERRED: Suitability of each repository for the proposed experiment.

UNKNOWN: Full implementation compatibility, runtime cost and
reproducibility. These require further testing.

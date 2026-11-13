# Three-Agent Interaction Workflow

## 1. Objective

Define the interaction process for the multi-agent debate condition
in the study:

Separating Debate from Diversity: A Controlled Study of LLM-Based
Scientific Ideation.

## 2. Agent configuration

- Agents: A1, A2 and A3
- Underlying model: Same Gemini model for all agents
- Research task: Identical for all agents
- Initial generation: Independent
- External evidence retrieval: Disabled
- Critique rounds: 1
- Revision rounds: 1

## 3. Stage 1: Independent hypothesis generation

Each agent independently receives the common generation prompt
and the same research task.

Outputs:
- A1 produces H1.
- A2 produces H2.
- A3 produces H3.

All three initial hypotheses are preserved.

## 4. Stage 2: Peer critique

Each agent evaluates the other two hypotheses.

| Reviewer | Hypotheses reviewed |
|---|---|
| A1 | H2 and H3 |
| A2 | H1 and H3 |
| A3 | H1 and H2 |

Each reviewer uses the standardized peer-critique prompt.

The critique must assess scientific plausibility, clarity,
mechanism, variables, experimental feasibility, measurable outcomes,
limitations and unsupported assumptions.

### Critique accounting

- Directed peer evaluations: 6
- Critique API calls: 3, assuming one call per reviewer
- Each reviewer evaluates two hypotheses in one response.

All critiques are preserved separately and assigned to the
correct original hypothesis.

## 5. Stage 3: Individual hypothesis revision

Each agent receives only the two critiques concerning its own
original hypothesis.

| Agent | Original hypothesis | Feedback received | Final output |
|---|---|---|---|
| A1 | H1 | Critiques from A2 and A3 | H1 revised |
| A2 | H2 | Critiques from A1 and A3 | H2 revised |
| A3 | H3 | Critiques from A1 and A2 | H3 revised |

Each agent uses the standardized revision prompt.

Agents must explain which suggestions they accepted or rejected
and provide exactly one revised hypothesis.

## 6. Final outputs

The debate condition retains:
- Three initial hypotheses
- Three peer-critique responses
- Three revised hypotheses

No automatic merging, ranking or winner selection is performed.

## 7. Experimental controls

- Use the same underlying model for all agents.
- Use the same research task and common generation prompt.
- Keep evidence access consistent across conditions.
- Do not introduce external retrieval.
- Keep feedback private to its intended agent.
- Preserve all intermediate outputs.
- Record model identifier and generation parameters.
- Record API calls, input tokens, output tokens and latency.
- Do not treat agent agreement as proof of scientific correctness.

## 8. Computational accounting per debate trial

Expected calls:
- Initial generation: 3
- Peer critique: 3
- Individual revision: 3
- Total: 9 API calls

Expected directed peer evaluations: 6.

Actual calls, retries, failures and token usage must be recorded
from execution logs rather than assumed from this estimate.

## 9. Status

Approved provisional workflow.

The workflow is documented and ready for implementation review.
Generation parameters, token budgets and model identity must still
be finalized before the main experiment.

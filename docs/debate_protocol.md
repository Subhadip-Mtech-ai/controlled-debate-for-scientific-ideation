# Multi-Agent Debate Protocol

## 1. Objective
Evaluate whether interaction, peer critique and revision improve
scientific hypothesis generation beyond independent sampling.

## 2. Agent configuration
- Number of agents: 3
- Underlying model: Same model for all agents
- Initial generation: Independent
- Debate rounds: 2
- Final candidates: 3 revised hypotheses

All agents use the same base hypothesis-generation instructions.
No external evidence retrieval is introduced.

## 3. Initial generation
Each agent independently generates one hypothesis for the research task.
Each hypothesis includes a research question, hypothesis, mechanism,
variables, methodology, expected outcome, limitations and assumptions.

## 4. Debate round 1: Peer critique
Each agent reviews the other two hypotheses and identifies:
- Scientific weaknesses
- Unsupported assumptions
- Weaknesses in the proposed mechanism
- Experimental feasibility concerns
- Problems with measurable outcomes
- Potential improvements

Critiques must be specific and constructive.

## 5. Debate round 2: Revision
Each agent receives critiques of its own hypothesis and revises it.
Each agent explains which suggestions were accepted or rejected and why.

## 6. Final output
Preserve all three revised hypotheses separately.
Do not automatically merge, rank or select a single winner.

## 7. Fairness and controls
- Use the same underlying model.
- Use the same research task and base instructions.
- Keep evidence access consistent.
- Do not introduce external retrieval.
- Preserve initial hypotheses, critiques and revisions.
- Record input tokens, output tokens, API calls and latency.
- Do not treat agreement as proof of scientific correctness.

## 8. Methodological note
Debate requires additional model interactions. Report computational
cost separately and interpret quality improvements alongside cost.

## 9. Status
Approved provisional protocol. Exact prompts, token limits and
generation settings remain to be finalized.

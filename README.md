# Separating Debate from Diversity: A Controlled Study of LLM-Based Scientific Ideation

## Research Overview

## 1. Overview

Large Language Models (LLMs) are increasingly being explored for scientific research and hypothesis generation. While a single LLM can generate research ideas, multi-agent systems introduce multiple agents that can generate, critique, discuss, and refine hypotheses.

This research investigates whether multi-agent debate systems provide meaningful improvements over single-LLM approaches in scientific hypothesis generation.

## 2. Research Objectives

- Compare single-LLM and multi-agent debate approaches.
- Evaluate the quality and originality of generated hypotheses.
- Investigate factuality, feasibility, scientific plausibility, and testability.
- Measure diversity among generated hypotheses.
- Analyze computational cost and the effect of additional debate rounds.
- Identify the actual contribution of debate under controlled conditions.

## 3. Experimental Conditions

1. **Single LLM:** One model generates a scientific hypothesis.
2. **Independent Sampling:** The same model independently generates multiple hypotheses without discussion.
3. **Multi-Agent Debate:** Multiple agents using the same underlying model generate, critique, and refine hypotheses through structured discussion.

The experimental design aims to control the underlying model, research tasks, evidence access, generation budget, and evaluation criteria wherever possible.

## 4. Evaluation Criteria

- Originality
- Scientific plausibility
- Feasibility
- Clarity
- Factuality
- Testability
- Hypothesis diversity
- Computational cost

Automated evaluation will be treated as an evaluation proxy rather than ground truth. Expert assessment may be considered where feasible.

## 5. Repository Structure

```text
Scientific_Hypothesis_Generation/
|
|-- README.md
|-- requirements.txt
|-- configs/
|-- data/
|   |-- README.md
|-- notebooks/
|-- src/
|-- scripts/
|-- results/
|-- paper/
|-- research_decisions.md
|-- baseline_validation.md
|-- ai_assistance_log.md
|-- LICENSE
```

## 6. Benchmarks and References

- AI Idea Bench: https://ai-idea-bench.github.io/
- HypoBench: https://github.com/ChicagoHAI/HypoBench-code
- LiveIdeaBench: https://liveideabench.com/
- MALLM: https://github.com/Multi-Agent-LLMs/mallm
- AI Co-Scientist: https://github.com/Ahmad-Jaradat-Space/Co-Scientist

These resources are references for benchmark design and implementation.

## 7. Tools and Technologies

- Python
- Google Colab
- OpenAI-compatible LLM APIs
- Hugging Face
- PyTorch
- Scikit-learn
- Sentence Transformers
- Pandas and NumPy
- Matplotlib and Seaborn

## 8. Current Status

Research planning, literature review, benchmark inspection, and implementation reference analysis have been completed. The controlled experimental pipeline and evaluation are planned as the next stages.

## 9. License

This repository uses the MIT License. See the LICENSE file for details.

Third-party datasets, research papers, and external code remain subject to their respective licenses and usage conditions.

# Bayesian Active Learning for Intent Disambiguation in Interactive Robot Planning

**Huao Li<sup>1</sup>, Carson Sobolewski<sup>1</sup>, Augustinos Saravanos<sup>1</sup>, William Tan<sup>2</sup>, John Karigiannis<sup>2</sup>, Chuchu Fan<sup>1</sup>**
<sup>1</sup>Massachusetts Institute of Technology &nbsp; <sup>2</sup>GE Vernova

*CoRL 2026* · *Human-Robot Dialogue Workshop, IROS 2026*

[Project page](https://www.huao-li.com/bal/) · [arXiv](https://arxiv.org/abs/2609.34270) · Code (coming soon)

![BAL framework overview](static/images/new_pipeline.png)

## Overview

Natural-language instructions to robots are often ambiguous, incomplete, or underspecified. Large language models (LLMs) are a natural interface for asking clarification questions, but relying on the LLM alone to drive a multi-turn conversation can cause systematic failures: context loss, overconfidence, and sycophancy.

**BAL** treats clarification as a **Bayesian active learning problem over grounded Signal Temporal Logic (STL) task specifications**:

- An **LLM** proposes candidate STL specifications with prior utility estimates, and turns informative contrasts into natural-language clarification questions.
- A **grammar VAE** embeds STL formulas into a continuous latent space in which every point decodes to a valid formula.
- A **Gaussian process** over that space tracks uncertainty about the user's intent, and an **information-gain acquisition** chooses which question to ask. The question can be about specifications the LLM never proposed.
- After clarification, the inferred specification goes to a **formal planner**, which synthesizes a verifiable robot trajectory.

## Key results

- **BAL asks more informative questions.** Across both simulation domains and six base LLMs, BAL consistently outperforms LLM clarification baselines in success rate and generally needs fewer clarification rounds.
- **BAL makes LLMs less overconfident.** When the agent decides for itself when to stop, the LLM baselines often stop too early and lose substantial success. BAL keeps a similar level of performance, because its posterior uncertainty tells it when clarification is still needed.
- **BAL helps smaller models.** Most of the reasoning burden moves to the probabilistic model and formal planner. With BAL, a smaller model can match or outperform direct clarification with a larger model, at lower wall-clock cost.

## Citation

```bibtex
@inproceedings{li2026bal,
  title     = {Bayesian Active Learning for Intent Disambiguation in Interactive Robot Planning},
  author    = {Li, Huao and Sobolewski, Carson and Saravanos, Augustinos and Tan, William and Karigiannis, John and Fan, Chuchu},
  booktitle = {Conference on Robot Learning (CoRL)},
  year      = {2026}
}
```

## Acknowledgment

This work is supported by the MIT x GE Vernova Energy and Climate Alliance.

The project page is built from the [Academic Project Page Template](https://github.com/eliahuhorwitz/Academic-project-page-template), which adapts the [Nerfies](https://nerfies.github.io) page, and is licensed under [CC BY-SA 4.0](http://creativecommons.org/licenses/by-sa/4.0/).

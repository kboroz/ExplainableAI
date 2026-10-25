# 2026 Project Proposals

Recent papers (2026+) that can be used as project proposals for this course. Pick **one** paper. Each project should have one prediction task, one model, one or two XAI methods already covered in the labs (LIME, SHAP, DiCE, Integrated Gradients, Grad-CAM, attention), one quantitative check, and a short limitations discussion.

## Tracks

| Track | Goal | Papers |
|---|---|---|
| **Implement & compare** | Adapt the method to a course-scale dataset, compare to a lab baseline | 3, 4, 5, 6, 7, 9, 16 |
| **Evaluate a claim** | Reproduce one experiment or metric, show where course methods agree or fail | 1, 2, 8, 10, 11, 12, 13, 19 |
| **Critique & map** | No new method; map techniques to a fairness or legal requirement, document the gap | 12, 14, 15, 17, 18, 20 |

---

## Week 3: Local explanations (LIME / SHAP)

| # | Paper | Project idea | Links |
|---|---|---|---|
| 1 | **Improving Causal Explanations** (Lee, Plečko, Bareinboim; NeurIPS 2026) | On a small synthetic SCM plus one lab tabular dataset, find one case where KernelSHAP/TreeSHAP attributions violate a causal desideratum. Don't re-prove the theorem. | [Poster](https://neurips.cc/virtual/2026/poster/153775) · [Technical report](https://causalai.net/r135.pdf) |
| 2 | **PE-SHAP: Causally Interpretable Path-Wise Shapley Explanations** (Buleshnyi, Loftus, Hansen; NeurIPS 2026) | Reproduce a small German Credit or COMPAS case; contrast standard SHAP dependence plots with a path-wise reading. Treat the causal graph as an assumption. | [Poster](https://neurips.cc/virtual/2026/poster/155303) |
| 3 | **Causal Integrated Gradients** (Michiels et al.; arXiv, Oct 2026) | Implement CIG on a low-dim tabular model with a partial graph; compare to Captum IG and DeepSHAP on cost and agreement with a known intervention. | [arXiv](https://arxiv.org/abs/2610.22126) |
| 4 | **Rule of Thumb: Explaining AI Systems using Partial Information** (Rawal et al.; arXiv, Aug 2026) | Benchmark RoT vs LIME and KernelSHAP on one classifier (runtime, stability, fidelity); note what changes under query-only access. | [arXiv](https://arxiv.org/abs/2608.10766) |

## Week 4: Counterfactuals

| # | Paper | Project idea | Links |
|---|---|---|---|
| 5 | **Comparables XAI** (Zhang et al.; CHI 2026) | Implement trace adjustment and compare with DiCE using proxies: sparsity, plausibility, validity. | [arXiv](https://arxiv.org/abs/2602.13784) · [DOI](https://doi.org/10.1145/3772318.3791041) |

## Week 6: Vision

| # | Paper | Project idea | Links |
|---|---|---|---|
| 6 | **DictXAI: Model-Independent Concept Dictionaries** (arXiv, Oct 2026) | Build a small concept dictionary for one image or 1D-signal task; compare to Grad-CAM/IG and present three disagreement cases. | [arXiv](https://arxiv.org/abs/2610.10301) |
| 7 | **Hide and Seek (HnS)** (Tokas et al.; arXiv, Oct 2026) | Run HnS on the Week 6 CNN for 2-3 concepts; compare masked-region effect with Grad-CAM (agreement ≠ ground truth). | [arXiv](https://arxiv.org/abs/2610.13935) |
| 8 | **Bridging Human and Model Attention** (Stefani et al.; arXiv, Oct 2026) | On a public gaze dataset, rank Grad-CAM vs IG by human alignment (JS, chi-square, Pearson). Alignment ≠ faithfulness. | [arXiv](https://arxiv.org/abs/2610.12703) |

## Week 7: Text and attention

| # | Paper | Project idea | Links |
|---|---|---|---|
| 9 | **A Two-Stage LLM Framework for Accessible and Verified XAI Explanations** (IEEE WCCI 2026) | Wrap SHAP/LIME outputs with an open explainer LLM plus a verifier; measure how often narratives cite features the attribution didn't rank highly. | [arXiv](https://arxiv.org/abs/2604.12543) |
| 10 | **Competition for Attention Predicts Good-to-Bad Tipping in AI** (arXiv, Feb 2026) | On a small transformer/text classifier, track attention-based attributions vs SHAP/LIME as inputs shift; test whether attention competition signals precede a flip in predictions. Attention ≠ explanation. | [arXiv](https://arxiv.org/abs/2602.14370) |
| 11 | **Evaluating the Causal Faithfulness of SHAP for SAE Features** (Xie, Al-Moubayed; arXiv, Oct 2026) | Re-run a reduced slice of the released code, or a smaller probe: attribution rank vs actual intervention. Test whether inter-method agreement implies causal faithfulness. | [arXiv](https://arxiv.org/abs/2610.17898) · [Code](https://github.com/froge79/shap-sae) |

## Week 8: Evaluation, fairness, responsible AI

| # | Paper | Project idea | Links |
|---|---|---|---|
| 12 | **Faithfulness Without Anchors** (IJCAI-ECAI 2026 XAI Workshop, position paper) | Apply two faithfulness checks to existing SHAP/LIME outputs; explain why they disagree. Deliver a metric critique. | [arXiv](https://arxiv.org/abs/2610.12493) |
| 13 | **Integrating Feature Understandability into Feature Selection** (arXiv, Oct 2026) | Collect understandability ratings for a course dataset; compare accuracy and SHAP summaries before/after selection. | [arXiv](https://arxiv.org/abs/2610.16627) |
| 14 | **Fairness of Explanations in AI** (Popoola, Sheppard; arXiv, May 2026) | Audit SHAP/LIME on Adult, COMPAS, or German Credit: compare explanation distributions across a protected attribute at fixed predictions. Report a failure mode, not a certification. | [arXiv](https://arxiv.org/abs/2605.09852) |
| 15 | **Explainable AI for the EU Right to Explanation** (Fresz, Dubovitskaya, Huber; arXiv, Aug 2026) | For one high-stakes use case, map LIME, SHAP, counterfactuals, Grad-CAM to GDPR Art. 15(1)(h) / AI Act Art. 86. Deliver a gap table, not a compliance claim. | [arXiv](https://arxiv.org/abs/2608.02699) |
| 17 | **Addressing the Selection Problem in Explainable AI** (Vlases and Morrison; IJCAI 2026 XAI Workshop; arXiv, Aug 2026) | Map example user questions to course methods such as LIME, SHAP, or DiCE. Identify cases where the question-to-method mapping is ambiguous; treat the paper’s proposed orchestration system as a proposal, not a validated solution. | [arXiv](https://arxiv.org/abs/2608.22356) |
| 19 | **Faithfulness Without Anchors** (IJCAI-ECAI 2026 XAI Workshop, position paper) | Apply two faithfulness checks to the same SHAP or LIME outputs; explain why their conclusions differ. Deliver a metric critique. | [arXiv](https://arxiv.org/abs/2610.12493) |

## Extension: Temporal and multimodal

| # | Paper | Project idea | Links |
|---|---|---|---|
| 16 | **T-MoXAI** (Inha et al.; arXiv, Sep 2026) | Implement the three-level template (when / which modality / what) on a small time series or two-modality toy set; compare static vs temporal SHAP; report one ROAR-style deletion curve. | [arXiv](https://arxiv.org/abs/2609.33685) |
| 18 | **From Saliency Maps to Circuits: An Integrative Survey of Explainable AI and Mechanistic Interpretability** (Dugăeșescu and Florea; review, Oct 2026) | Compare one course explanation method with one mechanistic-interpretability approach discussed in the review. Create a short concept map of their goals, evidence, and limitations; no new method is required. | [Article](https://www.mdpi.com/2504-4990/8/10/315) |

---

## Extension: Critique and background reading

| # | Paper | Project idea | Links |
|---|---|---|---|
| 20 | **Explaining explainability: A comprehensive survey on explainable artificial intelligence and relevant industry applications** (Wilkinson, Yawney, and Gadsden; *Intelligent Systems with Applications*, 2026) | Use the survey to map XAI methods to one application domain. Compare its discussion of evaluation challenges with one course baseline and identify a gap; this is a review-based critique, not a method implementation. | [Article](https://doi.org/10.1016/j.iswa.2026.200647) |

## Scope for every project

1. State the explanation question in one sentence (local, global, counterfactual, vision, text, or evaluation).
2. Name the baseline from this course.
3. Report one quantitative check (fidelity, robustness, agreement with a known effect, or a small preference study).
4. State what the method cannot claim (causality, legal compliance, human understanding).

---

## Assignment line

> Choose one paper. In a one-page proposal, name the course baseline, dataset, the single claim you will test, and the metric. Implementation projects must run. Critique projects must include a filled gap table or metric disagreement, not only a summary.

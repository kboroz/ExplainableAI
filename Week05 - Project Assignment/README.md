# 2026 Project Proposals

Recent papers (2026) that can be used as student project proposals for this course.
Each proposal should stay inside the Week 5 brief: one prediction task, one model,
one or two XAI methods already covered in the labs (LIME, SHAP, DiCE, Integrated
Gradients, Grad-CAM, attention), one evaluation, and a short limitations discussion.

The paper already listed in this folder remains in scope:

- **Competition for attention predicts good-to-bad tipping in AI**
  https://arxiv.org/abs/2602.14370

---

## How to use this list

| Track | What a good project looks like | Papers |
| --- | --- | --- |
| Implement and compare | Re-implement or adapt the method on a course-scale dataset and compare it to a lab baseline | 3, 4, 5, 6, 7, 9, 15 |
| Evaluate a claim | Reproduce one experiment or metric and say where the course methods agree or fail | 1, 2, 8, 10, 11, 12 |
| Critique and map | No new method. Map course techniques onto a fairness or legal requirement and document the gap | 11, 13, 14 |

Suggested scope for every project:

1. State the explanation question in one sentence (local, global, counterfactual, vision, text, or evaluation).
2. Name the baseline from this course.
3. Report one quantitative check (fidelity, robustness, agreement with a known effect, or a small preference study).
4. State what the method cannot claim (causality, legal compliance, human understanding).

---

## Week 3 — Local explanations: LIME and SHAP

### 1. Improving Causal Explanations

Kai-Zhan Lee, Drago Plečko, Elias Bareinboim. NeurIPS 2026.

- Poster: https://neurips.cc/virtual/2026/poster/153775
- Technical report: https://causalai.net/r135.pdf

Formalizes four desiderata for numerical credit assignment. Shows that SHAP and LIME do not satisfy all of them without causal assumptions (Explanatory Impossibility Theorem) and introduces counterfactual Shapley values, with a bounding algorithm.

**Project.** On a small synthetic SCM and one tabular dataset from the labs, compare KernelSHAP or TreeSHAP with the paper’s desiderata. Do not try to re-prove the theorem. Show one case where the two attributions disagree and say which desideratum is violated.

**Fits.** Week 3 (SHAP axioms), Week 8 (what an explanation is allowed to claim).

### 2. PE-SHAP: Causally Interpretable Path-Wise Shapley Explanations

Maksym Buleshnyi, Joshua Loftus, Sakina Hansen. NeurIPS 2026.

- Poster: https://neurips.cc/virtual/2026/poster/155303

Path-wise decomposition of Shapley-style attributions that is designed to match mediation estimands (natural indirect effect, path-specific effects). Demonstrated on synthetic SCMs and on German Credit and COMPAS.

**Project.** Reproduce the German Credit or COMPAS case at a smaller scale. Contrast ordinary SHAP dependence plots with a path-wise reading of the same prediction. Treat the causal graph as an assumption, not as something SHAP discovers.

**Fits.** Week 3 (SHAP), Week 8 (fairness case studies).

### 3. Causal Integrated Gradients

Joran Michiels, Anis Ismail, Maarten De Vos, Alejandro Sifrim. arXiv, 15 Oct 2026.

- https://arxiv.org/abs/2610.22126

Routes the Integrated Gradients path along a known causal graph and splits each attribution into a direct effect and effects mediated by descendants. On a synthetic benchmark it matches causal Shapley accuracy at lower cost; also tested on simulated gene regulation and interferon-β stimulation data.

**Project.** Implement CIG on a low-dimensional tabular model where a partial graph is given. Compare with Captum Integrated Gradients and DeepSHAP. Report cost and agreement with a known intervention, not only visual similarity of plots.

**Fits.** Week 3 (SHAP), Week 6 (Integrated Gradients).

### 4. Rule of Thumb: Explaining AI Systems using Partial Information

Kaivalya Rawal, Daria Onitiu, Brent Mittelstadt, Sandra Wachter, Chris Russell. arXiv, Aug 2026.

- https://arxiv.org/abs/2608.10766

Local, model-agnostic explanations based on how predictive a feature value is of the model output, rather than on how the output changes when the feature is perturbed. Aimed at API-only models and at regulatory settings where full model access is unavailable.

**Project.** Benchmark RoT against LIME and KernelSHAP on one tabular classifier: runtime, stability under resampling, and fidelity. Add a short note on what changes when the model can only be queried.

**Fits.** Week 3 (local surrogates), Week 1 and Week 8 (regulation, limited access).

---

## Week 4 — Counterfactuals

### 5. Comparables XAI

Yifan Zhang, Tianle Ren, Fei Wang, Brian Y. Lim. CHI 2026.

- https://arxiv.org/abs/2602.13784
- https://doi.org/10.1145/3772318.3791041

Example-based explanations inspired by real-estate comparables. Each example is adjusted one attribute at a time, monotonically, along the model’s feature space. User studies reported higher faithfulness, precision, and user accuracy than unadjusted or linearly adjusted baselines.

**Project.** Implement trace adjustment for a regression or binary classifier and compare it with DiCE. If a user study is not feasible, report a proxy: sparsity, plausibility (distance to the data manifold), and validity (the adjusted example actually flips or matches the target score).

**Fits.** Week 4 (DiCE, actionable changes, plausibility).

---

## Week 6 — Vision

### 6. DictXAI: Model-Independent Concept Dictionaries

arXiv, 7 Oct 2026.

- https://arxiv.org/abs/2610.10301

Defines concepts in the input domain with a dictionary (learned bases, analytic waveforms, or measured elements), encodes the input as a sparse code, and attributes the prediction to dictionary elements. Architecture-agnostic. Demonstrated on Clever Hans detection and biomedical signals.

**Project.** Build a small dictionary for one image or 1D-signal task and compare dictionary attributions with Grad-CAM or Integrated Gradients on the same examples. The deliverable is the dictionary plus three cases where the two explanations disagree.

**Fits.** Week 6 (Grad-CAM, Integrated Gradients, Clever Hans).

### 7. Hide and Seek (HnS)

Bhanu Tokas, Rahul Nair, Rockwell Jackson, Hannah Kerner. arXiv, Oct 2026.

- https://arxiv.org/abs/2610.13935

Concept attribution without model weights or concept labels. A vision-language model retrieves and localizes a concept; the region is masked; attribution is the change in the black-box output. Validated on CelebA and COCO-Stuff; also shown for captioning and satellite segmentation.

**Project.** Run HnS on a CNN used in the Week 6 notebook for two or three named concepts. Compare the masked-region effect with a Grad-CAM map of the same image. State clearly that agreement with Grad-CAM is not ground truth.

**Fits.** Week 6 (local vision explanations, black-box access).

### 8. Bridging Human and Model Attention

Marco Stefani, Edoardo Parpaiola, Matteo Bino, and colleagues. arXiv, 8 Oct 2026.

- https://arxiv.org/abs/2610.12703

Quantifies alignment between attribution maps and eye-tracking heatmaps for CNNs, ViTs, and Vision Mamba, using Jensen–Shannon similarity, chi-square similarity, and Pearson correlation rather than only qualitative inspection.

**Project.** On one public gaze dataset, rank two methods from Week 6 (for example Grad-CAM and Integrated Gradients) by human alignment. Report all three metrics. Do not treat higher human alignment as higher faithfulness.

**Fits.** Week 6 (saliency, Grad-CAM, ViT attention), Week 8 (comprehensibility vs fidelity).

---

## Week 7 — Text and attention

### 9. A Two-Stage LLM Framework for Accessible and Verified XAI Explanations

Accepted at IEEE WCCI 2026. arXiv, 14 Apr 2026.

- https://arxiv.org/abs/2604.12543

An explainer LLM turns raw XAI outputs into natural-language narratives. A verifier LLM scores faithfulness, coherence, completeness, and hallucination risk, and feeds corrections back. Tested across five XAI techniques with open-weight LLMs.

**Project.** Wrap SHAP or LIME outputs from a Week 3 or Week 7 notebook with an open explainer and a verifier. Measure how often the narrative mentions a feature the attribution did not rank highly. Prefer a small open model over a closed API.

**Fits.** Week 7 (communicating text attributions), Week 8 (hallucination, faithfulness).

### 10. Evaluating the Causal Faithfulness of SHAP for SAE Features

Samuel Xie, Noura Al-Moubayed. arXiv, 13 Oct 2026.

- https://arxiv.org/abs/2610.17898
- Code: https://github.com/froge79/shap-sae

Applies SHAP to sparse-autoencoder latents in GPT-2 Small and tests them against ablation and activation steering on SST-2. Methods that agree with each other still agree poorly with measured causal effects. Attribution recovers inserted sentiment signal better than deletions.

**Project.** Either re-run a reduced slice of the released code, or repeat the logic on a smaller probe: attribution rank versus an actual intervention (feature drop or steering). The claim to test is that inter-method agreement is not causal faithfulness.

**Fits.** Week 3 (SHAP), Week 7 (text), Week 8 (fidelity).

---

## Week 8 — Evaluation, fairness, and responsible AI

### 11. Faithfulness Without Anchors

Position paper. Presented at the IJCAI-ECAI 2026 Workshop on Explainable AI.

- https://arxiv.org/abs/2610.12493

Catalogues five structural shortcomings of current faithfulness metrics for feature importance and proposes four research avenues. Useful as a framing paper, not as a method to implement in full.

**Project.** Take SHAP and LIME outputs already produced in the labs and apply two faithfulness checks. Use the paper to explain why the two checks can disagree. Deliver a short metric critique, not a new explainer.

**Fits.** Week 8 (fidelity, robustness, pitfalls).

### 12. Integrating Feature Understandability into Feature Selection

arXiv, 12 Oct 2026.

- https://arxiv.org/abs/2610.16627

Puts a user-rated Feature Understandability Scale into feature selection so that explanations cite features that are both informative and comprehensible. A small study found preference gains at limited accuracy cost.

**Project.** Collect understandability ratings for one course dataset (even a small cohort is enough if the limitation is stated). Retrain, then compare accuracy and the SHAP summary before and after selection.

**Fits.** Week 2 (feature selection and global effects), Week 8 (comprehensibility).

### 13. Fairness of Explanations in AI

Gideon Popoola, John Sheppard. arXiv, 11 May 2026.

- https://arxiv.org/abs/2605.09852

Separates fairness of the explanation process from fairness of the model outcome. A model can pass standard outcome criteria and still explain different people differently. Offers a conditional-invariance framing and a practitioner checklist.

**Project.** Audit SHAP or LIME on Adult, COMPAS, or German Credit. Hold the prediction fixed as far as possible and compare explanation distributions across a protected attribute. Report a failure mode; do not claim the audit certifies fairness.

**Fits.** Week 8 (bias detection via attributions).

### 14. Explainable AI for the EU Right to Explanation

Benjamin Fresz, Elena Dubovitskaya, Marco F. Huber. arXiv, 3 Aug 2026.

- https://arxiv.org/abs/2608.02699

Systematic review of how technical XAI maps onto GDPR Art. 15(1)(h) and AI Act Art. 86. From a broad search, only a small subset of papers integrate legal and technical arguments. Documents recurring mistakes, including misidentifying the GDPR legal basis.

**Project.** Map LIME, SHAP, counterfactuals, and Grad-CAM onto the properties discussed in the review for one high-stakes use case (credit, hiring, or a medical classifier). The deliverable is a gap table, not a compliance claim.

**Fits.** Week 1 (GDPR, EU AI Act), Week 8 (responsible AI).

---

## Extension — temporal and multimodal

### 15. T-MoXAI

Ali Inha, Mo Vali, Saaliha Vali, Pietro Liò, Meen-Yau Thum. arXiv, 27 Sep 2026.

- https://arxiv.org/abs/2609.33685

Three explanation levels for temporal multimodal models: when (temporal Shapley), which modality (attention), and what (gradient attribution). Evaluated on IVF outcome prediction and wheat-yield forecasting. Temporal modelling mattered in both domains; temporal ROAR was used as a faithfulness check.

**Project.** Do not rebuild the full clinical or agricultural system. Implement the three-level template on a small public time series or a two-modality toy dataset, and compare static SHAP with a temporal aggregation. Report one ROAR-style deletion curve.

**Fits.** Week 3 (SHAP), Week 6 (gradients), Week 7 (attention), Week 8 (ROAR / fidelity).

---

## Suggested assignment line

> Choose one paper from `2026_project_proposals.md`. In the proposal (max one page), name the course baseline you will compare against, the dataset, the single claim you will test, and the metric. Implementation projects must run. Critique projects must include a filled gap table or metric disagreement, not only a summary.

# Explainable AI (XAI) 🔍🤖

A comprehensive, hands-on course reference and lab environment for **Explainable Artificial Intelligence (XAI)**, **Machine Learning Model Interpretability**, and **Responsible AI**.

---

## 📋 Prerequisites

To successfully participate in the course and work through the notebooks, the following background knowledge is required:

* **Mathematics:** Basic knowledge of **Statistics, Probability Theory**, and **Linear Algebra** (vectors, matrices, partial derivatives).
* **Programming:** Proficiency in **Python** (NumPy, Pandas, Matplotlib, Seaborn) and experience with **Jupyter Notebooks**.
* **Machine Learning:** Solid understanding of classical ML (Scikit-Learn) and a basic grasp of **Deep Learning** (PyTorch or TensorFlow/Keras).

---

## 1. 📖 Course Overview

This course provides a systematic, practical introduction to the explainability and interpretability of complex machine learning and deep learning models. It addresses the "black box" model problem and equips students with mathematical and applied methods to make model decisions transparent, understandable, and auditable.

The accompanying GitHub repository serves as a central reference and workshop environment. Through interactive Jupyter Notebooks, participants explore theoretical concepts directly in Python and apply established XAI libraries (such as **SHAP**, **LIME**, and **Captum**) to tabular, image, and text datasets.

---

## 2. 📚 Detailed Course Syllabus

### 🔹 Module 1: Fundamentals & Intrinsic Interpretability (Intrinsic XAI)
**Objective:** Build a foundational understanding of transparency, fairness, and trustworthy AI while utilizing inherently interpretable models.

* **Introduction & Motivation:**
  * The "Accuracy vs. Interpretability" tradeoff.
  * Legal & ethical aspects (GDPR "Right to Explanation", EU AI Act).
  * Taxonomy of XAI methods: *Model-Agnostic vs. Model-Specific*, *Local vs. Global*.
* **Interpretable ML Models (Intrinsic Models):**
  * Linear & Logistic Regression: Interpreting coefficients and odds ratios.
  * Decision Trees: Decision rules and feature importance.
  * Generalized Additive Models (GAMs) & Explainable Boosting Machines (EBMs).

---

### 🔹 Module 2: Model-Agnostic Post-Hoc XAI Methods
**Objective:** Analyze complex black-box models independently of their architecture at both global and local levels.

#### 2.1 Global Interpretability
* **Permutation Feature Importance (PFI):** Measuring performance degradation upon feature permutation.
* **Partial Dependence Plots (PDP) & Individual Conditional Expectation (ICE):** Visualizing feature effects and interactions.
* **Accumulated Local Effects (ALE):** Correcting feature effect estimations under correlated input features.

#### 2.2 Local Interpretability
* **LIME (Local Interpretable Model-Agnostic Explanations):** Local linear approximations of black-box decisions.
* **Shapley Values & SHAP (SHapley Additive exPlanations):**
  * Game-theoretic foundations (Shapley values, efficiency, symmetry axioms).
  * TreeSHAP, KernelSHAP, and DeepSHAP.
  * Visualizations: Summary Plots, Force Plots, Waterfall Plots, and Dependence Plots.
* **Counterfactual Explanations:** "What changes are required for the model to yield a different outcome?" (e.g., DiCE framework).

---

### 🔹 Module 3: Deep Learning Interpretability & Specialized XAI Approaches
**Objective:** Understand specialized XAI techniques for neural networks (Computer Vision & NLP) and evaluate explanation quality.

#### 3.1 Pixel & Attribution Methods for Neural Networks
* **Gradient-Based Methods:** Saliency Maps, Integrated Gradients, SmoothGrad.
* **Activation & Class-Based Methods:** Grad-CAM, HiResCAM, and Layer-wise Relevance Propagation (LRP).
* **Attention-Based XAI:** Visualizing attention weights in Transformer architectures (NLP / Vision Transformers).

#### 3.2 Validation, Pitfalls & Responsible AI
* **Evaluating Explanations:** Fidelity, Robustness, and Comprehensibility metrics.
* **Pitfalls & Vulnerabilities:** Sensitivity of XAI methods to adversarial attacks and input noise.
* **Fairness & Bias Detection:** Identifying gender, demographic, or racial bias via feature attribution analysis.

---

Week	Short title	Main topics
1	XAI Foundations & Interpretable Models	Why explainability matters; interpretability–accuracy tradeoffs; XAI taxonomy; responsible AI and regulatory context; interpreting linear/logistic regression and decision trees.
2	Global Explanations: Feature Effects	Permutation feature importance; PDP and ICE; ALE; feature interactions and the limitations of global plots.
3	Local Explanations: LIME & SHAP	Local surrogate explanations; Shapley value intuition and properties; practical LIME and SHAP; comparing local explanations.
4	Counterfactuals & Actionable Explanations	Counterfactual reasoning; DiCE; actionable changes, plausibility, and constraints; communicating explanations for individual predictions.
5	Project Assignment Workshop	Introduce the project brief and deliverables; choose a dataset and prediction task; select a model and XAI methods; plan experiments, evaluation, and presentation.
6	Explaining Neural Networks: Vision	Saliency maps; Integrated Gradients and SmoothGrad; Grad-CAM/HiResCAM; LRP; hands-on image-model explanations.
7	Explaining Text Models & Attention	Attribution for text classifiers; attention visualizations and their limitations; applying suitable XAI methods to NLP or transformer models.
8	Evaluating Explanations & Responsible AI	Fidelity, robustness, and comprehensibility; noise and adversarial vulnerabilities; using explanations to investigate bias; project presentations and discussion.

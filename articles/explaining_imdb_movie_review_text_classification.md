# Explaining IMDb Movie Review Text Classification  
### Approximate Text Explanation (ATE)

**Author:** Tjark Prokoph  
**Published:** March 9, 2023  
**Read Time:** 3 min  

[GitHub Repository: tjarkpr/ate](https://github.com/tjarkpr/ate)  
> *Transformation of TensorFlow text classification models into local interpretable models to explain the base model.*

## Motivation

To make the decisions of models and algorithms used in classification and regression comprehensible, various procedures exist. These models often work with complex input data, leading to increasingly opaque or “black-box” decision-making.

Explanation procedures aim to clarify these decisions:
- **Local explanations** focus on a single input and how the model made its decision.
- **Global explanations** aim to model and understand all decisions made by the model.

Inspired by recent advancements in large language models like ChatGPT, the core question we explore is:  
**Which parts of a textual input caused the model to make a specific classification?**

## Approximate Local Text Explanation (ALTE)

**ALTE** is based on the [LIME](https://github.com/marcotcr/lime) (Local Interpretable Model-Agnostic Explanations) method.

### Goal:
To understand the influence of input components (text tokens) on the model’s output **for a single input**.

### Method:
1. The input text is broken into components (tokens).
2. A binary vector (same length as the number of tokens) is used to activate/deactivate tokens.
3. Many permutations of this vector are generated.
4. Each permutation is run through the original classification model.
5. The results form a **meta dataset**.
6. A **linear model** is trained on this dataset to locally approximate the decision boundary of the original model.

### Optimization:
- To handle the computational load:
  - **Permutation upper bound**
  - **Number of repetitions**
  - **Number of epochs** for training the linear model  
  ...are all configurable.
- The process includes **randomized, iterative refinement**, improving the quality of the linear approximation over time.

👉 **[ALTE Tutorial Notebook](https://gist.github.com/tjarkpr/931514e936999fb7e27a5f98c3576ca4)**

## Approximate Global Text Explanation (AGTE)

**AGTE** also builds on the LIME method but focuses on **global explanation** across the entire dataset.

![AGTE-Method]()

### Goal:
To understand how input components (tokens) affect the classification label **across all data points**.

### Method:
1. Repeats the ALTE process **N-fold** across multiple data points.
2. Trains **multiple linear models**, each capturing decision boundaries at different regions of the dataset.
3. Aggregates these models for a broader understanding of the classification logic.

### Output:
- The token influence data is transformed into **decision rule sets** using a **DecisionTree**.
- This enables structured, rule-based interpretation of the classification model.

👉 **[AGTE Tutorial Notebook](https://gist.github.com/tjarkpr/d08d175da0654a255686d13034b06e05)**

## Related Work

- **Paper:** *["Why Should I Trust You?": Explaining the Predictions of Any Classifier](https://arxiv.org/abs/1602.04938)* by Marco Tulio Ribeiro, Sameer Singh, Carlos Guestrin  
- **GitHub:** [marcotcr/lime](https://github.com/marcotcr/lime)  
- **Dataset:** IMDb Movie Reviews
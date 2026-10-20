# Google Foundational Courses: source-grounded principles

Course directory and key written lessons checked on 2026-10-13. This is a selective synthesis, not a transcript or evidence that all videos and exercises were completed. Google courses primarily teach ML practice and project delivery. The research interpretations below are adaptations.

## Four-course map

| Course | Official scope | Research interpretation |
| --- | --- | --- |
| [Introduction to Machine Learning](https://developers.google.com/machine-learning/intro-to-ml) | ML types; supervised learning; data, training, evaluation, inference | Understand what the model learns from and where predictions are expected to apply |
| [Machine Learning Crash Course](https://developers.google.com/machine-learning/crash-course) | Models, loss and metrics, data, overfitting, representations, production systems, fairness | Inspect evidence quality, evaluate generalization, diagnose failure, and consider the full system |
| [Problem Framing](https://developers.google.com/machine-learning/problem-framing) | Decide whether ML is appropriate; define outcome, output, and success | Make the motivating question and proxy assumptions explicit before choosing a method |
| [Managing ML Projects](https://developers.google.com/machine-learning/managing-ml-projects) | Feasibility, planning, metrics, experiments, pipelines, production, ethics | Explore under uncertainty, preserve experimental evidence, and revise plans |

Directory: https://developers.google.com/machine-learning/foundational-courses

## Principles and their boundaries

### 1. Define the goal before choosing technology

**Course:** [Understand the problem](https://developers.google.com/machine-learning/problem-framing/problem) asks for a goal in non-ML terms, checks whether ML is suitable, and uses a heuristic or non-ML solution as a benchmark. It considers data reliability, representation, inference-time availability, and whether predictions enable useful action.

**Research adaptation:** State the phenomenon or limitation independently of architecture. A scientific explanation is a legitimate outcome even without an immediate product action. Compare against a plausible simple account, not only a fashionable model.

### 2. Inspect proxies and objective alignment

**Course:** [Framing an ML problem](https://developers.google.com/machine-learning/problem-framing/ml-framing) distinguishes ideal outcomes, model goals, outputs, and proxy labels. Clicking or liking a video imperfectly approximates usefulness. The caching example shows why output design must reflect decision thresholds and whether they are fixed or dynamic.

**Research adaptation:** Training loss and benchmark scores are proxies for broader claims. Test the link between the learning signal and the intended capability. Do not prescribe classification universally: the course itself explains why dynamic thresholds may favor regression.

### 3. Separate model quality from success

**Course:** [Measuring success](https://developers.google.com/machine-learning/managing-ml-projects/success) distinguishes business and model metrics, recommends an agreed optimization metric and acceptability goals, and warns that impressive model metrics need not improve outcomes. Early real-world tests help establish the connection.

**Research adaptation:** Define the scientific claim and its required evidence. Mechanistic explanation, transfer reliability, annotation efficiency, and practical usefulness are different criteria. A benchmark gain supports only the capability measured under that protocol.

### 4. Data quantity and coverage are distinct

**Course:** [Supervised Learning](https://developers.google.com/machine-learning/intro-to-ml/supervised) distinguishes size from diversity, using many years of July weather versus coverage of all months. [Datasets, generalization, and overfitting](https://developers.google.com/machine-learning/crash-course/overfitting) emphasizes data quality, labels, preparation, and evaluation.

**Research adaptation:** Count independent sampling units and inspect sampling bias. More correlated windows do not necessarily broaden subject or condition coverage. Data emphasis is a diagnostic priority, not proof that algorithmic work is unimportant. Avoid converting illustrative course percentages into universal planning rules.

### 5. Start with interpretable baselines and a functioning pipeline

**Course:** [Implementing a model](https://developers.google.com/machine-learning/problem-framing/implement-model) recommends starting simply and establishing the data pipeline. Simple models help assess whether complexity is justified. It also discusses pretrained models and training-serving skew.

**Research adaptation:** A baseline anchors both performance and interpretation. Control alternative sources of improvement before attributing gains to a new design. Simplicity is a starting point, not a restriction on ambitious research.

### 6. Protect independent evaluation

**Course:** [Dividing the original dataset](https://developers.google.com/machine-learning/crash-course/overfitting/dividing-datasets) separates training, validation, and testing. Reusing tests to guide design can fit their peculiarities. It discusses duplicate examples, sufficient test size, representativeness, and mismatch with real-world data.

**Research adaptation:** Define independence at the level required by the claim. Use grouped or temporal splits when appropriate. The course's same-distribution guidance for routine evaluation does not rule out deliberately designed domain-shift tests; disclose their intended role.

### 7. Experiments are reproducible hypothesis tests

**Course:** [Experiments](https://developers.google.com/machine-learning/managing-ml-projects/experiments) recommends baselines, single small changes, recording poor or neutral results, and clear experiment artifacts. It identifies noise from initialization, shuffling, asynchronous updates, and small evaluation sets; repetition helps confirm results.

**Research adaptation:** Define expected results and competing explanations before running. Isolated changes help attribution; interactions may require other designs. Repetition addresses variability but does not repair leakage, unfair comparisons, or unsupported causal claims.

### 8. Diagnose with small reliable tests

**Course:** [Interpreting loss curves](https://developers.google.com/machine-learning/crash-course/overfitting/interpreting-loss-curves) considers bad examples, learning rate, NaNs, outliers, shuffling, and overfitting. A small trusted subset can help isolate training problems.

**Research adaptation:** Find the earliest unreliable stage and construct a discriminating check. Memorizing a tiny clean subset demonstrates trainability, not transfer or scientific validity.

### 9. Plan for uncertainty and revise the framing

**Course:** [ML project planning](https://developers.google.com/machine-learning/managing-ml-projects/planning) describes nonlinear progress, uncertain effort, time-boxing, portfolios of approaches, and evolving plans. [Experiments](https://developers.google.com/machine-learning/managing-ml-projects/experiments) discusses error analysis, reframing stalled projects, and stopping an approach when warranted. [Feasibility](https://developers.google.com/machine-learning/managing-ml-projects/feasibility) considers data, difficulty, prediction quality, technical requirements, and cost.

**Research adaptation:** Plan milestones around resolved uncertainties. Keep informative negative results. Reframe when evidence justifies it, while retaining the intellectual connection to the original motivation. Time-box an approach rather than assuming a hard problem must be abandoned quickly.

### 10. Examine the system and distribution of failures

**Course:** [Production ML systems](https://developers.google.com/machine-learning/crash-course/production-ml-systems) treats the model as one part of a broader data and serving ecosystem. [Fairness](https://developers.google.com/machine-learning/crash-course/fairness) asks practitioners to inspect training-data bias and prediction behavior beyond overall loss.

**Research adaptation:** Attribute results across the whole experimental pipeline. Inspect meaningful performance slices and failure conditions. Domain robustness and fairness are related but distinct; group metrics alone do not establish fairness, and appropriate fairness criteria depend on context.

## What the courses do not establish

- They do not validate any specific EEG hypothesis, architecture, or pretraining objective.
- They do not provide a complete theory of scientific novelty, causal identification, or field-specific statistics.
- Their incremental model improvement workflow can support research hygiene without defining the ambition or contribution of a research program.
- A research recommendation should combine these principles with actual domain evidence and the user's constraints.

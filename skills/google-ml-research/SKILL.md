---
name: google-ml-research
description: "Apply Google Machine Learning Foundational Courses principles to ML research framing, hypothesis-driven experiment design, failure diagnosis, and research retrospectives. Use for research mindset, problem framing, baseline and evaluation planning, or requests such as 研究思维、研究问题梳理、实验设计、实验失败分析、研究复盘. Not for routine implementation, manuscript polishing, or literature search alone."
---

# Google ML Research

Help the user convert an uncertain ML research idea into a clear question, a testable explanation, and an informative next experiment. Ground advice in Google's four Foundational Courses while distinguishing scientific inquiry from product optimization. Respond in the user's language; use plain language before technical precision.

## Source and scope

Read [course-principles.md](references/course-principles.md) when explaining the framework, attributing a principle, or selecting guidance for a research decision. It maps principles to official lessons and explains their research adaptation.

Read [eeg-research.md](references/eeg-research.md) only for EEG, neural decoding, or EEG foundation model requests. EEG examples are adaptations, not Google course claims or established findings.

Use supplied notes, experiment logs, and project instructions before inventing a workflow. Treat unprovided results as unknown. Use the cached principles for ordinary coaching; consult official pages when the user requests current course content, exact wording, or an uncertain attribution. Say what could not be verified. Do not imply video lessons or interactive exercises have been completed merely because their page was read.

This skill supports framing, planning, diagnosis, and learning. It does not itself authorize training runs, paid compute, external messages, publishing, or file deletion. Execute experiments only within the user's authorized task.

## Choose the relevant depth

Match the user's actual need; do not force every request through a full checklist.

- **Mindset learning:** Explain the relevant course principle, a concrete example, and a research habit the user can practice. Map the four courses when requested.
- **Idea or question framing:** Identify the phenomenon, important limitation, competing explanations, and decisive evidence. For ideation, briefly identify obvious approaches before considering a reasonable, less expected perspective.
- **Experiment planning:** Specify the hypothesis, comparison, evaluation boundary, resources, and decision after the result.
- **Failure diagnosis:** Locate the first unreliable stage, compare plausible causes, and propose a small test that distinguishes them.
- **Retrospective or stalled project:** State what was learned, what remains unresolved, and whether to continue, revise, or pause an approach based on evidence and cost.

If context is incomplete, develop the usable parts and mark assumptions. Ask only for missing information that changes the recommendation, such as the intended generalization claim, existing result, data split, or compute constraint.

## Research decision framework

### Start from the phenomenon and intended outcome

State the problem without architecture names first. Identify the affected setting or people and why it matters. For scientific work, success can be a robust new explanation, a boundary condition, or a reproducible phenomenon, not only a deployment metric.

Separate the observation from its proposed explanation and from the proposed method. A method's novelty is not evidence that the problem is important. Ask what simpler explanation or approach could already account for the result.

### Check alignment between goal, learning signal, and evidence

Trace: intended outcome → target or proxy → training objective → evaluation → proposed claim. Identify where improvement in one may fail to imply improvement in the next.

Distinguish training loss, model selection metrics, acceptability constraints, and scientific success criteria. Recommend a primary comparison metric when useful, with additional metrics needed for the claim. Do not assume that optimizing a proxy proves real usefulness or the proposed mechanism.

### Understand data before attributing model behavior

Inspect provenance, sampling unit, coverage, label construction, preprocessing, and feature availability at inference. Distinguish more examples from more independent subjects, sessions, conditions, or devices. Treat predictive correlation as a clue rather than causal proof.

Check whether the proposed question is answerable with the available data. Suggest a narrower claim or missing evidence when it is not. Do not prescribe scaling or a new loss as the default response to poor performance.

### Build baselines and evaluate the intended boundary

Use simple or established baselines to anchor interpretation. Keep preprocessing, data access, selection procedure, supervision, and compute comparable where they could explain the effect; disclose unavoidable differences.

Make the split match the claim: new samples, sessions, subjects, sites, devices, or time periods require appropriate independent units. Use validation for adaptive selection and preserve a held-out test for final confirmation. Repeated test-guided decisions weaken independence; report contamination instead of silently treating the test as untouched.

### Design experiments to change a judgment

An experiment should specify:

- The explanation being tested and a plausible alternative.
- What changes and what is held comparable.
- Expected observations if the explanation is supported or weakened.
- Evaluation unit, metric, variability checks, and relevant constraints.
- The decision each plausible outcome would inform.

Prefer a small, reliable experiment that resolves important uncertainty. Change one factor when isolating its contribution; use factorial or interaction comparisons when a hypothesis concerns combinations. Ablation gains alone do not establish a causal mechanism.

Account for initialization, sample order, small evaluation sets, and selection effects. Use repeated runs or uncertainty estimates proportional to the size and importance of the claimed effect. Do not invent a universal seed count or significance threshold.

Record negative and neutral results with configurations and data versions. An unsuccessful run is informative only when its implementation and evaluation are trustworthy. Label unexecuted designs as proposals; never fabricate outcomes.

### Diagnose anomalies and update the question

Follow the evidence through data → preprocessing → training → selection → evaluation. Check integrity and implementation before recommending architectural changes. A tiny trusted subset can test trainability; it cannot establish generalization.

Analyze errors and performance slices, not only averages. Ask whether failures cluster by condition or population. Distinguish domain robustness from fairness, and examine fairness when people and consequences make it relevant.

Keep plans provisional. Estimate cost and uncertainty, time-box an approach where useful, and revise after observing evidence. Reframe a stalled question when learning supports doing so. Do not demand steady weekly metric gains or promise success on a schedule.

Google's incremental engineering advice supports reliable exploration; do not turn it into a requirement that research must pursue only incremental contributions. Preserve room for a broader conceptual explanation and adjacent-domain connections.

## Deliver a useful artifact

Lead with the current judgment and the most consequential uncertainty. Choose an output that fits the request: a course explanation, research card, experiment table, diagnosis, or retrospective. Scale detail to the available evidence.

For a new project, a compact research card can contain:

1. **Problem:** The phenomenon and why it matters.
2. **Evidence:** What has actually been observed; what is assumed.
3. **Hypothesis:** The proposed explanation and a credible alternative.
4. **Alignment gap:** Where data, objective, or evaluation may miss the goal.
5. **Experiment:** Baseline, comparison, evaluation boundary, and expected patterns.
6. **Decision:** What would lead to continuation, revision, or stopping this approach.

For results, include what changed, uncertainty, competing interpretations, and the next test. Cite the relevant Google lessons when explaining the framework; do not attach course citations to unverified domain claims.

Before delivering, check that the proposed experiment could distinguish explanations, the evaluation supports the stated scope, and the recommendation follows from evidence rather than enthusiasm for a model.

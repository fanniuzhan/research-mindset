# EEG research adaptation

Use only for EEG and neural decoding contexts. These are research prompts and example designs, not established conclusions or content attributed to Google.

## Questions that change the research decision

- **Claim boundary:** New windows, sessions, subjects, datasets, montages, devices, or tasks? Define which capability is claimed and which is actually evaluated.
- **Independent unit:** How many subjects and recordings underlie the window count? Adjacent or overlapping windows can make random splits misleading for broader transfer claims.
- **Sampling and labels:** Are task, stimulus, response, clinical label, and actual neural state being conflated? Are classes confounded with session, device, dataset, or preprocessing?
- **Pipeline:** Reference, channel order, units, filtering, resampling, artifacts, windowing, and normalization can change results. Fit learned preprocessing using permitted training information. If target-subject adaptation or calibration is allowed, declare its data and compare baselines under the same access.
- **Foundation model boundary:** Check potential overlap between pretraining and downstream evaluation. State whether unseen subjects, tasks, and datasets were absent from pretraining or only from downstream fine-tuning.
- **Objective alignment:** Which information does pretraining preserve, and which downstream tasks require it? Treat the link between reconstruction and neural decoding as an empirical question.
- **Comparison:** Match downstream labels, selection protocol, preprocessing, and relevant compute or parameter budgets. Distinguish linear probing from full fine-tuning.
- **Stability:** Inspect per-subject or per-session variability and meaningful worst-case behavior. Avoid treating dependent windows as independent evidence for population transfer.

## Example: reconstruction and transfer

**Motivation:** Reliable decoding for new subjects with limited annotations.

**Possible observation:** Reconstruction improves while subject-held-out decoding does not. Confirm this pattern before explaining it.

**Candidate explanation:** The objective may preserve subject-specific or background information more strongly than task-useful transferable information.

**Alternatives:** Optimization or fine-tuning differences, preprocessing inconsistency, inadequate labels, model capacity, inappropriate pooling, pretraining overlap, or high evaluation variance.

**Small next test:** Compare checkpoint-wise reconstruction and downstream decoding under a fixed selection and evaluation protocol. Use simple or established baselines and repeated evaluation proportional to variability. Probe whether representation changes track task information, subject information, or both. Subject predictability alone does not prove a shortcut or harmful representation.

**Interpretation:** A stable dissociation supports further objective-alignment investigation. It does not establish the hidden cause. If the dissociation disappears with an aligned evaluation pipeline, investigate that explanation first. If instability dominates, improve evidence reliability before introducing another method.

## Choose the next experiment by uncertainty

| Uncertainty | Candidate check | What it can establish |
| --- | --- | --- |
| Does the training implementation function? | Fit a tiny trusted subset; inspect data and gradients | Trainability and possible implementation faults |
| Is transfer failure reproducible? | Repeat the relevant subject/session-held-out evaluation | Reliability of the phenomenon under that protocol |
| Does the new module contribute? | Controlled removal or substitution with matched data and selection | Contribution under the tested conditions, not mechanism by itself |
| Is an effect tied to a nuisance factor? | Stratify or intervene while preserving meaningful task information | Dependence on that factor, within the intervention's limitations |
| Is a representation useful without adaptation? | Linear probe with declared preprocessing and label budget | Accessible task information under that readout |
| Does it reduce annotation requirements? | Label-budget curves with consistent sampling and model selection | Sample efficiency over the tested budgets |

Prefer EEG-specific explanations when evidence supports them: spectral structure, channel topology, temporal dynamics, cross-subject stability, and objective-to-task alignment. Increasing model or data size can be a valid control or useful direction; avoid treating it as an automatic explanation or an automatic prohibition.

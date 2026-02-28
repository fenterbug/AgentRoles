# Agent Role Effectiveness Evaluation

A methodology for quantifying the impact of using Agent Roles versus no role on task outcomes.

## Why Measure?

Agent Roles claim to improve consistency, quality, and efficiency. This framework provides a repeatable way to test that claim—so you can make data-driven decisions about which roles to invest in and where they add the most value.

## Evaluation Design

Each evaluation compares two runs of **the same task**:

| Run | Setup |
|-----|-------|
| **Baseline** | Agent receives the task with no role specification |
| **Role** | Agent receives the same task plus a relevant Agent Role |

All other variables (model, temperature, task prompt, evaluator) are held constant between runs.

---

## Scoring Rubric

Score each dimension on a **1–5 scale** after the task completes.

### 1. Task Accuracy (1–5)
Does the output correctly fulfill the stated requirements?

| Score | Meaning |
|-------|---------|
| 1 | Major requirements missed or incorrect |
| 2 | Some requirements met; significant gaps |
| 3 | Most requirements met; minor gaps |
| 4 | All requirements met; trivial issues only |
| 5 | Requirements fully met with no issues |

### 2. Output Quality (1–5)
Is the output well-structured, clear, and appropriate for its audience?

| Score | Meaning |
|-------|---------|
| 1 | Poorly structured, unclear, or inappropriate |
| 2 | Usable but rough; needs significant revision |
| 3 | Acceptable quality; light revision needed |
| 4 | Good quality; ready with minor polish |
| 5 | Excellent quality; publication-ready |

### 3. Consistency (1–5)
Does the output follow predictable patterns aligned with the role's defined behavior?

| Score | Meaning |
|-------|---------|
| 1 | Inconsistent; unpredictable output structure |
| 2 | Mostly inconsistent; occasional alignment |
| 3 | Somewhat consistent; deviates occasionally |
| 4 | Consistent; rare deviations |
| 5 | Fully consistent with role guidelines |

### 4. Scope Adherence (1–5)
Did the agent stay within the expected boundaries (neither under- nor over-reaching)?

| Score | Meaning |
|-------|---------|
| 1 | Far outside expected scope |
| 2 | Noticeably out of scope |
| 3 | Mostly in scope; minor drift |
| 4 | In scope; trivial drift |
| 5 | Perfectly scoped |

### 5. Efficiency (1–5)
Was the output produced without unnecessary verbosity, repetition, or wasted steps?

| Score | Meaning |
|-------|---------|
| 1 | Extremely verbose or repetitive |
| 2 | Noticeably inefficient |
| 3 | Acceptable; some excess |
| 4 | Efficient; minimal excess |
| 5 | Concise and direct |

---

## Scorecard Template

Copy this table for each evaluation run.

```
Task ID:        _______________________________________________
Task:           _______________________________________________
Role Used:      _______________________________________________  (or "None" for baseline)
Model:          _______________________________________________
Date:           _______________________________________________
Evaluator:      _______________________________________________

┌──────────────────────┬────────────────┬───────────────┐
│ Dimension            │ Baseline Score │ Role Score    │
├──────────────────────┼────────────────┼───────────────┤
│ Task Accuracy        │      /5        │      /5       │
│ Output Quality       │      /5        │      /5       │
│ Consistency          │      /5        │      /5       │
│ Scope Adherence      │      /5        │      /5       │
│ Efficiency           │      /5        │      /5       │
├──────────────────────┼────────────────┼───────────────┤
│ TOTAL                │     /25        │     /25       │
└──────────────────────┴────────────────┴───────────────┘

Improvement: ___ points  ( ___% )

Notes:
_______________________________________________
_______________________________________________
```

---

## Interpreting Results

| Score Difference | Interpretation |
|-----------------|----------------|
| +10 or more | Strong role benefit — role is highly effective for this task type |
| +5 to +9 | Moderate benefit — role adds meaningful value |
| +1 to +4 | Marginal benefit — role helps but may not justify overhead |
| 0 | Neutral — role had no measurable impact |
| Negative | Role may be hurting — revisit role design |

---

## Example Evaluation

### Task: Review a Python function for correctness and style

**Baseline prompt:**
```
Review the following Python function for correctness and style issues.
[code]
```

**Role prompt:**
```
You are adopting the Code Reviewer role.
[paste roles/technical/code-reviewer/ROLE.md]

Review the following Python function for correctness and style issues.
[code]
```

**Results:**

```
Task ID:        eval-001
Task:           Review Python function for correctness and style
Role Used:      Code Reviewer
Model:          (your model here)
Date:           (date)
Evaluator:      (your name)

┌──────────────────────┬────────────────┬───────────────┐
│ Dimension            │ Baseline Score │ Role Score    │
├──────────────────────┼────────────────┼───────────────┤
│ Task Accuracy        │     3/5        │     5/5       │
│ Output Quality       │     3/5        │     4/5       │
│ Consistency          │     2/5        │     5/5       │
│ Scope Adherence      │     3/5        │     4/5       │
│ Efficiency           │     3/5        │     4/5       │
├──────────────────────┼────────────────┼───────────────┤
│ TOTAL                │    14/25       │    22/25      │
└──────────────────────┴────────────────┴───────────────┘

Improvement: +8 points (+32%)

Notes:
Baseline output missed two style issues and was inconsistently
formatted across runs. Role output followed a consistent
structure and caught all issues.
```

---

## Running Multiple Evaluations

To get statistically meaningful results:

1. **Use at least 5 tasks** per role being evaluated.
2. **Use different evaluators** for the same task where possible.
3. **Randomize presentation order** so evaluators don't know which run is baseline vs role.
4. **Aggregate scores** by averaging across tasks and evaluators.

### Aggregate Scorecard

```
Role:           _______________________________________________
Tasks Evaluated: ____
Evaluators:      ____

┌──────────────────────┬──────────────────┬─────────────────┐
│ Dimension            │ Avg Baseline     │ Avg Role Score  │
├──────────────────────┼──────────────────┼─────────────────┤
│ Task Accuracy        │       /5         │       /5        │
│ Output Quality       │       /5         │       /5        │
│ Consistency          │       /5         │       /5        │
│ Scope Adherence      │       /5         │       /5        │
│ Efficiency           │       /5         │       /5        │
├──────────────────────┼──────────────────┼─────────────────┤
│ TOTAL                │      /25         │      /25        │
└──────────────────────┴──────────────────┴─────────────────┘

Overall Improvement: ___ points  ( ___% )
```

---

## Choosing Tasks for Evaluation

Good evaluation tasks:

- Are **representative** of the role's stated purpose
- Have **objectively verifiable** requirements
- Can be completed in a **single agent turn**
- Are **novel** (not likely in training data verbatim)
- Are **repeatable** (same prompt produces comparable outputs)

Avoid tasks that are too open-ended (making scoring subjective) or too trivial (where any agent scores 5/5 without a role).

---

## Contributing Evaluation Results

If you run evaluations and want to share your findings, open a pull request adding your results to `evaluations/` using the filename format:

```
evaluations/<role-name>-eval-<YYYY-MM-DD>.md
```

Include the completed scorecard(s) and any notes on your setup.

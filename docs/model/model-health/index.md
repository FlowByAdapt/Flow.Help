# Model Health

**Model Health** audits the current Revit project for common model-quality issues and presents the results through a coordinated health dashboard.

Use it to assess overall model health, review individual audit checks, investigate affected elements and manage issues that have been intentionally ignored.

!!! info "Model Health is currently evolving"

	Model Health is being progressively expanded with additional checks and model-review capabilities.

	The available checks and scoring behaviour may develop as the tool is tested across a wider range of projects.

---

## Open Model Health

On the Revit ribbon:

**Flow → Model → Health**

Model Health opens for the current Revit project.

---

## What do you want to do?

### Run a Model Health Audit

Run the available audit checks and review the overall health of the current project.

The dashboard summarises the model health score, checks completed, checks requiring attention and issues identified.

➡️ [**Running Health Checks**](running-health-checks.md)

### Review Identified Issues

Select a check requiring attention and review the individual issues identified by the audit.

Where an issue relates to Revit elements, Model Health can help select the affected elements in the project.

➡️ [**Reviewing Issues**](reviewing-issues.md)

### Having Problems?

Find help if an audit cannot be completed, expected issues are not shown, an affected element cannot be located or the displayed results are no longer current.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Model Health Dashboard

After an audit has been run, the dashboard provides a summary of the current results.

The summary includes:

* **Model Health** — the calculated health score and rating.
* **Audit Checks** — the number of checks executed.
* **Passed** — checks where no issues were identified.
* **Needs Attention** — checks containing one or more issues.
* **Issues Found** — the total number of identified issues, together with a severity breakdown.

The audit results below the dashboard show the status of each individual check.

!!! tip "Use the dashboard as an overview"

	The Model Health score provides a quick indication of overall model condition.

	Use the individual audit results and issue details to understand what is contributing to the score.

---

## Health Score

The **Model Health** score provides a simple overall indication of the conditions identified by the current audit.

The score is affected by both:

* the number of issues identified; and
* the severity of those issues.

Higher-severity issues have a greater effect on the score.

The current health ratings are:

| Score  | Rating    |
| ------ | --------- |
| 95–100 | Excellent |
| 85–94  | Good      |
| 70–84  | Fair      |
| 50–69  | Poor      |
| 0–49   | Critical  |

The Model Health card changes its visual emphasis according to the current rating.

!!! note "A model-health indicator"

	The Model Health score is a Flow model-quality indicator intended to help identify models that may require attention.

	It is not a Revit performance score or a formal project-compliance assessment.

---

## Getting Help

Hover over **Health** on the Flow ribbon and press **F1** to return directly to this page.
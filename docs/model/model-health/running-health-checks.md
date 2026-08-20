# Running Model Health Checks

Use **Model Health** to audit common model-quality conditions within the current Revit project.

A Model Health audit runs the available checks together and presents the results through the Model Health dashboard.

---

## Open Model Health

On the Revit ribbon:

**Flow → Model → Health**

The Model Health window opens for the current project.

---

## Run an Audit

Click:

**Run Audit**

Flow evaluates the current project using the available Model Health checks.

When the audit has completed, the dashboard and audit results are updated to show the current findings.

!!! info "The audit reviews the current project"

	Model Health evaluates the state of the active Revit project when **Run Audit** is used.

	If the model changes afterwards, run the audit again to update the results.

---

## Available Health Checks

The current Model Health audit includes the following checks.

### Revit Warnings

Reviews warnings reported by Revit and identifies warning conditions requiring attention.

### Imported CAD

Identifies imported CAD content within the project.

### In-Place Families

Identifies in-place families within the project.

### Unplaced Rooms

Identifies rooms that are not currently placed.

### Model Groups

Identifies model groups within the project.

### Duplicate Marks

Checks supported model categories for duplicate **Mark** values.

Duplicate marks are evaluated within their respective Revit category rather than across unrelated categories.

The currently supported categories include:

* Doors
* Windows
* Rooms
* Mechanical Equipment
* Plumbing Fixtures
* Generic Models
* Specialty Equipment
* Casework
* Furniture

!!! note "The audit library is still developing"

	Additional Model Health checks may be introduced as the tool continues to develop.

---

## Review the Dashboard

After the audit completes, the summary cards at the top of Model Health provide an overview of the results.

### Model Health

Displays the overall health score and rating.

The card is visually highlighted according to the current model-health rating.

### Audit Checks

Shows the total number of checks executed during the audit.

### Passed

Shows how many checks completed without identifying issues.

### Needs Attention

Shows how many checks identified one or more issues requiring review.

### Issues Found

Shows the total number of issues identified.

A severity summary is also displayed, showing the number of:

* Critical
* High
* Medium
* Low

severity issues.

---

## Understand the Health Score

The Model Health score provides a quick indication of the overall audit result.

Issues reduce the score according to their severity, with higher-severity conditions having a greater effect.

The current ratings are:

| Score  | Rating    |
| ------ | --------- |
| 95–100 | Excellent |
| 85–94  | Good      |
| 70–84  | Fair      |
| 50–69  | Poor      |
| 0–49   | Critical  |

!!! tip "Use the score to identify the overall condition"

	The score is most useful as a high-level indicator.

	Review the individual checks and identified issues to understand what is contributing to the current result.

---

## Review the Audit Results

Each audit check appears as a row in the results table.

The table shows:

* **Check**
* **Category**
* **Severity**
* **Status**
* **Issues**
* **Duration**

A check with no identified issues is shown as:

**Passed**

A check containing one or more issues is shown as:

**Failed**

The **Issues** column shows the number of issues identified by that check.

The **Duration** column shows approximately how long the check took to execute.

---

## Review a Check

Select a check containing issues and click:

**Review Issues**

The Issue Details window opens with the individual issues identified by that check.

After an audit, Model Health automatically selects a result containing issues where one is available.

See [**Reviewing Issues**](reviewing-issues.md) for the issue-review workflow.

---

## Run the Audit Again

After making changes to the Revit model, click:

**Run Audit**

The checks are run again against the current model and the dashboard is updated with the new results.

!!! tip "Re-run after resolving issues"

	Model Health results represent the model at the time the audit was run.

	Re-run the audit after making significant corrections before relying on the displayed score or issue counts.

---

## Related Help

* [Model Health](index.md)
* [Reviewing Issues](reviewing-issues.md)
* [Troubleshooting](troubleshooting.md)
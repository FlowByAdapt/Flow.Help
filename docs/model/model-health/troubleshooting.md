# Model Health Troubleshooting

Use the following checks if Model Health cannot complete an audit, expected results are unavailable or an affected element cannot be reviewed as expected.

---

## Run Audit Does Not Complete

If **Run Audit** does not complete:

1. Confirm that the required Revit project is open.
2. Confirm that the project remains available and responsive.
3. Review any message displayed by Flow.
4. Close and reopen Model Health if necessary.
5. Run the audit again.

If the problem consistently occurs on the same project, record the project and Revit version when reporting the problem.

---

## A Check Shows Passed When I Expected Issues

A check shown as **Passed** means that the current audit did not identify an issue for that check.

First:

1. Confirm that the expected condition still exists in the model.
2. Click **Run Audit** to make sure the displayed results are current.
3. Review what the particular audit check evaluates.

Some checks intentionally review a defined set of model conditions rather than every possible variation.

!!! note "Duplicate Marks uses supported categories"

	The Duplicate Marks check reviews duplicate Mark values within supported Revit categories.

	The same Mark value used by elements belonging to different categories is not treated as a duplicate by this check.

---

## Review Issues Is Not Available

**Review Issues** requires a selected audit result containing one or more issues.

If the command is not available:

1. Review the **Status** and **Issues** columns.
2. Select a check showing **Failed**.
3. Confirm that its **Issues** value is greater than zero.
4. Click **Review Issues** again.

After an audit, Model Health normally selects a result containing issues automatically.

---

## No Issues Are Shown

If an audit check shows:

**Passed**

and:

**Issues → 0**

the check completed without identifying the condition it is designed to detect.

This is different from a check containing identified issues, which is shown as **Failed**.

---

## I Cannot Select an Affected Element

If an issue is shown but the expected element cannot be selected:

1. Confirm that the element still exists in the project.
2. Close the issue review.
3. Click **Run Audit** again.
4. Reopen **Review Issues**.
5. Select the issue again.

The model may have changed since the previous audit was run.

---

## The Element Is Selected but I Cannot See It

A selected element may not be visible in the current Revit view.

This can occur because of normal Revit visibility conditions such as:

* the active view;
* view range;
* category visibility;
* view templates;
* temporary hide/isolate;
* phase settings; or
* other view-specific visibility controls.

Use the normal Revit tools to inspect the selected element where required.

---

## My Results Are Out of Date

Model Health results represent the state of the project when the audit was last run.

If the model has changed:

1. Return to the main Model Health window.
2. Click **Run Audit**.
3. Wait for the audit to complete.
4. Review the updated dashboard and results.

!!! info "Re-run after changing the model"

	Model Health does not treat an earlier audit as a live representation of every subsequent model change.

	Run the audit again when you need an updated assessment.

---

## My Health Score Did Not Change

The health score is calculated from the issues identified by the current audit.

If you have corrected an issue but the score has not changed:

1. Confirm that the model change has been completed.
2. Click **Run Audit** again.
3. Check whether the relevant audit result has changed.
4. Review the updated issue and severity counts.

The score will only reflect conditions identified by the latest audit.

---

## An Ignored Issue Is Missing

Issues that have been intentionally ignored are managed separately from the active issue-review workflow.

From the main Model Health window, click:

**Ignored Issues**

Review the ignored items and restore an issue if it should return to the active review workflow.

!!! warning "Ignored does not mean resolved"

	Ignoring an issue does not modify the Revit model or correct the underlying condition.

	It records that the issue has been intentionally excluded from the current active review.

---

## Restore View Does Not Return Me Where Expected

**Restore View** is intended to return to the Revit view state stored during the Model Health review workflow.

If the expected view cannot be restored:

1. Confirm that the original view still exists.
2. Check whether the document or view state has changed since the issue was reviewed.
3. Return to the required view manually if necessary.

---

## Duplicate Marks Takes Longer Than Other Checks

The Duplicate Marks check may take longer than some simpler audit checks because it reviews eligible model elements and compares their Mark values within supported categories.

A longer duration does not necessarily indicate a problem.

The **Duration** column is provided primarily as information about audit execution.

---

## Reporting a Problem

If the problem continues, record:

* the Revit version;
* the health check involved;
* what you expected to happen;
* what happened instead;
* any error message displayed by Flow; and
* a screenshot of Model Health or the relevant issue details where useful.

Because Model Health is still being developed, examples from real projects are particularly useful for identifying checks or workflows that need refinement.

---

## Related Help

* [Model Health](index.md)
* [Running Health Checks](running-health-checks.md)
* [Reviewing Issues](reviewing-issues.md)
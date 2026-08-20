# Reviewing Model Health Issues

Model Health groups identified issues by audit check so that they can be reviewed without working through the model manually.

Where an issue relates to Revit elements, Model Health can help select the affected elements in the project.

---

## Select a Health Check

After running an audit, review the results table in the main Model Health window.

Select a check with:

**Status → Failed**

and an **Issues** count greater than zero.

After an audit, Model Health automatically selects a result containing issues where one is available.

---

## Open the Issue Details

With the required check selected, click:

**Review Issues**

The Issue Details window opens and displays the issues identified by that check.

!!! tip "Review Issues requires an identified issue"

	**Review Issues** is available when the selected audit check contains one or more issues.

	If the selected check has passed, select a check containing issues instead.

---

## Review the Issues

The Issue Details window provides more information about the conditions identified by the selected audit check.

Depending on the issue, the available information can include:

* the issue description;
* the number of affected Revit elements;
* the issue severity; and
* a suggested action for reviewing or correcting the condition.

Some checks can return several separate issues.

For example, a check may identify different groups of affected elements that need to be reviewed independently.

---

## Select Issues

Select the issue or issues that you want to investigate.

Where an issue is associated with Revit elements, the selected issue can then be used to select the corresponding elements in the project.

!!! info "Not every issue is the same"

	Different audit checks identify different types of model conditions.

	The number of affected elements and the appropriate corrective action therefore depend on the check being reviewed.

---

## Select Affected Elements

For an issue associated with Revit elements, use the available selection control to select the affected elements in Revit.

This allows the elements identified by the audit to be inspected using the normal Revit tools.

Model Health identifies the elements requiring attention but does not automatically correct the underlying model condition.

!!! tip "Review the model before changing it"

	Selecting affected elements provides a direct route from the audit result back to the Revit model.

	Review the surrounding model context before deciding how the issue should be resolved.

---

## Resolve an Issue

Use the issue description and suggested action as guidance when reviewing the identified condition.

Make the required correction using the appropriate Revit tools.

Examples may include:

* resolving a Revit warning;
* removing or replacing imported CAD;
* reviewing an in-place family;
* placing or removing an unplaced room;
* reviewing model-group usage; or
* assigning unique Mark values.

Model Health is currently primarily an **audit and review tool**. Corrective changes remain under the user's control.

---

## Ignore an Issue

Some identified conditions may be intentional or accepted for the current project.

Where appropriate, an issue can be ignored so that it can be managed separately from issues still requiring attention.

Use the available issue controls to ignore the selected issue.

!!! warning "Ignore only accepted conditions"

	Ignoring an issue does not correct the underlying Revit model condition.

	Use it for conditions that have been reviewed and intentionally accepted rather than simply to remove unwanted audit results.

---

## Review Ignored Issues

From the main Model Health window, click:

**Ignored Issues**

The Ignored Issues window allows previously ignored Model Health issues to be reviewed.

Ignored items can be restored when they should once again be included in the active review workflow.

---

## Restore the Revit View

Model Health may temporarily change the Revit view or selection while affected elements are being investigated.

Use:

**Restore View**

from the main Model Health window to return to the previously stored view state where available.

---

## Check the Model Again

After correcting model issues, return to Model Health and click:

**Run Audit**

Flow evaluates the current model again and updates:

* the health score;
* passed checks;
* checks requiring attention;
* total issue count;
* severity counts; and
* individual audit results.

The new audit results can then be used to confirm whether the correction resolved the identified condition.

---

## Related Help

* [Model Health](index.md)
* [Running Health Checks](running-health-checks.md)
* [Troubleshooting](troubleshooting.md)
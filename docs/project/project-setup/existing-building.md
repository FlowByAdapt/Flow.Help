# Existing Building

**Existing Building** prepares an existing Revit model by reviewing its element phasing and removing identified demolished or redundant Existing Building content.

The workflow is completed in two stages:

**Phasing → Cleanup**

Complete **Phasing first**. After phasing changes are applied, Flow automatically reinspects the model and refreshes the Cleanup results before anything is deleted.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Existing Building

Use **Existing Building** when preparing a Revit model that contains existing or previously modelled building information that needs to be brought into the standard Flow Existing Building state.

The workflow can:

* inspect phase-bearing model elements
* identify elements created outside the target Existing phase
* identify which of those elements Flow can update
* apply the target Existing phase where possible
* identify demolished elements
* identify Rooms
* identify Room Separation Lines
* remove the inspected Cleanup targets after confirmation

!!! important "Phasing first"

	Always complete the **Phasing** review before Cleanup.

	Applying phasing can change the resulting Cleanup population, so Flow automatically refreshes Cleanup after phasing has been applied.

---

## Before You Start

Open or activate the Revit project you want to prepare.

Select **Inspect Project** so the Existing Building status can be included in the Setup Overview.

If Existing Building requires attention, select the available review action to open **Existing Building Review**.

!!! warning "Existing Building can modify and delete model content"

	Inspection itself is read-only.

	**Apply Phasing** changes element phasing and **Clean Up** deletes identified model content.

	Review the results and confirmations before applying either operation.

---

## Opening Existing Building Review

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

If Existing Building cleanup targets are found, open the **Existing Building Review** from the Current Project area.

The review window displays **Phasing** first, followed by **Cleanup**.

The Phasing section is marked **Start here**.

<!-- Screenshot recommended:
Show the complete Existing Building Review window in its initial state.
Phasing should be clearly visible first with the Start here indicator, with Cleanup visible below.
This is the most important screenshot on this page because it establishes the required workflow order.
-->

---

## Existing Building Workflow

Use the workflow in this order:

1. **Inspect Phasing**
2. Review the Phasing results
3. **Apply Phasing** where required
4. Flow automatically reinspects Phasing
5. Flow automatically refreshes Cleanup
6. Review the refreshed Cleanup results
7. **Clean Up** where required
8. Flow automatically reinspects Cleanup

Do not use an earlier Cleanup count as the expected deletion count after applying phasing.

---

## Inspecting Phasing

### 1. Select Inspect Phasing

In the Phasing section, select **Inspect Phasing**.

Flow examines the relevant phase-bearing elements in the active project.

### 2. Review the Phasing Summary

Flow reports:

* the number of candidate elements
* the number currently outside the target Existing phase
* the number of writable elements that can be updated
* the number of read-only elements that Flow cannot directly change

The actionable count represents writable elements that are currently outside the target Existing phase.

<!-- Screenshot recommended:
Show the Phasing section after inspection.
Include the candidate count, elements outside Existing, Writable summary, Read-only summary and enabled Apply Phasing action.
-->

---

## Writable and Read-Only Elements

Not every phase-bearing Revit element can necessarily be changed by Flow.

### Writable

A writable element has a Phase Created value that Flow can modify in the current project state.

If it is outside the target Existing phase, it can be included in **Apply Phasing**.

### Read-Only

A read-only element may participate in the phasing inspection but cannot be directly updated by Flow.

Flow reports these separately rather than treating them as successfully changed.

!!! info "Read-only does not mean ignored"

	Read-only elements remain visible in the inspection results so that the remaining model state can be understood.

	Flow does not bypass Revit's read-only restrictions.

---

## Applying Phasing

### 1. Review the Inspection

Before applying changes, check:

* the target phase has been resolved
* the number of elements outside Existing
* the writable count
* the read-only count
* the number of actionable writable elements

**Apply Phasing** is only available when Flow has resolved the target phase and there are writable elements outside that phase.

### 2. Select Apply Phasing

Select **Apply Phasing**.

Flow displays a confirmation before changing the model.

### 3. Confirm the Phasing Changes

Review the confirmation and proceed when the inspected result is appropriate.

Flow updates the applicable writable elements to the target Existing phase.

### 4. Flow Reinspects Phasing

After the update, Flow automatically runs the Phasing inspection again.

This determines how many elements remain outside Existing after the operation.

### 5. Flow Refreshes Cleanup

Flow then automatically reinspects **Cleanup** using the updated model state.

This is important because changing element phasing can alter which elements Revit now reports as Cleanup targets.

---

## Expected Result After Applying Phasing

After successful phasing:

* applicable writable elements have been updated to Existing
* Flow has automatically reinspected Phasing
* the remaining elements outside Existing are reported
* Cleanup has automatically been refreshed
* the Cleanup counts now represent the updated model state

Flow reports the number of elements it directly updated and the number that remain outside Existing.

<!-- Screenshot recommended:
Show the Existing Building Review after Apply Phasing has completed.
The completion message or updated Phasing result should be visible together with the refreshed Cleanup counts.
This provides a useful before/after comparison with the initial inspection screenshot.
-->

---

## Revit May Change Additional Elements

The number of elements directly updated by Flow is not necessarily the total number of model elements whose phase state changes.

Revit can propagate phase changes to related or dependent elements as part of its own model behaviour.

For this reason, Flow distinguishes between:

* elements **directly updated by Flow**
* the model state found during the automatic follow-up inspection

!!! info "Flow reports direct changes"

	The Apply Phasing result reports the elements Flow directly changed.

	The follow-up inspection reports the resulting Revit model state, which may also reflect changes made automatically by Revit.

---

## Elements Excluded from Phasing

The Existing Building phasing workflow deliberately excludes elements whose names contain:

* `architrave`
* `panel`

The comparison is case-insensitive.

These exclusions preserve the behaviour established for the Existing Building preparation workflow and prevent those elements from being included in the direct phasing operation.

---

## Reviewing Cleanup

After Phasing has been completed, review the refreshed **Cleanup** section.

Cleanup identifies direct targets including:

* demolished elements
* Rooms
* Room Separation Lines

The displayed count represents the elements Flow has directly identified for the Cleanup operation.

!!! important "Use the refreshed Cleanup result"

	If Apply Phasing has been used, rely on the Cleanup counts shown **after** the automatic refresh.

	The number of Cleanup targets can change as a result of the phasing operation.

---

## Cleaning Up the Existing Building

### 1. Review the Cleanup Counts

Check the number of:

* demolished elements
* Rooms
* Room Separation Lines

Confirm that the resulting Cleanup population is appropriate before continuing.

### 2. Select Clean Up

Select **Clean Up**.

Flow displays a confirmation showing the direct number of identified Cleanup targets.

### 3. Confirm the Cleanup

Review the confirmation and select **Clean Up** to proceed.

Flow asks Revit to delete the identified direct Cleanup targets.

### 4. Respond to Revit Messages

Revit may identify dependent or hosted elements that are affected by the deletion.

Where required, Revit can display its own native deletion warning or confirmation.

Review the Revit message and respond appropriately.

For hosted demolished elements, this can include Revit asking you to confirm deletion of the affected element or elements.

### 5. Flow Reinspects Cleanup

After the Cleanup operation completes, Flow automatically runs the Cleanup inspection again.

The Cleanup section is updated from the resulting Revit model state.

---

## Expected Result After Cleanup

When all direct Cleanup targets have been removed, Flow reports:

**Cleanup completed successfully.**

**No demolished elements, rooms or room separation lines remain.**

The **Clean Up** action is no longer required while the inspection contains no Cleanup targets.

<!-- Screenshot recommended:
Show the Existing Building Review after successful Cleanup with zero remaining Cleanup targets.
This is useful as the final-state screenshot if space allows.
-->

---

## Direct Targets and Revit Dependent Deletions

The Cleanup count shown by Flow represents the **direct targets** identified by the Existing Building inspection.

Revit may delete additional dependent elements when those targets are removed.

The final number of elements affected by Revit can therefore be greater than the number shown in the Flow Cleanup confirmation.

!!! warning "Revit controls dependent deletion"

	Review any native Revit deletion messages carefully.

	Flow reports the direct Cleanup targets, but Revit determines what additional dependent model content must also be removed with them.

---

## Demolished Elements

Cleanup identifies applicable non-type elements that have a valid **Phase Demolished** assignment.

These elements form the demolished-element portion of the Cleanup result.

The exact population should always be reviewed before deletion.

---

## Rooms

Existing Building Cleanup includes Revit **Rooms** identified by the Cleanup inspection.

Rooms are reported separately in the Cleanup summary so their contribution to the deletion count is clear.

---

## Room Separation Lines

Existing Building Cleanup also identifies **Room Separation Lines**.

These are reported separately from Rooms and demolished model elements.

---

## View Templates Are Not Changed

Existing Building preparation does not clear or modify Revit view templates as part of the Phasing or Cleanup workflow.

View-template management is intentionally separate from these model preparation operations.

!!! info "View templates are outside this workflow"

	Do not expect Existing Building Cleanup to remove view-template assignments or alter view-template settings.

---

## If Apply Phasing Is Disabled

### Phasing Has Not Been Inspected

Select **Inspect Phasing** first.

### The Target Existing Phase Cannot Be Resolved

Flow must be able to identify the target Existing phase before it can apply changes.

### No Writable Elements Require a Change

If there are no writable elements outside the target Existing phase, there is nothing for **Apply Phasing** to update.

### Remaining Elements Are Read-Only

Elements that Revit does not allow Flow to modify remain reported but cannot be changed by Apply Phasing.

---

## If Elements Remain Outside Existing

A successful Apply Phasing operation does not guarantee that every inspected candidate will end up in Existing.

Remaining elements can include elements that:

* are read-only
* cannot be directly changed in their current Revit state
* are otherwise outside the actionable writable population

Review the follow-up Phasing inspection rather than assuming a successful operation means the remaining count must be zero.

!!! important "Cleanup and Phasing are separate results"

	Cleanup can reach zero targets while Phasing still reports elements outside Existing.

	A zero Cleanup count does not by itself mean that every phase-bearing element has been moved to Existing.

---

## If the Cleanup Count Changes After Phasing

This is expected.

Applying phasing changes the Revit model state.

Flow therefore automatically runs a fresh Cleanup inspection after Apply Phasing so that the deletion preview is based on the updated model rather than stale inspection results.

Use the refreshed Cleanup count when deciding whether to proceed.

---

## If Revit Displays a Deletion Warning

A native Revit warning during Cleanup does not necessarily mean Flow has failed.

Revit may need confirmation because deleting one of the direct Cleanup targets also affects hosted or dependent elements.

Read the Revit message carefully and choose the appropriate native Revit action.

If Revit prevents the deletion, resolve the reported model condition and inspect Cleanup again before retrying.

---

## If Cleanup Cannot Be Refreshed

After Apply Phasing, Flow attempts to refresh Cleanup automatically.

If the phasing operation succeeds but the follow-up Cleanup inspection cannot be completed, Flow reports that the phasing update completed but Cleanup could not be refreshed.

Do not rely on the previous Cleanup count.

Run the appropriate inspection again before using **Clean Up**.

---

## Repeating the Workflow

Existing Building Review can be reinspected as the model changes.

If Phasing still reports actionable elements, review the result before deciding whether another phasing operation is appropriate.

If Cleanup reports additional targets after subsequent model changes, review those targets before running Cleanup again.

---

## Related Help

* [Project Setup](index.md)
* [Reviewing a Current Project](current-projects.md)
* [Project Setup Troubleshooting](troubleshooting.md)
# Project Setup Troubleshooting

This page covers common issues that can occur while using **Project Setup**.

For the normal setup sequence, start with the [Project Setup](index.md) guide and follow the individual workflow pages for detailed instructions.

**Ribbon:** **Flow → Project → Setup**

---

## Project Setup Does Not Show the Current Project

If Project Setup was already open when you changed Revit documents, select **Refresh**.

Refresh updates Project Setup to the current Revit context.

If you open **Flow → Project → Setup** again while the window is already open, Flow returns to the existing Project Setup window and refreshes its context rather than opening another copy.

!!! info "Refresh does not inspect the project"

	Refresh updates the Revit context used by Project Setup.

	Select **Inspect Project** separately when you want Flow to assess the setup of the active project.

---

## Inspect Project Is Unavailable

### No Project Is Active

Open or activate a Revit project and try again.

### A Family Document Is Active

Project Setup inspection is intended for Revit project documents.

Open or activate a project document before selecting **Inspect Project**.

### An Inspection Is Already Running

Allow the current Project Setup inspection to complete before starting another inspection.

---

## The Setup Overview Has Changed

Project Setup automatically reinspects relevant areas after several successful operations.

For example:

* enabling Worksharing triggers another project inspection
* selecting an unresolved model role triggers another project inspection
* configuring Worksets triggers another project inspection
* creating Project Folders triggers folder reinspection
* applying Existing Building phasing triggers Phasing and Cleanup reinspection
* Existing Building Cleanup triggers cleanup reinspection

The updated status represents the resulting project or filesystem state.

This is normally expected.

---

## Project Identity Shows Start Here Again

Changing any reviewed Project Identity value clears the previous review.

This includes:

* Project Year
* Project Number
* Client
* Location

Check the revised information and select **Review Identity** again.

!!! info "Folder planning is also reset"

	Changing a reviewed Project Identity clears the existing project-folder plan.

	After reviewing the revised identity, inspect the Project Folders again before creating anything.

---

## Project Identity Cannot Be Reviewed

Check that the required Project Identity information has been entered correctly.

Review:

* Project Year
* Project Number
* Client
* Location

Correct the relevant value and select **Review Identity** again.

Actions that depend on a reviewed Project Identity remain unavailable until the identity passes validation.

---

## Create Project Is Disabled

Check the following.

### Project Identity Has Not Been Reviewed

Complete the Project Identity and select **Review Identity**.

### No Project Profile Is Selected

Select the appropriate **Project Profile**.

### The Required Template Is Unavailable

Check the template information shown in the New Project area.

The approved template for the selected Project Profile and current Revit version must be available.

### Project Creation Is Not Available

Project Setup determines whether project creation is available in the current Revit context.

Review the status shown in the New Project area.

See [Creating a New Project](new-projects.md).

---

## The Template Was Available but the Project Was Not Created

Flow checks the physical template again immediately before creating the project.

If the template has become unavailable since the Project Profile was selected, Flow stops the operation rather than creating the project from another template.

Check that the approved template remains accessible and try again.

---

## Project Information Requires Attention

Open the **Project Information** review and check the reported fields.

Possible conditions include:

* missing values
* values that differ from the proposed setup
* missing parameters
* read-only parameters

Review the proposed information before applying changes.

See [Project Information](project-information.md).

---

## A Project Information Value Cannot Be Changed

Revit may report a Project Information parameter as read-only.

Flow does not bypass Revit's read-only restrictions.

If a configured parameter does not exist or cannot be written, review the project/template configuration and the parameter itself.

---

## Project Folders Cannot Be Created

Check the status of each selected folder target.

Flow only creates selected targets that are currently reported as **Available**.

A target may not be available because:

* the exact project folder already exists
* the required year location is unavailable
* the required folder template is unavailable
* another folder conflicts with the project number
* an incomplete previous provisioning attempt exists
* another required part of the configured destination cannot be resolved

Review the reported target before attempting folder creation.

See [Project Folders](project-folders.md).

---

## The Project Folder Already Exists

If Flow finds the exact expected project folder, it identifies the existing folder rather than creating it again.

No folder creation is required for that target.

If the existing folder does not match the expected project identity, review the reported status before making manual changes.

---

## Flow Reports a Project Number Conflict

Another folder may already use the same project number without matching the exact expected project folder.

Check:

* the reviewed Project Identity
* the reported folder location
* the existing project folder

Resolve the conflict before attempting provisioning.

!!! warning "Do not delete an existing project folder simply to clear the status"

	First confirm which folder legitimately belongs to the project.

---

## Flow Reports an Incomplete Project Folder

An incomplete target indicates that a previous Flow folder provisioning operation did not finish successfully.

Review the target before continuing.

If the incomplete provisioning attempt can safely be discarded, use **Remove Incomplete Project Folder**.

!!! warning "Removal is permanent"

	Removing an incomplete project folder deletes that folder and everything currently contained within it.

	Check the reported location before confirming the operation.

After removal, Flow reinspects the affected target.

---

## Worksharing Requires Attention

The project may not yet be workshared.

Select **Enable Worksharing** and review the confirmation.

After successful enablement, Flow automatically reinspects Project Setup.

The standard Flow worksets are configured separately.

See [Worksharing](worksharing.md).

---

## Worksets Cannot Be Configured

### Worksharing Is Not Enabled

Enable Worksharing first.

### The Project Has Not Been Inspected

Select **Inspect Project**.

### The Model Role Is Unknown

Flow needs to know whether the model is a:

* **Main Project**
* **Topography**

Choose the appropriate role when prompted.

Flow records the role and reinspects the project before continuing with workset configuration.

See [Worksets](worksets.md).

---

## Flow Asks for the Model Role

This occurs when Flow cannot determine which workset configuration should apply to the project.

Choose:

* **Main Project** for the primary building model
* **Topography** for the topography/survey model

The selected role determines which standard worksets Flow expects.

!!! important "Choose the actual model role"

	Do not select a role simply to clear the Worksets warning.

	The role controls how Flow evaluates and configures the project.

---

## Additional Worksets Are Still Present

This is expected.

Flow does not delete unrelated existing worksets during standard Workset configuration.

The operation creates the required standard worksets and can rename the expected initial workset where required.

Additional worksets are preserved.

---

## Existing Building Requires Attention

Open **Existing Building Review**.

Complete the workflow in this order:

1. Select **Inspect Phasing**.
2. Review the Phasing results.
3. Select **Apply Phasing** where required.
4. Allow Flow to re-inspect Phasing.
5. Allow Flow to refresh Cleanup.
6. Review the refreshed Cleanup results.
7. Select **Clean Up** where required.

!!! important "Do not start with an old Cleanup result"

	Applying Phasing can change the Cleanup population.

	Use the Cleanup result produced after Flow's automatic refresh.

See [Existing Building](existing-building.md).

---

## Apply Phasing Is Disabled

Check the Phasing inspection.

**Apply Phasing** requires:

* a resolved target Existing phase
* at least one writable element outside that phase

If all remaining non-target elements are read-only, Flow cannot directly change them.

---

## Elements Remain Outside Existing After Apply Phasing

This does not necessarily mean the operation failed.

Flow reports the number of elements it directly updates and then reinspects the resulting model.

Some elements may remain outside Existing because they are read-only or cannot be directly modified in their current Revit state.

Review the updated **Writable** and **Read-only** results.

---

## The Cleanup Count Changed After Apply Phasing

This is expected.

Applying phasing changes the Revit model state and can affect which elements are identified for Cleanup.

Flow therefore:

1. applies the Phasing changes
2. reinspects Phasing
3. reinspects Cleanup
4. displays the refreshed Cleanup result

Use the new Cleanup count when deciding whether to proceed.

---

## Cleanup Is Zero but Phasing Still Requires Attention

Phasing and Cleanup report different model conditions.

A project can contain:

* no remaining demolished elements, Rooms or Room Separation Lines requiring Cleanup
* elements that are still outside the target Existing phase

A zero Cleanup count therefore does not mean that the Phasing inspection must also be zero.

Review the two results independently.

---

## Revit Displays a Warning During Cleanup

Revit may display its own native warning or deletion confirmation during Existing Building Cleanup.

This can occur when deleting a direct Cleanup target also affects hosted or dependent elements.

Review the Revit message carefully and choose the appropriate Revit action.

For some hosted demolished elements, Revit may ask you to confirm deletion of the affected element or elements.

!!! info "The Flow count is the direct target count"

	Flow reports the elements directly identified for Cleanup.

	Revit determines whether additional dependent elements must also be deleted.

	The total number of elements affected by Revit can therefore be greater than the count shown by Flow.

---

## Cleanup Did Not Remove Everything

After Cleanup, Flow automatically reinspects the model.

If targets remain, review the updated Cleanup result rather than relying on the original count.

Revit may have prevented part of the deletion or the resulting model state may still contain applicable Cleanup targets.

Resolve any Revit warnings or model conditions and reinspect before trying again.

---

## Cleanup Completed but Could Not Be Refreshed

If a model operation succeeds but the follow-up inspection cannot be completed, do not assume the previous inspection result is still current.

Run the appropriate inspection again before performing another destructive action.

For Existing Building, this is particularly important after Phasing because the previous Cleanup population may no longer represent the model.

---

## View Templates Did Not Change

This is expected.

Existing Building Phasing and Cleanup do not clear or modify Revit view templates.

View-template management is outside the Existing Building workflow.

---

## Refresh Did Not Update the Setup Statuses

**Refresh** does not perform a Current Project inspection.

It updates Project Setup to the current Revit context.

Select **Inspect Project** to reassess the project and update the Setup Overview.

---

## The Project Was Changed Outside Project Setup

If you manually change:

* Project Information
* Worksharing
* Worksets
* project-related model conditions
* other setup information

select **Inspect Project** when you return to Project Setup.

For Project Folders, use the folder inspection workflow so the filesystem targets are checked again.

---

## Still Having Problems?

If the issue remains:

1. Confirm that the correct Revit project is active.
2. Select **Refresh** if the active document has changed.
3. Select **Inspect Project**.
4. Review the individual status that requires attention.
5. Open the relevant workflow and review its latest inspection result.
6. Check any message reported by Flow or Revit.

Where possible, use the latest inspection result when diagnosing a problem rather than an earlier result collected before the project changed.

---

## Related Help

* [Project Setup](index.md)
* [Project Identity](project-identity.md)
* [Creating a New Project](new-projects.md)
* [Reviewing a Current Project](current-projects.md)
* [Project Information](project-information.md)
* [Project Folders](project-folders.md)
* [Worksharing](worksharing.md)
* [Worksets](worksets.md)
* [Existing Building](existing-building.md)
# Reviewing a Current Project

**Project Setup** can inspect the active Revit project and show which setup areas are complete, ready for the next step or require attention.

The **Current Project** workflow provides a Setup Overview for Project Information, Project Folders, Worksharing, Worksets and Existing Building preparation.

Inspection is read-only. Flow does not change the project simply because **Inspect Project** has been selected.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Current Project

Use the **Current Project** workflow when:

* continuing setup after creating a new project
* opening an existing project that needs to be checked
* reviewing whether the project meets the expected Flow setup
* checking what setup work remains
* returning to Project Setup after the project has been changed
* preparing an Existing Building project

---

## Before You Start

Open or activate the Revit project you want to inspect.

Project Setup inspection is available for Revit project documents. It cannot inspect a Revit family document as a project.

For workflows that depend on project naming or folder information, complete and review the **Project Identity** first.

!!! info "Inspection does not change the project"

	**Inspect Project** checks the current project state and reports the results.

	Changes such as enabling worksharing, configuring worksets or preparing an Existing Building model remain separate actions.

---

## Opening the Tool

Open:

**Flow → Project → Setup**

The **Current Project** area identifies the active Revit project and provides access to the project inspection workflow.

---

## Inspecting a Project

### 1. Activate the Project

Make sure the Revit project you want to inspect is the active document.

### 2. Select Inspect Project

In the Current Project area, select **Inspect Project**.

Flow checks the project setup and updates the Current Project results.

Existing Building cleanup is also inspected as part of the overall Current Project workflow.

### 3. Review the Setup Overview

When inspection is complete, review the **Setup Overview**.

The overview reports the current state of:

* **Project Information**
* **Project Folders**
* **Worksharing**
* **Worksets**
* **Existing Building**

Each area includes a status and summary to help identify the next required action.

<!-- Screenshot recommended:
Show the Current Project area immediately after Inspect Project has completed.
Use a project with a mixture of Complete, Ready and Attention Required statuses.
The Setup Overview and individual workflow cards should both be visible where practical.
-->

---

## Understanding the Setup Overview

Project Setup uses a common set of statuses.

| Status | Meaning |
| --- | --- |
| **Complete** | The inspected setup currently meets the required condition. |
| **Ready** | The area is ready for the next setup action. |
| **Attention Required** | Flow found something that requires review or action. |
| **Not Inspected** | The area has not yet been inspected. |
| **Not Applicable** | The area does not currently require an action. |

The status of each area reflects its own workflow.

For example, Worksharing may require attention while Project Information and Project Folders are already complete.

---

## Continue Setup

After inspection, **Continue Setup** can provide a shortcut to the next appropriate setup action.

Depending on the current project state, this can lead to actions such as:

* reviewing Project Information
* enabling Worksharing
* configuring Worksets
* inspecting Project Folders
* creating Project Folders

If the project has not yet been inspected, **Continue Setup** can start the inspection.

!!! info "Continue Setup does not run everything"

	Continue Setup identifies an appropriate next step.

	It does not automatically make every outstanding change to the project.

	Operations that modify the project remain explicit actions.

---

## Project Information

The **Project Information** area compares the configured Project Information fields with the values currently stored in Revit.

Select **Review / Update** to inspect the fields and prepare any required changes.

Changes are reviewed before they are written to the project.

See [Project Information](project-information.md).

---

## Project Folders

The **Project Folders** area checks the configured project-folder targets using the reviewed Project Identity.

Depending on the result, Flow can identify folders that:

* already exist
* are available to create
* cannot currently be created
* conflict with an existing project number
* appear to contain an incomplete previous Flow provisioning operation

Folder creation remains a separate confirmed action.

See [Project Folders](project-folders.md).

---

## Worksharing

The **Worksharing** area reports whether the active project is workshared.

If worksharing is required but has not yet been enabled, Flow can enable it as a separate confirmed operation.

After successful enablement, Flow automatically reinspects Project Setup so the Current Project results reflect the changed model state.

See [Worksharing](worksharing.md).

---

## Worksets

When the project is workshared, Flow can compare the existing worksets with the expected configuration for the project's model role.

If the model role cannot be determined, Flow asks whether the project is:

* **Main Project**
* **Topography**

The selected role is then used when determining the expected workset configuration.

Flow can preview the required workset changes before they are applied.

See [Worksets](worksets.md).

---

## Existing Building

The **Existing Building** area identifies projects containing Existing Building cleanup targets that require review.

Select **Review / Prepare** to open the Existing Building workflow.

The workflow is completed in this order:

1. Inspect **Phasing**.
2. Apply the required Existing Building phasing.
3. Flow automatically reinspects Phasing.
4. Flow automatically refreshes **Cleanup** against the updated model.
5. Review the refreshed Cleanup targets.
6. Select **Clean Up** where required.
7. Flow reinspects Cleanup after the operation.

!!! important "Complete Phasing first"

	Existing Building phasing can change how Revit treats related or dependent elements.

	For this reason, Flow refreshes Cleanup after phasing rather than relying on cleanup results collected before the phasing changes.

See [Existing Building](existing-building.md).

---

## Expected Result

After a successful Current Project inspection:

* the active project has been assessed without being modified
* the Setup Overview reflects the inspected project state
* each setup area displays its current status
* available setup actions are enabled where appropriate
* Continue Setup can identify an appropriate next step

You can then work through the areas that are Ready or require attention.

---

## Automatic Reinspection

Several Project Setup actions automatically perform a follow-up inspection after changing the project.

This includes:

* enabling Worksharing
* adopting a model role
* configuring Worksets
* applying Existing Building phasing
* cleaning up Existing Building content

Project Folder creation also performs its own follow-up folder inspection.

The purpose of these checks is to update the displayed results using the changed project state.

---

## Refresh vs Inspect Project

The **Refresh** button at the bottom of Project Setup is not the same as **Inspect Project**.

### Refresh

**Refresh** updates Project Setup to the current Revit context and refreshes information such as available Project Profiles and templates.

It clears the previous Current Project inspection because those results may no longer apply to the active context.

### Inspect Project

**Inspect Project** performs a new assessment of the active Revit project.

Use **Inspect Project** when you want the Current Project statuses to reflect the actual project setup.

!!! tip "Use Inspect Project after external changes"

	If the project has been changed outside the Project Setup workflow, select **Inspect Project** to reassess its setup.

---

## If Inspect Project Is Unavailable

### No Project Is Active

Open or activate a Revit project and try again.

### A Family Document Is Active

Project Setup inspection is intended for Revit project documents.

Open or activate a project document before selecting **Inspect Project**.

### An Inspection Is Already Pending

Flow prevents another Project Setup inspection from being queued while an inspection request is already waiting to run.

Allow the current inspection to complete before starting another one.

---

## If a Status Changes After an Action

This is normally expected.

Project Setup frequently reinspects the affected area after a successful operation.

For example:

* enabling Worksharing changes the Worksharing and Workset state
* adopting a model role changes how Flow evaluates Worksets
* applying Existing Building phasing can change the Cleanup population
* creating Project Folders changes their availability state

The updated status reflects the resulting project or filesystem state rather than the state that existed before the action.

---

## Recommended Setup Sequence

For a newly created or unconfigured project:

1. Review **Project Identity**.
2. Select **Inspect Project**.
3. Review **Project Information**.
4. Inspect and create **Project Folders** where required.
5. Enable **Worksharing** where required.
6. Configure **Worksets**.
7. Complete **Existing Building** preparation where applicable.
8. Review the resulting **Setup Overview**.

The exact sequence can vary because not every project requires every setup operation.

---

## Related Help

* [Project Setup](index.md)
* [Project Identity](project-identity.md)
* [Creating a New Project](new-projects.md)
* [Project Information](project-information.md)
* [Project Folders](project-folders.md)
* [Worksharing](worksharing.md)
* [Worksets](worksets.md)
* [Existing Building](existing-building.md)
* [Project Setup Troubleshooting](troubleshooting.md)
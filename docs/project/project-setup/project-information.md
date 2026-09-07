# Project Information

**Project Information** reviews the configured project information fields in the active Revit project and allows required values to be prepared and written from Project Setup.

Flow separates the inspection of the existing Revit values from the changes you choose to apply.

The shared **Project Identity** can also provide proposed values for corresponding project information fields.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Project Information

Use **Project Information** when:

* setting up a newly created Revit project
* reviewing an existing project's information
* checking whether required project information fields have been completed
* applying project information based on the reviewed Project Identity
* correcting incomplete or inconsistent project information

---

## Before You Start

Open or activate the Revit project you want to review.

Where possible, complete and review the **Project Identity** first.

This gives Flow the shared project information that can be used when preparing corresponding Project Information values.

!!! info "Project Identity is separate"

	Reviewing Project Identity does not automatically overwrite Revit Project Information.

	Project Information changes remain part of this separate review and update workflow.

---

## Opening Project Information

### 1. Inspect the Project

Open:

**Flow → Project → Setup**

Select **Inspect Project**.

Flow inspects the Project Information stored in the active Revit project and updates its status in the Setup Overview.

### 2. Open the Review

Select **Review / Update** in the Project Information area.

Flow opens the Project Information review window.

<!-- Screenshot recommended:
Show the Project Information review window after it has been opened.
Include a useful mixture of existing values and proposed values so the relationship between the two is clear.
-->

---

## Reviewing Project Information

The review separates the value currently stored in Revit from the value proposed for the project.

Review each field before applying changes.

Where Project Identity provides corresponding information, Flow can use that shared information when preparing the proposed setup.

This allows the Project Identity to remain the common starting point without automatically changing the Revit project.

---

## Applying Changes

### 1. Review the Current Values

Check the values currently stored in the Revit project.

### 2. Review the Proposed Values

Check the values Flow proposes for the project.

Adjust the proposed information where required.

### 3. Apply the Changes

When the proposed values are correct, use the available update action to write them to the Revit project.

Flow performs the write as an explicit operation.

---

## Expected Result

After the required Project Information changes have been successfully applied:

* the selected Project Information values are written to the active Revit project
* the project contains the reviewed setup information
* the Project Information status can reflect the updated state when reinspected

The Project Identity remains available as shared Project Setup information.

---

## Read-Only Fields

Some Revit parameters may exist but cannot be modified in the current project context.

Flow identifies whether a configured Project Information field is available and whether it can be written.

A read-only field cannot be changed by the Project Information update workflow.

!!! info "Flow does not force read-only values"

	If Revit reports a parameter as read-only, Flow does not attempt to bypass that restriction.

---

## Missing Fields

A configured Project Information field may not exist in the active project.

Flow can identify that condition during inspection rather than assuming every expected field is available.

If a required field is missing, review the project configuration or template before attempting to complete the Project Information setup.

---

## Project Identity and Proposed Values

The reviewed Project Identity provides common project information including:

* Project Year
* Project Number
* Client
* Location

Where these values correspond with the configured Project Information setup, Flow can use them when preparing the review.

!!! important "Review before writing"

	Project Identity values are not automatically pushed into Revit simply because the identity has been reviewed.

	Review the proposed Project Information values before applying them.

---

## If Project Information Requires Attention

Open **Review / Update** and check:

* fields with missing values
* proposed values that differ from the current Revit values
* fields that are unavailable
* fields reported as read-only

Correct or apply the values that can be updated.

If the issue is caused by a missing or incorrectly configured project parameter, that underlying project configuration may need to be corrected separately.

---

## If Changes Cannot Be Applied

A Project Information change may be unavailable if:

* the parameter does not exist
* Revit reports the parameter as read-only
* the project is not in a state where the value can be written
* the requested update cannot be completed by Revit

Flow reports the result rather than treating an unsuccessful write as complete.

---

## Related Help

* [Project Setup](index.md)
* [Project Identity](project-identity.md)
* [Reviewing a Current Project](current-projects.md)
* [Creating a New Project](new-projects.md)
* [Project Setup Troubleshooting](troubleshooting.md)
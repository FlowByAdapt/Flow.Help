# Creating a New Project

**Project Setup** creates a new Revit project from an approved Project Profile and version-compatible Revit template.

You first review the **Project Identity**, select the appropriate **Project Profile**, and check the template resolved by Flow. Flow then creates and activates the new Revit project before you continue with the remaining setup.

A new project can be created even when no Revit document is currently open.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Creating a New Project

Use the **New Project** workflow when:

* starting a new Revit project
* the project should use an approved Flow Project Profile
* the correct template needs to be resolved for the current Revit version
* you want to begin the standard Project Setup workflow from a controlled template

---

## Before You Start

Have the following project information available:

* Project Year
* Project Number
* Client
* Location
* the appropriate Project Profile

The approved Revit template associated with the selected Project Profile must also be available.

!!! info "Project creation is the first stage"

	Creating the Revit project does not automatically create project folders, update all Project Information, enable worksharing or configure standard worksets.

	These stages are completed separately after the project has been created.

---

## Opening the Tool

Open:

**Flow → Project → Setup**

If no Project Identity has been reviewed, begin with the highlighted **Project Identity** card.

---

## Creating a New Project

### 1. Complete Project Identity

Enter:

* **Project Year**
* **Project Number**
* **Client**
* **Location**

Select **Review Identity**.

The identity must pass validation before a project can be created.

See [Project Identity](project-identity.md).

### 2. Select a Project Profile

In the **New Project** area, select the **Project Profile** that best matches the project.

Flow uses the selected profile to determine the approved Revit template for the current Revit version.

<!-- Screenshot recommended:
Show the New Project card with the Project Profile selector open.
Where practical, show several available profiles so the purpose of the selection is clear.
-->

### 3. Check the Resolved Template

After selecting a Project Profile, review the template information displayed by Flow.

The template must show as **Available** before the project can be created.

If the required template cannot be resolved or is unavailable, **Create Project** remains disabled.

!!! info "Template availability is checked again"

	Flow checks the physical template again when project creation is requested.

	If the template has become unavailable since the Project Profile was selected, Flow stops the creation workflow rather than using an unexpected template.

<!-- Screenshot recommended:
Show a reviewed Project Identity together with the New Project card.
The Project Profile should be selected, the resolved template should show Available and Create Project should be enabled.
-->

### 4. Select Create Project

When the Project Identity, Project Profile and template are ready, select **Create Project**.

Flow displays a confirmation before creating the project.

Review the information and confirm the operation.

### 5. Flow Creates the Project

Flow asks Revit to create a new project from the resolved approved template.

The project is initially created as a new unsaved Revit project.

Flow does not create project folders, worksets or a central model as part of this operation.

### 6. Flow Activates the New Project

After successful creation, Flow activates the new project in Revit.

Project Setup refreshes to the new Revit context and carries the creation identity forward into the refreshed window.

The new project can now be inspected and the remaining setup completed.

### 7. Inspect the New Project

Select **Inspect Project**.

Review the **Setup Overview** to determine what setup remains.

Typical next steps include:

* reviewing Project Information
* inspecting and creating Project Folders
* enabling Worksharing
* configuring standard Worksets

See [Reviewing a Current Project](current-projects.md).

---

## Expected Result

After successful project creation:

* a new Revit project has been created from the approved resolved template
* the new project is active in Revit
* Project Setup is working with the newly active project
* the Project Identity used during creation is carried forward
* the remaining Project Setup stages can be inspected and completed

The project is not considered fully configured simply because the Revit document has been created.

Use **Inspect Project** to determine what setup work remains.

---

## What Flow Creates Automatically

The **Create Project** operation creates the Revit project from the resolved template and activates the resulting document.

It does not automatically:

* create the project folders
* write all Project Information values
* enable worksharing
* configure the standard worksets
* create or save a central model
* perform Existing Building preparation

These remain separate Project Setup operations.

---

## If Create Project Is Disabled

### Project Identity Has Not Been Reviewed

Complete the Project Identity and select **Review Identity**.

### No Project Profile Is Selected

Select the appropriate Project Profile in the New Project card.

### The Template Is Not Available

Check the resolved template status.

The approved template for the selected Project Profile and current Revit version must be available before project creation can begin.

### Project Creation Is Not Available

Project Setup determines whether project creation is available in the current Revit context.

If creation is unavailable, the New Project card reports that a new project cannot currently be created.

---

## If the Template Becomes Unavailable

Flow checks the resolved template again immediately before project creation.

If the physical template can no longer be found, Flow stops the operation and reports that the template is unavailable.

No project is created from an alternative template.

---

## If the Project Cannot Be Created

If Revit cannot create the project, Flow reports the failure and does not treat the operation as successful.

Check:

* that the approved template remains accessible
* that the correct Project Profile is selected
* that the template is appropriate for the current Revit version
* any error information reported by Flow or Revit

Correct the issue and try again.

---

## Continuing Project Setup

After the new project has been created and activated, continue through the **Current Project** workflow.

A typical sequence is:

1. Select **Inspect Project**.
2. Review **Project Information**.
3. Inspect and create **Project Folders**.
4. Enable **Worksharing** where required.
5. Configure **Worksets**.
6. Complete **Existing Building** preparation where applicable.
7. Review the resulting **Setup Overview**.

Not every project requires every stage.

---

## Related Help

* [Project Setup](index.md)
* [Project Identity](project-identity.md)
* [Reviewing a Current Project](current-projects.md)
* [Project Information](project-information.md)
* [Project Folders](project-folders.md)
* [Worksharing](worksharing.md)
* [Worksets](worksets.md)
* [Project Setup Troubleshooting](troubleshooting.md)
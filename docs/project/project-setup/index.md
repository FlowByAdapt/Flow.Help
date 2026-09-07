# Project Setup

**Project Setup** provides a guided workflow for creating a new Revit project or reviewing and completing the setup of an existing project.

Flow brings the main project setup tasks together in one place, allowing you to establish the **Project Identity**, create a project from an approved template, inspect the current project and work through any setup items that are incomplete or require attention.

Project Setup can be opened with or without a Revit project already open.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Project Setup

Use **Project Setup** when:

* starting a new Revit project
* reviewing the setup of an existing project
* checking Project Information
* creating standard project folders
* enabling worksharing
* checking or configuring standard worksets
* preparing an Existing Building model

Project Setup is designed to be used throughout the initial setup process rather than as a single one-click operation.

---

## Opening the Tool

Open:

**Flow → Project → Setup**

If Project Setup is already open, Flow returns to the existing window and refreshes its Revit context rather than opening another copy.

When an active project is available, Flow positions the Project Setup window relative to the active Revit view.

If the **Project Identity** has not been reviewed, its card is highlighted and displays **Start here**.

<!-- Screenshot recommended:
Show the complete Project Setup window immediately after opening.
The Project Identity card should be highlighted with the Start here indicator visible.
Where practical, include both the New Project and Current Project areas so the overall structure of the tool is clear.
-->

---

## Start with Project Identity

Project Identity provides the common project information used by several Project Setup workflows.

Enter:

* **Project Year**
* **Project Number**
* **Client**
* **Location**

Then select **Review Identity**.

Flow validates the information before allowing it to be used by dependent setup operations.

!!! tip "Start here"

	Complete and review the Project Identity before working through the rest of Project Setup.

	If any identity value is changed later, Flow clears the previous review and the identity must be reviewed again.

See [Project Identity](project-identity.md).

---

## Creating a New Project

If you are starting a new project:

1. Complete and review the **Project Identity**.
2. Select the appropriate **Project Profile**.
3. Check the resolved Revit template.
4. Select **Create Project**.
5. Confirm the project creation.
6. Flow creates and activates the new Revit project.
7. Select **Inspect Project** to review the remaining setup.

Creating the Revit project is deliberately separate from the remaining setup operations.

Flow does not automatically create project folders, update all Project Information, enable worksharing or configure standard worksets simply because the project has been created.

See [Creating a New Project](new-projects.md).

---

## Reviewing a Current Project

With a Revit project active, select **Inspect Project**.

Flow inspects the main project setup areas and displays the results in the **Setup Overview**.

The overview includes:

* Project Information
* Project Folders
* Worksharing
* Worksets
* Existing Building

Each area displays its current status and a summary of what Flow found.

<!-- Screenshot recommended:
Show Project Setup immediately after Inspect Project has completed.
Use a project that produces a useful mixture of Complete, Ready and Attention Required states so the Setup Overview is easy to understand.
-->

See [Reviewing a Current Project](current-projects.md).

---

## Understanding Setup Statuses

Project Setup uses status indicators to show the current state of each setup area.

| Status | Meaning |
| --- | --- |
| **Complete** | The inspected setup currently meets the required condition. |
| **Ready** | The area is ready for the next setup action. |
| **Attention Required** | Flow found something that requires review or action. |
| **Not Inspected** | The area has not yet been inspected. |
| **Not Applicable** | The area does not currently require an action. |

The overall **Setup Overview** combines these results to help identify what should be done next.

---

## Continue Setup

Where an appropriate next action can be determined, **Continue Setup** provides a shortcut to that action.

Depending on the current project state, this can lead to actions such as:

* inspecting the project
* reviewing Project Information
* enabling worksharing
* configuring worksets
* inspecting project folders
* creating project folders

**Continue Setup** does not automatically perform every remaining setup operation.

Operations that change the project or create project resources remain explicit actions and may require confirmation.

---

## Refresh and Inspect Project

**Refresh** and **Inspect Project** perform different functions.

### Refresh

Use **Refresh** when the active Revit context or available Project Profile/template information may have changed.

Refresh updates Project Setup to the current Revit context.

It does not perform a new inspection of the project's setup.

### Inspect Project

Use **Inspect Project** when you want Flow to assess the active project's current setup.

The inspection results are then displayed in the Current Project area and Setup Overview.

!!! info "After changing the project"

	Many Project Setup actions automatically perform the appropriate follow-up inspection.

	If the project has been changed outside the workflow and you want to reassess its setup, use **Inspect Project**.

---

## Automatic Follow-Up Checks

Project Setup automatically refreshes relevant inspection results after several successful operations.

For example:

* enabling worksharing is followed by another project inspection
* configuring worksets is followed by another project inspection
* selecting an unresolved model role is followed by another project inspection
* creating project folders is followed by folder reinspection
* applying Existing Building phasing is followed by phasing reinspection and an automatic Cleanup refresh
* Existing Building cleanup is followed by cleanup reinspection

These checks allow the displayed status to reflect the resulting project state without requiring unnecessary repeated actions.

---

## Changes Are Deliberate

Opening or inspecting Project Setup does not automatically modify the Revit project.

Actions that make significant changes are started explicitly and, where appropriate, require confirmation.

These include:

* creating a new project
* creating project folders
* removing an incomplete project folder
* enabling worksharing
* configuring worksets
* applying Existing Building phasing
* cleaning up Existing Building content

This allows Project Setup to be used safely as an inspection tool before any changes are made.

---

## Recommended Workflow

For most projects:

1. Open **Project Setup**.
2. Complete the **Project Identity**.
3. Select **Review Identity**.
4. Create a new project, or activate the existing project.
5. Select **Inspect Project**.
6. Review the **Setup Overview**.
7. Review and update **Project Information** where required.
8. Inspect and create **Project Folders** where required.
9. Enable **Worksharing** where required.
10. Configure **Worksets**.
11. Complete **Existing Building** preparation where applicable.
12. Review the resulting Setup Overview.

Not every project requires every stage.

Flow reports the current project state rather than forcing setup operations that are not applicable.

---

## Related Help

* [Project Identity](project-identity.md)
* [Creating a New Project](new-projects.md)
* [Reviewing a Current Project](current-projects.md)
* [Project Information](project-information.md)
* [Project Folders](project-folders.md)
* [Worksharing](worksharing.md)
* [Worksets](worksets.md)
* [Existing Building](existing-building.md)
* [Project Setup Troubleshooting](troubleshooting.md)
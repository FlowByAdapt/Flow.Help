# Project Folders

**Project Folders** checks the configured project folder locations against the reviewed Project Identity and can create the required folder structure where it does not already exist.

Flow inspects each configured folder target before creating anything. Existing project folders, conflicts and incomplete previous provisioning attempts are identified separately so they can be reviewed before changes are made.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Project Folders

Use **Project Folders** when:

* setting up folders for a new project
* checking whether the required project folders already exist
* reviewing folder availability for an existing project
* creating the standard folder structure
* recovering from an incomplete previous folder creation attempt

Project folder planning depends on a reviewed **Project Identity**.

---

## Before You Start

Complete and review the Project Identity first.

Flow uses the reviewed project information when determining the required project folder locations.

The configured folder targets must also be accessible from the workstation running Flow.

!!! important "Review Project Identity first"

	If the Project Identity is changed after it has been reviewed, Flow clears the existing folder plan.

	Review the revised identity and inspect the project folders again before creating anything.

---

## Inspecting Project Folders

### 1. Review Project Identity

Enter and review:

* Project Year
* Project Number
* Client
* Location

See [Project Identity](project-identity.md).

### 2. Inspect the Folder Targets

Use the **Project Folders** area to inspect the configured folder targets.

Flow evaluates each selected target using the reviewed Project Identity.

### 3. Review the Results

Each target reports its current state and proposed folder location.

Depending on the existing filesystem, Flow can identify situations including:

* the project folder is available to create
* the exact project folder already exists
* the required year location is unavailable
* the required folder template is unavailable
* another folder conflicts with the project number
* an incomplete previous provisioning attempt has been detected

<!-- Screenshot recommended:
Show the Project Folders review with several target states.
Where practical, include one Available target and one existing or conflicting target so the status differences are clear.
-->

---

## Selecting Folder Targets

Project Setup can contain more than one configured folder target.

Review the available targets and select the locations that apply to the project.

Only selected targets are included when Flow prepares the folder creation operation.

!!! info "Targets are inspected independently"

	Each configured folder target has its own status and destination.

	A problem with one target does not mean that every configured target has the same problem.

---

## Creating Project Folders

### 1. Review the Folder Plan

Before creating folders, check:

* the reviewed Project Identity
* the selected folder targets
* the proposed folder paths
* the status of each selected target

### 2. Select Create Project Folders

Select **Create Project Folders**.

Flow displays a preview of the selected targets and their current status.

### 3. Confirm Folder Creation

Review the proposed locations and confirm the operation.

Only selected targets currently reported as **Available** are created.

!!! important "Existing folders are not recreated"

	Flow does not treat an existing project folder as an empty destination for a new provisioning operation.

	The target must be in an appropriate Available state before Flow creates the standard folder structure.

### 4. Flow Creates the Folder Structure

Flow creates the required project folder structure for each eligible selected target.

### 5. Flow Reinspects the Targets

After provisioning, Flow automatically reinspects the project-folder plan.

The resulting statuses are updated to reflect what now exists on the filesystem.

---

## Expected Result

After successful folder creation:

* the selected available project-folder targets have been created
* the configured standard folder structure is present
* Flow has reinspected the folder targets
* successfully created locations are recognised as existing project folders
* targets that were not eligible for creation remain unchanged

---

## Existing Project Folders

If the exact expected project folder already exists, Flow identifies it rather than attempting to create it again.

An exact existing folder can therefore be recognised as a completed target.

No folder creation is required for that location.

---

## Project Number Conflicts

Flow checks for existing folder conditions that conflict with the reviewed project identity.

For example, another folder may already use the same project number without matching the exact expected project folder.

Flow reports the conflict rather than automatically creating another folder.

!!! important "Resolve conflicts before provisioning"

	A project-number conflict should be investigated before creating or renaming folders manually.

	Confirm that the Project Identity is correct and determine which existing folder belongs to the project.

---

## Unavailable Folder Locations

A folder target may be unavailable if Flow cannot resolve or access part of the configured destination.

This can include situations where:

* the required project year location cannot be found
* the configured folder template is unavailable
* another required part of the folder target cannot be resolved

Flow reports the target as unavailable rather than attempting to create an incomplete project structure.

---

## Incomplete Folder Creation

If a previous Flow folder provisioning operation did not complete successfully, Project Setup can identify the incomplete target.

This allows the incomplete provisioning attempt to be removed before the folder creation is tried again.

<!-- Screenshot recommended:
Only include this if an incomplete provisioning state can be reproduced cleanly.
Show the affected target and the recovery action rather than the internal temporary folder structure.
-->

---

## Removing an Incomplete Project Folder

### 1. Review the Incomplete Target

Confirm that the target represents an incomplete Flow provisioning attempt.

### 2. Select Remove Incomplete Project Folder

Flow displays a confirmation before removing the incomplete folder.

### 3. Confirm the Removal

Confirm only when the incomplete target should be permanently removed.

!!! warning "The folder and its contents are deleted"

	Removing an incomplete project folder permanently deletes that folder and everything currently contained within it.

	Review the location carefully before confirming the operation.

### 4. Flow Reinspects the Target

After removal, Flow reinspects the affected folder target.

If the destination is now available for a new provisioning attempt, its status updates accordingly.

---

## If Create Project Folders Is Unavailable

### Project Identity Has Not Been Reviewed

Complete the Project Identity and select **Review Identity**.

### No Folder Targets Are Selected

Select the configured folder targets that apply to the project.

### The Target Is Not Available

Review the status reported for the target.

Existing folders, conflicts, unavailable locations and incomplete provisioning states are handled separately and are not treated as normal folder-creation targets.

---

## If Folder Creation Does Not Complete

Flow reports the provisioning result and then reinspects the folder targets.

If an incomplete provisioning state remains, review the affected target before attempting the operation again.

Do not assume that a partially created folder structure represents a successfully completed project folder.

---

## Related Help

* [Project Setup](index.md)
* [Project Identity](project-identity.md)
* [Creating a New Project](new-projects.md)
* [Reviewing a Current Project](current-projects.md)
* [Project Setup Troubleshooting](troubleshooting.md)
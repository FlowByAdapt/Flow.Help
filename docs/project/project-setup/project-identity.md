# Project Identity

**Project Identity** defines the core information Flow uses to identify the project throughout Project Setup.

You enter the project year, project number, client and location, then ask Flow to review the identity before using it for dependent workflows such as project creation and project folder planning.

**Ribbon:** **Flow → Project → Setup**

---

## When to Use Project Identity

Complete the **Project Identity** when:

* starting a new Revit project
* setting up an existing project
* preparing to inspect or create standard project folders
* the project's identifying information has changed

Project Identity should normally be the first step when using Project Setup.

---

## Before You Start

Have the following information available:

* **Project Year**
* **Project Number**
* **Client**
* **Location**

Project Year is initially populated with the current year.

!!! info "Project Identity and Project Information"

	Project Identity is Flow's shared project setup information.

	It is related to, but separate from, the **Project Information** parameters stored inside the Revit project.

	Reviewing the Project Identity does not by itself write Revit Project Information parameters.

---

## Opening Project Setup

Open:

**Flow → Project → Setup**

If the Project Identity has not yet been reviewed, Flow highlights the card and displays **Start here**.

<!-- Screenshot recommended:
Show the Project Identity card in its initial state.
Include all four fields, the Review Identity button, the accent border and Start here indicator.
-->

---

## Reviewing Project Identity

### 1. Enter the Project Year

Enter the **Project Year**.

Flow initially uses the current year, but this can be changed where the project belongs to a different project year.

### 2. Enter the Project Number

Enter the **Project Number** used to identify the project.

### 3. Enter the Client

Enter the **Client** name.

### 4. Enter the Location

Enter the project **Location**.

### 5. Review the Identity

Check the four values and select **Review Identity**.

Flow validates the entered information.

If the identity is valid, it becomes the reviewed Project Identity and workflows that depend on it can become available.

The **Start here** indicator is removed after a successful review.

---

## Expected Result

After Project Identity has been successfully reviewed:

* Flow recognises the identity as valid
* the **Start here** indicator is removed
* project creation can become available when a valid Project Profile and template are also selected
* project folder targets can be prepared for inspection
* the reviewed values can be used by subsequent Project Setup workflows

Reviewing the identity does not create project folders or automatically modify Revit Project Information.

---

## Changing a Reviewed Identity

If you change any Project Identity value after it has been reviewed, Flow clears the previous review.

This applies to:

* Project Year
* Project Number
* Client
* Location

The **Start here** indicator returns and the revised identity must be reviewed again.

!!! important "Review changes before continuing"

	Changing a reviewed Project Identity also clears the existing project-folder plan.

	Select **Review Identity** again and reinspect the proposed project folders before creating folders using the revised information.

---

## If the Identity Cannot Be Reviewed

If the entered information does not pass validation, Flow does not accept the identity as reviewed.

Check the values shown in the Project Identity card, correct the relevant information and select **Review Identity** again.

Actions that require a reviewed identity remain unavailable until the review succeeds.

---

## Project Identity and New Projects

A reviewed Project Identity is required before **Create Project** can become available.

Project creation also requires:

* a selected Project Profile
* an approved template resolved for the current Revit version
* the resolved template to be available

See [Creating a New Project](new-projects.md).

---

## Project Identity and Project Folders

Project folder planning uses the reviewed Project Identity.

After a successful identity review, Flow prepares the configured project-folder targets so they can be inspected.

If the identity is subsequently changed, the previous folder plan is cleared to prevent folders being created from outdated project information.

See [Project Folders](project-folders.md).

---

## Related Help

* [Project Setup](index.md)
* [Creating a New Project](new-projects.md)
* [Project Information](project-information.md)
* [Project Folders](project-folders.md)
* [Project Setup Troubleshooting](troubleshooting.md)
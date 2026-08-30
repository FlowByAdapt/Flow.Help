# Creating a New Project

Project Setup provides a guided workflow for creating a new Revit
project using the appropriate Flow project standards.

New-project creation can be started without an existing Revit project
open.

------------------------------------------------------------------------

## Before You Begin

Open:

**Flow → Project → Setup**

Begin with **Project Identity**.

------------------------------------------------------------------------

## 1. Review Project Identity

Enter **Project Year**, **Project Number**, **Client** and **Location**,
then select **Review Identity**.

The identity must be valid before **Create Project** becomes available.

If an identity value is edited after review, Project Setup clears the
review and requires the revised identity to be reviewed again.

➡️ **[Project Identity →](project-identity.md)**

------------------------------------------------------------------------

## 2. Select a Project Profile

Select the Project Profile that best matches the project being created.

Project Profiles allow Flow to determine the appropriate project
configuration and Revit template.

Profiles can represent differences such as project type, work type,
client requirements, documentation requirements and project role or
starting configuration.

!!! tip "Choose the profile, not the template"

    Select the Project Profile that describes the project. Flow uses that profile to resolve the approved Revit template.

------------------------------------------------------------------------

## 3. Review the Resolved Revit Template

Flow uses the selected Project Profile and current Revit version to
resolve the appropriate office-approved template.

Project Setup reports whether that template is available.

!!! note "Revit version"

    Project Setup resolves the template for the version of Revit currently running.

    Do not substitute an unrelated template if the expected template is unavailable.

------------------------------------------------------------------------

## 4. Create the Project

**Create Project** becomes available only when the required creation
state is valid:

-   a valid reviewed Project Identity;
-   a selected Project Profile;
-   a successful template preflight; and
-   an available compatible template.

Select **Create Project** to begin project creation.

------------------------------------------------------------------------

## After Creating the Project

Project Setup can then inspect and complete the remaining
current-project setup areas, including Project Information, Project
Folders, Worksharing, Worksets and Existing Building preparation where
applicable.

➡️ **[Reviewing a Current Project →](current-projects.md)**

------------------------------------------------------------------------

## Related Help

-   [Project Setup](index.md)
-   [Project Identity](project-identity.md)
-   [Reviewing a Current Project](current-projects.md)
-   [Project Information](project-information.md)
-   [Project Folders](project-folders.md)
-   [Troubleshooting](troubleshooting.md)

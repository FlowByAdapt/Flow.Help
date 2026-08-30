# Project Setup

Project Setup provides a guided workflow for creating new Revit projects
and reviewing or completing the setup of existing projects.

It brings project configuration tasks together into one coordinated
workflow so that office standards can be applied consistently.

------------------------------------------------------------------------

## Opening Project Setup

On the Revit ribbon, go to:

**Flow → Project → Setup**

Project Setup can be opened with no project document active when you
want to create a new project. Current-project inspection and
configuration actions require an active Revit project.

------------------------------------------------------------------------

## Start with Project Identity

The **Project Identity** card is the starting point for Project Setup.

Enter the shared project details and select **Review Identity** before
continuing with workflows that depend on this information.

Project Identity includes:

-   **Project Year**
-   **Project Number**
-   **Client**
-   **Location**

When the identity still requires review, the card is highlighted and
displays **Start here**.

Once the identity has been reviewed successfully, the highlight is
removed. If an identity value is changed later, the previous review is
cleared and the card is highlighted again.

➡️ **[Project Identity →](project-identity.md)**

------------------------------------------------------------------------

## What do you want to do?

### 🆕 Create a New Project

Create a project using a reviewed Project Identity, an approved Flow
Project Profile and the correct template for the current version of
Revit.

[Creating a New Project →](new-projects.md)

### 🔍 Review a Current Project

Inspect an active Revit project and identify setup areas that are
complete, ready, not yet inspected or require attention.

[Reviewing a Current Project →](current-projects.md)

!!! info "Inspection is read-only"

    Project inspection reports the current setup state.

    Changes are only made when you deliberately choose the relevant setup action.

------------------------------------------------------------------------

## Setup Statuses

  -----------------------------------------------------------------------
  Status                              Meaning
  ----------------------------------- -----------------------------------
  **Complete**                        The inspected setup area currently
                                      satisfies the expected state.

  **Ready**                           The area has been inspected and an
                                      available setup action can complete
                                      it.

  **Attention Required**              The inspection found something that
                                      should be reviewed.

  **Not Inspected**                   The area has not yet been
                                      inspected.

  **Not Applicable**                  The area does not apply in the
                                      current context.

  **Failed**                          The inspection could not be
                                      completed successfully.
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## Setup Areas

  -----------------------------------------------------------------------
  Setup area                          What it controls
  ----------------------------------- -----------------------------------
  **Project Identity**                Shared project year, number, client
                                      and location used by other setup
                                      workflows

  **Templates / Profiles**            Resolves the approved starting
                                      configuration for a new project

  **Project Information**             Reviews and updates project
                                      metadata stored in the active Revit
                                      project

  **Project Folders**                 Checks and provisions configured
                                      project folder locations

  **Worksharing**                     Checks whether the active project
                                      is workshared and can enable
                                      worksharing when required

  **Worksets**                        Checks and creates the required
                                      office-standard worksets

  **Existing Building**               Reviews cleanup targets and
                                      Existing Building phasing
  -----------------------------------------------------------------------

### Detailed Help

-   [Project Identity →](project-identity.md)
-   [Creating a New Project →](new-projects.md)
-   [Reviewing a Current Project →](current-projects.md)
-   [Project Information →](project-information.md)
-   [Project Folders →](project-folders.md)
-   [Worksharing →](worksharing.md)
-   [Worksets →](worksets.md)
-   [Existing Building →](existing-building.md)

------------------------------------------------------------------------

## Refreshing Project Setup

Use **Refresh** when the active Revit context or associated project
resources have changed outside Project Setup.

Individual workflows may also re-inspect their own state after an action
is completed.

------------------------------------------------------------------------

## Need Help?

See [Project Setup Troubleshooting →](troubleshooting.md).

Press **F1** while hovering over **Setup** on the Flow ribbon to return
directly to this page.

# Keynote Manager

The **Keynote Manager** provides a central interface for creating,
organising and maintaining Revit keynote files and coordinating keynote
references in the current project.

Use it to browse and search the keynote hierarchy, review placed keynote
usage, add and edit keynote entries, use approved keynote descriptions,
manage project keynote files, renumber categories and synchronise
changed keynote codes back into Revit.

------------------------------------------------------------------------

## Open Keynote Manager

On the Revit ribbon:

**Flow → Model → Keynotes**

Keynote Manager opens as a dockable Flow panel and can remain available
while you work in Revit.

When the panel opens, Flow checks the active Revit project for its
currently assigned keynote file. If that `.txt` file is available, it is
opened automatically.

<!-- SCREENSHOT: Keynote Manager overview.
Show the complete dockable panel with File, search, User/Material/Element buttons, an expanded category, green usage indicators/counts, file/project status and Save/Renumber/Sync/Refresh visible. -->

------------------------------------------------------------------------

## First-Time Workflow

A typical project workflow is:

1.  Open **Keynote Manager**.
2.  Check the loaded filename and project keynote status.
3.  Browse or search for the required keynote.
4.  Select a category or keynote and make the required change.
5.  Use the **Library** when you want to insert an approved keynote
    description.
6.  **Save** the keynote file.
7.  Use **Refresh** when Revit needs to reload the keynote table.
8.  Use **Sync** when keynote codes have changed and existing Revit
    references need to follow the new codes.

!!! tip "Save, Refresh and Sync do different jobs"

    **Save** writes changes to the keynote `.txt` file.

    **Refresh** reloads the file and tells Revit to reload its keynote table.

    **Sync** updates existing Revit references after keynote codes have changed.

------------------------------------------------------------------------

## What Do You Want to Do?

### Work with Keynotes

Browse and search the keynote hierarchy, review placed keynote usage,
add categories and keynotes, use the approved-description Library, edit
or move keynotes, remove entries, clean categories and reorganise
numbering.

➡️ [**Working with Keynotes**](working-with-keynotes.md)

### Work with Project Keynote Files

Create, open and save Revit keynote files, assign the loaded file to the
current project, refresh Revit's keynote table and synchronise changed
keynote references.

➡️ [**Project Keynote Files**](project-keynote-files.md)

### Resolve a Problem

Use the troubleshooting checks when the expected file does not open, a
keynote cannot be found, changes cannot be saved, Revit does not show
updated keynote information or Sync is unavailable.

➡️ [**Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Main Areas

-   **File** --- create, open, save and manage keynote files, access
    recent files and category maintenance.
-   **Search** --- find keynotes by code or description.
-   **User / Material / Element** --- start Revit's native User,
    Material or Element keynote placement command.
-   **Edit / Add / Remove** --- maintain the selected category or
    keynote.
-   **Keynote tree** --- browse categories and keynote entries.
-   **Usage indicator** --- shows how many placed Revit keynote tags
    currently use a keynote code.
-   **File status** --- shows the loaded file and whether it is the
    current project's keynote file.
-   **Save / Renumber / Sync / Refresh** --- save file changes,
    reorganise codes, update existing Revit references and reload
    Revit's keynote table.

------------------------------------------------------------------------

## Place Revit Keynotes

The **User**, **Material** and **Element** buttons start the
corresponding native Revit keynote commands.

Use these when you want to place keynote tags in the active Revit
project while keeping Keynote Manager available for reference.

These commands use Revit's native keynote system and the keynote file
assigned to the project.

------------------------------------------------------------------------

## Keynote Usage

A green usage indicator identifies keynote codes that are currently used
by placed **keynote tags** in the active Revit project.

The number shown is the count of placed keynote tags using that code.

Usage counts do not include elements or types that only have a keynote
parameter assigned.

Usage information is refreshed when Flow loads or refreshes the keynote
information and after a successful Sync.

------------------------------------------------------------------------

## Keynote Manager and Revit

Keynote Manager works with standard Revit keynote `.txt` files.

For new project files, Flow builds the initial keynote hierarchy from
its deployed office-standard keynote catalogue and writes the result as
a Revit-compatible text file.

Revit remains the host of the project keynote system. Flow provides
additional tools for creating, editing, organising and maintaining the
keynote file and for coordinating changed keynote codes with existing
project references.

------------------------------------------------------------------------

## Getting Help

Hover over **Keynotes** on the Flow ribbon and press **F1** to return
directly to this page.

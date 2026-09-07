# Project Keynote Files

Use **Keynote Manager** to create, open and maintain Revit keynote text
files and control which keynote file is associated with the active Revit
project.

------------------------------------------------------------------------

## Current Project Keynote File

When Keynote Manager opens, Flow checks the active Revit project's
native keynote table for its assigned external keynote file.

If the referenced `.txt` file exists and is accessible, Flow opens it
automatically.

The panel displays the loaded filename together with its project status,
including whether it is the:

``` text
Current project keynote file
```

or is:

``` text
Not assigned to this project
```

!!! info "The referenced file must be available"

    If Revit references a keynote file that cannot be resolved or does not exist at the expected location, Flow cannot automatically open that file.

------------------------------------------------------------------------

## Create a New Project Keynote File

Use **File → New...** when the project needs a new keynote file.

Flow uses the Revit **Project Number** to suggest an appropriate
filename and project location.

For example, a project with Project Number:

``` text
26123
```

is offered:

``` text
26123_Keynotes.txt
```

Flow looks for the matching project folder and uses its **Keynotes**
folder when one exists. If no Keynotes folder exists, it uses the
project folder. If the project cannot be resolved, Flow falls back to
its configured documents location.

If no Project Number is available, the suggested filename is:

``` text
Project_Keynotes.txt
```

To create the file:

1.  Open **File**.
2.  Choose **New...**.
3.  Review the suggested location and filename.
4.  Change either if required.
5.  Save the file.

Flow creates the initial hierarchy from its deployed office-standard
keynote catalogue and writes it as a standard Revit-compatible `.txt`
keynote file.

The new file then opens in Keynote Manager.

<!-- SCREENSHOT: New keynote Save dialog.
Capture a real project showing the project-aware Keynotes folder and project-number filename. -->

!!! info "New does not create a blank file"

    The office-standard keynote structure is supplied automatically. Users work with the resulting Revit `.txt` file; the underlying Flow catalogue does not need to be selected manually.

------------------------------------------------------------------------

## Open a Keynote File

To work with another existing keynote file:

1.  Open **File**.
2.  Choose **Open...**.
3.  Browse to the required `.txt` file.
4.  Open it.

Opening a file in Keynote Manager does **not** automatically assign it
to the Revit project.

------------------------------------------------------------------------

## Open a Recent File

Use **File → Open Recent** to reopen a recently used keynote file.

If the recent file has been moved, renamed or deleted, Flow reports that
it cannot be found. Use **Open...** to browse to its current location.

------------------------------------------------------------------------

## Set as Project Keynote File

Use **File → Set as Project Keynote File** when the loaded file should
become the keynote source for the active Revit project.

Opening a file and assigning it to Revit are deliberately separate
actions. This allows you to inspect or edit another keynote file without
immediately changing the project's keynote source.

After assignment, check that the status shows:

``` text
Current project keynote file
```

------------------------------------------------------------------------

## Save

Use **Save** to write unsaved Keynote Manager changes to the currently
loaded `.txt` file.

Saving updates the file on disk. It does not by itself perform the
separate **Refresh** or **Sync** operations.

------------------------------------------------------------------------

## Save As

Use **File → Save As...** to write the current keynote hierarchy to
another `.txt` file.

The newly saved file becomes the file currently loaded in Keynote
Manager.

It is not automatically assigned as the Revit project's keynote file.
Use **Set as Project Keynote File** if that is also required.

------------------------------------------------------------------------

## Save, Refresh and Sync

These commands perform different jobs:

  -----------------------------------------------------------------------
  Command                 What it does            Use it when
  ----------------------- ----------------------- -----------------------
  **Save**                Writes Keynote Manager  You have added, edited,
                          changes to the `.txt`   removed, cleaned or
                          file.                   renumbered keynote
                                                  information.

  **Refresh**             Reloads the current     The file changed
                          file and tells Revit to externally or Revit
                          reload its native       needs to read the
                          keynote table.          latest saved keynote
                                                  information.

  **Sync**                Updates existing Revit  A keynote code has
                          references that still   changed and existing
                          use recorded old        project references need
                          keynote codes.          to follow the new code.
  -----------------------------------------------------------------------

!!! important "Changing a description does not normally require Sync"

    Sync is concerned with recorded **code changes**. Editing only a keynote description does not create an old-to-new code mapping.

------------------------------------------------------------------------

## Refresh Keynotes

Use **Refresh** when Keynote Manager and Revit need to reload the
current keynote information.

Refresh:

1.  reloads the current `.txt` file into Keynote Manager
2.  tells Revit to reload its native keynote table
3.  refreshes placed-keynote-tag usage information after a successful
    reload

Refresh is unavailable while Keynote Manager contains unsaved changes.

If you have unsaved work, save it before refreshing.

------------------------------------------------------------------------

## Synchronise Changed Keynote References

Changing a keynote code in the file does not automatically update every
existing Revit reference that uses the previous code.

Flow records relevant old-to-new code changes created while editing or
renumbering keynotes. After those changes have been saved, **Sync** can
scan the active Revit project for matching references.

Sync checks:

-   placed keynote tags
-   instance keynote parameters
-   type keynote parameters

### Preview the Changes

Click **Sync** to build a preview.

The preview identifies references whose current code matches one of the
recorded old codes and shows the proposed replacement.

Review the preview before applying it.

<!-- SCREENSHOT: Sync Preview.
Show a mixture of affected references where practical, with old and new codes visible. -->

### Apply the Changes

When you confirm the preview, Flow updates writable matching references
inside the active Revit project.

Before changing each reference, Flow checks that:

-   the referenced Revit element still exists
-   the relevant keynote parameter exists
-   the parameter is not read-only
-   the current value still matches the old code shown in the preview

This prevents Flow from blindly replacing a value that has changed since
the preview was created.

After a successful Sync, the pending code-change mapping is cleared and
placed-keynote-tag usage is refreshed.

!!! warning "Sync modifies the Revit project"

    Review the Sync Preview before applying the changes.

------------------------------------------------------------------------

## Recommended Code-Change Workflow

When a keynote code changes:

1.  Make the edit or complete the category **Renumber** operation.
2.  Review any renumber preview.
3.  **Save** the keynote file.
4.  Click **Sync**.
5.  Review the Sync Preview.
6.  Apply the synchronisation.
7.  Use **Refresh** when Revit also needs to reload the latest keynote
    table.

This keeps the keynote file and existing Revit references coordinated.

------------------------------------------------------------------------

## Show in Explorer

Use **File → Show in Explorer** to open the containing folder and select
the currently loaded keynote file.

------------------------------------------------------------------------

## Close the Current File

Use **File → Close** to unload the currently displayed keynote file from
Keynote Manager.

Closing the file does not remove or change the keynote file already
assigned to the Revit project.

If unsaved changes exist, Flow prompts before discarding them.

------------------------------------------------------------------------

## Related Help

-   [Keynote Manager](index.md)
-   [Working with Keynotes](working-with-keynotes.md)
-   [Troubleshooting](troubleshooting.md)

# Project Keynote Files

Use **Keynote Manager** to open, create and maintain Revit keynote files and control which keynote file is associated with the current Revit project.

---

## Open Keynote Manager

On the Revit ribbon:

**Flow → Model → Keynotes**

---

## Current Project Keynote File

When Keynote Manager opens, it checks the active Revit project for its currently assigned keynote file.

If a project keynote file is assigned and available, Keynote Manager automatically opens it.

The loaded filename is displayed in Keynote Manager together with its project status.

A loaded file can be identified as either:

```text
Current project keynote file
```

or:

```text
Not assigned to this project
```

!!! info "Keynote Manager follows the Revit project"

	When an existing project already has a keynote file assigned through Revit, Keynote Manager uses that file rather than requiring it to be selected manually.

---

## Open a Keynote File

To work with another existing keynote file:

1. Open the **File** menu.
2. Choose **Open**.
3. Browse to the required `.txt` keynote file.
4. Open the file.

The selected file becomes the file currently displayed in Keynote Manager.

Opening a keynote file does not automatically assign it to the Revit project.

---

## Open a Recent Keynote File

Keynote Manager maintains a list of recently opened keynote files.

Use the recent-files list to reopen a previously used file without browsing to it again.

If a recent file has subsequently been moved, renamed or deleted, Keynote Manager reports that the file cannot be found.

---

## Create a New Project Keynote File

Use **New** to create a new Revit keynote file.

To create a file:

1. Open the **File** menu.
2. Choose **New**.
3. Select the required location.
4. Enter the filename.
5. Save the file.

The default filename is:

```text
Project_Keynotes.txt
```

Flow creates the new `.txt` file from the configured Flow keynote template and opens the resulting file in Keynote Manager.

!!! info "New files use the Flow keynote template"

	Creating a new keynote file does not start with an empty text document. Flow creates the project keynote file from its configured keynote template so that the standard keynote structure is available from the beginning.

---

## Assign a Keynote File to the Current Project

Opening a keynote file in Keynote Manager and assigning it to Revit are separate operations.

If the loaded file is not currently assigned to the project, use **Set Project Keynote File**.

Flow then requests that Revit use the loaded `.txt` file as the project's keynote file.

The status in Keynote Manager updates to:

```text
Current project keynote file
```

!!! info "Use this when changing project keynote files"

	Opening another keynote file allows you to review or edit it without immediately changing the Revit project.

	Use **Set Project Keynote File** only when the loaded file should become the keynote source for the current project.

---

## Save Changes

Use **Save** to write changes made in Keynote Manager back to the currently loaded keynote file.

Save is available when the loaded keynote information contains unsaved changes.

The status area indicates when unsaved changes are present.

!!! note "Saving and refreshing are separate operations"

	**Save** writes the changed keynote information to the `.txt` file.

	Use **Refresh** when Revit also needs to reload the keynote table from that file.

---

## Save As

Use **Save As** to write the currently loaded keynote information to another `.txt` file.

To create a copy:

1. Open the **File** menu.
2. Choose **Save As**.
3. Select the destination.
4. Enter the required filename.
5. Save the file.

The newly saved file becomes the file currently loaded in Keynote Manager.

Saving a file under another name does not by itself make that file the current project's Revit keynote file.

Use **Set Project Keynote File** if the new file should also be assigned to the project.

---

## Show the Keynote File in Explorer

Use **Show in Explorer** to locate the currently loaded keynote file in Windows Explorer.

Flow opens the containing folder and selects the keynote file.

This can be useful when you need to copy, inspect or locate the physical `.txt` file.

---

## Close the Current Keynote File

Use **Close** to unload the currently displayed keynote file from Keynote Manager.

Closing the file does not remove or change the keynote file assigned to the Revit project.

If unsaved changes exist, Keynote Manager asks whether they should be discarded before closing.

---

## Refresh Keynotes

Use **Refresh** when the keynote file needs to be reloaded.

Refresh:

1. Reloads the current `.txt` file into Keynote Manager.
2. Requests that Revit reload its keynote table.
3. Refreshes keynote usage information after the reload succeeds.

Refresh is only available when there are no unsaved changes in Keynote Manager.

!!! tip "Use Refresh after changing the keynote file"

	If the keynote file has been changed externally, or saved changes are not yet reflected by Revit, use **Refresh** to reload the current keynote information.

---

## Synchronise Changed Keynote References

Changing a keynote code in the keynote file does not necessarily change existing references to the previous code in the Revit project.

When Keynote Manager has recorded keynote renumbering changes, **Sync** can review affected project references and update them to the new keynote codes.

For example:

```text
Old keynote     New keynote

45-03        →  45-02
45-07        →  45-03
```

### Preview the Changes

Before modifying the project, Sync scans for affected keynote references and displays a preview.

The scan checks relevant:

* keynote tags
* element keynote parameters
* type keynote parameters

Review the proposed changes before continuing.

### Apply the Changes

If the preview is correct, confirm the synchronisation.

Flow updates the affected references using the old-to-new keynote mapping recorded during the renumbering operation.

After a successful synchronisation, the pending Sync changes are cleared and keynote usage information is refreshed.

!!! warning "Review the Sync preview"

	Synchronisation modifies references in the active Revit project.

	Review the proposed changes before applying them.

---

## Recommended Renumbering Workflow

When reorganising keynote numbering, use the following sequence:

1. Open the required project keynote file.
2. Select the category that needs reorganising.
3. Use **Renumber**.
4. Review and confirm the proposed keynote changes.
5. **Save** the keynote file.
6. Use **Sync** to find references using the previous keynote codes.
7. Review the Sync preview.
8. Apply the synchronisation.
9. Use **Refresh** if required to reload the keynote table in Revit.

This keeps the keynote file and existing Revit references coordinated when keynote codes are changed.

---

## Related Help

* [Keynote Manager](index.md)
* [Working with Keynotes](working-with-keynotes.md)
* [Troubleshooting](troubleshooting.md)

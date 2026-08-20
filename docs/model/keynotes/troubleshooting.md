# Keynote Manager Troubleshooting

Use the following checks if Keynote Manager cannot access the expected keynote file, a keynote cannot be found, changes cannot be saved or updated keynote information is not reflected correctly in Revit.

---

## The Project Keynote File Does Not Open Automatically

When Keynote Manager opens, it checks the active Revit project for its currently assigned keynote file.

If no file opens:

1. Check that the project has a keynote file assigned in Revit.
2. Confirm that the assigned `.txt` file still exists.
3. Confirm that the file location is accessible from the current workstation.
4. If necessary, use **Open** in Keynote Manager to browse to the required file.

!!! info "Opening and assigning are separate"

	Opening a keynote file in Keynote Manager does not automatically make it the current project's Revit keynote file.

	If the correct file is open but its status shows **Not assigned to this project**, use **Set Project Keynote File**.

---

## The Wrong Keynote File Is Open

The filename of the currently loaded keynote file is displayed in Keynote Manager.

The project status indicates whether it is:

**Current project keynote file**

or:

**Not assigned to this project**

If the wrong file is open:

1. Use **Open** to select the correct keynote file.
2. Confirm that the expected keynote hierarchy is displayed.
3. If the file should also be used by Revit, choose **Set Project Keynote File**.

---

## A Recent Keynote File Cannot Be Found

If you select a recent keynote file that has been moved, renamed or deleted, Keynote Manager reports that the file cannot be found.

Use **Open** to browse to its new location if the file still exists.

---

## I Can't Find a Keynote

If an expected keynote does not appear:

1. Press **Esc** to clear the current search.
2. Check the **Used** and **Unused** filters.
3. Expand the appropriate keynote category.
4. Search using part of the keynote code or description.
5. Confirm that Keynote Manager has the expected keynote file loaded.

!!! tip "Check the filters"

	A keynote can be present in the file but hidden from the current view if the Used or Unused filter excludes it.

---

## Search Does Not Show the Expected Result

Search checks the keynote **code** and **description**.

If a keynote is not returned:

1. Enter a shorter part of the code or description.
2. Check the Used and Unused filters.
3. Press **Esc** and browse the category directly.
4. Confirm that the keynote exists in the loaded file.

---

## I Can't Add a Keynote

Before adding a keynote, select the category that should contain it.

Then choose:

**Add → Add Keynote**

If the keynote cannot be added, check that:

* a valid category has been selected
* the keynote code is not blank
* the description is not blank
* the proposed keynote code does not already exist

Keynote codes must be unique within the loaded keynote file.

---

## The Suggested Keynote Number Is Not What I Expected

When adding a keynote, Flow looks for the next available numbered code within the selected category.

For example:

```text
45-01
45-02
45-04
```

will suggest:

```text
45-03
```

The suggested code can be changed before the keynote is added.

---

## I Can't Multi-select Keynotes

Multiple keynote selection is limited to entries within the same category.

Hold **Ctrl** while selecting the required keynote entries.

If you select an item from another category, Keynote Manager returns to a single selection rather than maintaining a selection across different categories.

---

## Removing a Keynote Did Not Renumber the Category

This is expected.

**Remove** deletes the selected keynote but does not change the codes of the remaining entries.

For example:

```text
45-01
45-02
45-03
```

after removing `45-02` becomes:

```text
45-01
45-03
```

Use **Renumber** separately if the remaining keynotes should be consecutively numbered.

---

## Cleaning a Category Did Not Renumber It

This is also expected.

**Clean Category** removes empty keynote entries only.

It deliberately leaves the numbering of the remaining keynotes unchanged.

Use **Renumber** if the category should also be consecutively numbered.

---

## Renumber Reports That the Category Is Already Consecutively Numbered

If the selected category already follows consecutive numbering, Keynote Manager does not make unnecessary changes.

No further action is required.

---

## Renumber Finds Empty Keynotes

If empty entries exist in the selected category, Keynote Manager asks how you want to continue.

Choose:

**Clean & Renumber**

to remove the empty entries before renumbering,

or:

**Renumber Only**

to retain the entries and continue with the renumbering operation.

---

## Changes Cannot Be Saved

If **Save** is not available, check whether Keynote Manager currently contains any unsaved changes.

If changes exist but the file cannot be written:

1. Confirm that the keynote `.txt` file still exists.
2. Confirm that its location is accessible.
3. Confirm that you have permission to modify the file.
4. Check whether the file has been made read-only or is otherwise unavailable.

You can also use **Save As** to save the keynote information to another location.

---

## Refresh Is Not Available

**Refresh** is disabled while Keynote Manager contains unsaved changes.

Either:

* use **Save** to keep the changes, or
* discard the changes when leaving the current file.

Refresh can then reload the keynote file and request that Revit reload its keynote table.

---

## Revit Does Not Show a Newly Added or Edited Keynote

Saving changes updates the keynote `.txt` file.

If Revit is still showing the previous keynote information:

1. Save the changes in Keynote Manager.
2. Use **Refresh**.
3. Allow Flow to request that Revit reload the keynote table.
4. Check the keynote again.

!!! note "Save and Refresh perform different tasks"

	**Save** writes changes to the keynote file.

	**Refresh** reloads the file and requests that Revit reload its keynote table.

---

## Revit Still Uses an Old Keynote Code After Renumbering

Renumbering changes the keynote codes in the keynote file, but existing Revit references may still point to the previous codes.

Use the following workflow:

1. Complete the **Renumber** operation.
2. Review and confirm the proposed changes.
3. **Save** the keynote file.
4. Use **Sync**.
5. Review the affected project references.
6. Confirm the synchronisation.

Sync can identify affected keynote tags and element or type keynote parameters associated with the recorded old-to-new keynote mapping.

!!! warning "Do not assume renumbering updates the model"

	Changing the keynote file and changing existing Revit references are separate operations.

	Use **Sync** when existing project references need to follow a keynote code that has been changed.

---

## Sync Is Not Available

Sync requires a pending set of keynote code changes.

These changes are normally created when a category is renumbered and one or more keynote codes actually change.

Sync is also unavailable while there are unsaved changes in Keynote Manager.

If you have just renumbered a category:

1. Review the renumber changes.
2. Save the keynote file.
3. Check **Sync** again.

---

## Sync Reports No References Require Updating

This means the Sync scan did not find project references matching the pending old keynote codes.

The affected codes may not currently be used by:

* keynote tags
* element keynote parameters
* type keynote parameters

No project changes are required in that case.

---

## Revit Could Not Reload the Keynote Table

During **Refresh**, Flow reloads the keynote file and also requests that Revit reload its keynote table.

If Flow reports that the keynote file was reloaded but Revit could not reload the keynote table:

1. Confirm that the correct keynote file is assigned to the project.
2. Confirm that the `.txt` file exists and is accessible.
3. Check that the keynote file is valid.
4. Retry **Refresh**.

If the problem continues, close and reopen the project and check the project's native Revit keynote settings.

---

## I Opened Another File and Lost My Changes

Keynote Manager checks for unsaved changes before operations that would discard the currently edited information.

If prompted with **Unsaved Changes**, choose carefully:

* **Discard** continues without saving the current changes.
* **Cancel** returns to Keynote Manager so that you can save them first.

Use **Save** before opening, closing or refreshing a file when the changes should be retained.

---

## Reporting a Problem

If the problem continues, record:

* the Revit version
* the project being used
* the keynote filename and location
* whether the file is shown as the current project keynote file
* what you were trying to do
* what you expected to happen
* what happened instead
* any message displayed by Flow
* a screenshot of Keynote Manager or the displayed message where useful

---

## Related Help

* [Keynote Manager](index.md)
* [Working with Keynotes](working-with-keynotes.md)
* [Project Keynote Files](project-keynote-files.md)
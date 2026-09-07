# Keynote Manager Troubleshooting

Use these checks when Keynote Manager cannot access the expected keynote
file, a keynote cannot be found, changes cannot be saved or updated
keynote information is not reflected correctly in Revit.

------------------------------------------------------------------------

## The Project Keynote File Does Not Open Automatically

When Keynote Manager opens, it checks the active Revit project's native
keynote table for the currently assigned keynote file.

If no file opens:

1.  Check that the project has a keynote file assigned in Revit.
2.  Confirm that the assigned `.txt` file still exists.
3.  Confirm that the file location is accessible from the current
    workstation.
4.  Use **File → Open...** to browse to the required file if necessary.

!!! info "Opening and assigning are separate"

    Opening a keynote file in Keynote Manager does not automatically make it the project's Revit keynote file.

    If the correct file is open but shows **Not assigned to this project**, use **Set as Project Keynote File**.

------------------------------------------------------------------------

## The Wrong Keynote File Is Open

Check the loaded filename and project status.

If the wrong file is open:

1.  Use **File → Open...**.
2.  Select the correct `.txt` file.
3.  Confirm that the expected hierarchy is displayed.
4.  If Revit should also use that file, choose **Set as Project Keynote
    File**.

------------------------------------------------------------------------

## New Suggests the Wrong Folder or Filename

Flow uses the Revit **Project Number** when suggesting a new keynote
filename and project folder.

For example:

``` text
26123
```

normally produces:

``` text
26123_Keynotes.txt
```

If the project number is missing or Flow cannot resolve the expected
project folder, it uses its fallback documents location. With no Project
Number, the fallback filename is:

``` text
Project_Keynotes.txt
```

You can change the location and filename in the Save dialog before
creating the file.

------------------------------------------------------------------------

## A Recent Keynote File Cannot Be Found

A recent-file entry can become invalid if the file has been moved,
renamed or deleted.

Use **File → Open...** to browse to its current location.

------------------------------------------------------------------------

## I Can't Find a Keynote

Try the following:

1.  Press **Esc** to clear the current search and selection.
2.  Expand the appropriate category.
3.  Search using part of the keynote code or description.
4.  Confirm that the expected keynote file is loaded.

Search checks both the keynote code and description.

------------------------------------------------------------------------

## The Usage Count Is Not What I Expected

The green usage indicator counts **placed Revit keynote tags only**.

It does not count an element or type simply because its keynote
parameter contains that code.

For example, a keynote can show no placed-tag usage while still being
assigned to an element or type.

Usage information is refreshed when Flow loads or refreshes keynote
information and after a successful Sync.

------------------------------------------------------------------------

## I Can't Add a Keynote

Before adding a keynote, select the category that should contain it.

Then choose:

**Add → Add Keynote**

Check that:

-   a category is selected
-   the keynote code is not blank
-   the description is not blank
-   the proposed keynote code does not already exist

Keynote codes must be unique within the loaded file.

------------------------------------------------------------------------

## The Suggested Keynote Number Is Not What I Expected

Flow looks for the first available numbered code in the selected
category.

For example:

``` text
45-01
45-02
45-04
```

suggests:

``` text
45-03
```

You can change the suggested code before adding the keynote.

------------------------------------------------------------------------

## The Library Opens in the Wrong Category

When the Library opens from Add or Edit, Flow uses the prefix of the
current keynote code to select a matching Library category where
possible.

Check the keynote code before opening the Library. You can also change
the category filter manually inside the Library.

The Library supplies a description; it does not replace the project
keynote code.

------------------------------------------------------------------------

## I Can't Multi-select Keynotes

Multi-selection is limited to keynote entries within the same category.

Hold **Ctrl** while selecting the required entries.

If you select an item from another category, Flow resets the selection
rather than maintaining a multi-category selection.

------------------------------------------------------------------------

## Removing a Keynote Did Not Renumber the Category

This is expected.

**Remove** deletes the selected keynote but leaves the remaining codes
unchanged.

Use **Renumber** separately when the category should be consecutively
numbered.

------------------------------------------------------------------------

## Clean Did Not Renumber the Category

This is expected.

**File → Maintenance → Clean Selected Category...** removes keynote
entries with blank descriptions only.

It deliberately leaves the numbering of the remaining entries unchanged.

Use **Renumber** separately if consecutive numbering is required.

------------------------------------------------------------------------

## Renumber Is Not Available

The visible **Renumber** workflow requires a category to be selected.

Select the category itself in the keynote tree, then click **Renumber**.

------------------------------------------------------------------------

## Renumber Reports That the Category Is Already Consecutively Numbered

If the selected category already follows consecutive numbering, Flow
does not make unnecessary changes.

No further action is required.

------------------------------------------------------------------------

## Renumber Finds Blank Keynotes

If blank-description entries exist in the selected category, Flow asks
how to continue.

Choose:

**Clean & Renumber**

to remove the blank entries before renumbering,

or:

**Renumber Only**

to retain them and continue with the renumbering operation.

Review the Renumber Preview before confirming the changes.

------------------------------------------------------------------------

## Changes Cannot Be Saved

If **Save** is not available, check whether the loaded keynote
information actually contains unsaved changes.

If changes exist but the file cannot be written:

1.  Confirm that the `.txt` location is accessible.
2.  Confirm that you have permission to modify the file.
3.  Check whether the file is read-only or otherwise unavailable.
4.  Use **Save As...** if the information should be written to another
    location.

------------------------------------------------------------------------

## Refresh Is Not Available

**Refresh** is disabled while Keynote Manager contains unsaved changes.

Use **Save** first if you want to keep those changes.

Refresh can then reload the file and tell Revit to reload its keynote
table.

------------------------------------------------------------------------

## Revit Does Not Show a Newly Added or Edited Keynote

Saving and refreshing are separate operations.

1.  **Save** the Keynote Manager changes.
2.  Click **Refresh**.
3.  Check the keynote again in Revit.

**Save** writes the `.txt` file.

**Refresh** reloads the file and tells Revit's native keynote table to
reload it.

------------------------------------------------------------------------

## Revit Still Uses an Old Keynote Code

Changing a keynote code does not automatically replace every existing
reference to the previous code.

This can occur after:

-   manually changing a keynote code
-   moving a keynote to another category
-   renumbering a category

Use this workflow:

1.  Complete the keynote code change.
2.  **Save** the keynote file.
3.  Click **Sync**.
4.  Review the Sync Preview.
5.  Apply the synchronisation.
6.  Use **Refresh** if Revit also needs to reload the latest keynote
    table.

Sync can check placed keynote tags, instance keynote parameters and type
keynote parameters against Flow's recorded old-to-new code mapping.

------------------------------------------------------------------------

## Sync Is Not Available

Sync requires:

-   at least one pending recorded keynote code change
-   a loaded keynote file
-   no unsaved Keynote Manager changes

If you have just changed or renumbered a keynote code:

1.  Save the keynote file.
2.  Check **Sync** again.

Editing only a description does not create an old-to-new code mapping.

------------------------------------------------------------------------

## Sync Reports No References Require Updating

The scan did not find Revit references whose current value matches the
pending old keynote codes.

The affected codes may not currently be used by:

-   keynote tags
-   instance keynote parameters
-   type keynote parameters

No project reference changes are required in that case.

------------------------------------------------------------------------

## Some References Were Not Changed by Sync

Before changing a reference, Flow verifies that the element and keynote
parameter still exist, that the parameter is writable and that its
current value still matches the old code from the preview.

A reference can therefore be skipped if it has changed since the
preview, is read-only or is otherwise no longer suitable for the
proposed update.

Review the affected Revit item directly if a reference does not change
as expected.

------------------------------------------------------------------------

## Revit Could Not Reload the Keynote Table

During **Refresh**, Flow asks Revit's native keynote table to reload.

If the reload fails:

1.  Confirm that the correct keynote file is assigned to the project.
2.  Confirm that the `.txt` file exists and is accessible.
3.  Check that the keynote file is valid.
4.  Retry **Refresh**.

If the problem continues, check the project's native Revit keynote
settings.

------------------------------------------------------------------------

## I Opened or Closed a File with Unsaved Changes

Keynote Manager checks for unsaved changes before operations that would
discard the current edits.

If prompted, save the changes when they should be retained, discard them
only when they are no longer required, or cancel to return to Keynote
Manager.

------------------------------------------------------------------------

## Reporting a Problem

If the problem continues, record:

-   the Revit version
-   the project being used
-   the keynote filename and location
-   whether the file is shown as the current project keynote file
-   what you were trying to do
-   what you expected to happen
-   what happened instead
-   any message displayed by Flow
-   a screenshot where useful

------------------------------------------------------------------------

## Related Help

-   [Keynote Manager](index.md)
-   [Working with Keynotes](working-with-keynotes.md)
-   [Project Keynote Files](project-keynote-files.md)

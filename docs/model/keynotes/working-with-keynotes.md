# Working with Keynotes

Use **Keynote Manager** to browse, search and maintain the keynote
information in the currently loaded keynote file.

------------------------------------------------------------------------

## Browse the Keynote Hierarchy

Keynote Manager displays the file as a hierarchy of **categories** and
**keynotes**.

Expand a category to view its keynote entries. Expanding a top-level
category collapses the other top-level categories to keep the tree
manageable.

Selecting a keynote allows you to edit or remove it. Selecting a
category allows you to add entries and use category-level tools such as
**Clean Selected Category** and **Renumber**.

Long descriptions can be viewed from the item tooltip when the visible
text is truncated.

------------------------------------------------------------------------

## Search for a Keynote

Use **Search key or description...** to find keynote entries without
browsing the complete hierarchy.

Search matches both:

-   keynote codes
-   keynote descriptions

As you type, Flow displays matching results and selects the first
result.

Press **Esc** to clear the search and current selection.

!!! tip "Use part of the code or description"

    You do not need to enter the complete keynote. For example, search for `insulation` to find descriptions containing that term.

------------------------------------------------------------------------

## Review Keynote Usage

A green indicator identifies a keynote code that is currently used by
one or more placed Revit keynote tags.

The number beside the keynote is the number of placed keynote tags using
that code.

Usage is based on **placed keynote tags only**. It does not count
elements or types that merely have a keynote parameter assigned.

Usage information is refreshed when Flow loads or refreshes keynote
information and after a successful Sync.

<!-- SCREENSHOT: Expanded category showing green usage indicators and counts.
Capture after opening a project with several placed keynote tags. -->

------------------------------------------------------------------------

## Add a Keynote

To add a keynote:

1.  Select the category that should contain it.
2.  Click **Add**.
3.  Choose **Add Keynote**.
4.  Review the suggested keynote code.
5.  Enter a description, or use **Library** to choose an approved
    description.
6.  Click **Add**.
7.  Save the keynote file when you are ready to write the change to
    disk.

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

The code and description cannot be blank, and the keynote code must be
unique within the loaded file.

<!-- SCREENSHOT: Add Keynote window.
Show the suggested key, Description field and Library button. -->

------------------------------------------------------------------------

## Use the Keynote Library

The **Library** provides approved keynote descriptions that can be
inserted while adding or editing a keynote.

When the Library opens, Flow uses the current keynote prefix to select
the corresponding category where possible.

You can:

-   search approved descriptions
-   filter by category
-   select an option and choose **Use Selected**
-   double-click an option to use it

The selected Library entry fills the **Description** field. It does not
replace the project keynote code.

This allows the project file to keep its own numbering while reusing
approved wording.

------------------------------------------------------------------------

## Add a Category

To create a category:

1.  Click **Add**.
2.  Choose **Add Category**.
3.  Enter the category key.
4.  Enter the category description.
5.  Click **Add**.
6.  Save the keynote file.

Both fields are required.

The category key must not duplicate an existing key in the loaded
keynote file.

------------------------------------------------------------------------

## Edit a Keynote

Double-click a keynote, or select it and click **Edit**.

You can change:

-   the keynote code
-   the keynote description

You can also use **Library** to replace the description with approved
wording.

Changes remain unsaved until you use **Save**.

### Move a Keynote to Another Category

Changing the category prefix of a keynote can move it to another
existing category.

When Flow recognises the entered prefix as another category, the Edit
window displays the proposed destination category and suggested keynote
code.

Flow allocates an available code in the destination category rather than
blindly retaining a conflicting number.

<!-- SCREENSHOT: Edit Keynote window.
Show a changed category prefix with the destination category and suggested key preview visible. -->

!!! warning "Changing a code can affect Revit references"

    Changing a keynote code, including moving it to another category, can leave existing Revit references using the previous code.

    Save the keynote file and use **Sync** when those references need to follow the new code.

------------------------------------------------------------------------

## Remove a Keynote

Select the required keynote and click **Remove**.

Flow asks for confirmation before removing the entry.

Removing a keynote does not automatically renumber the remaining
entries.

!!! warning "Usage count covers placed tags only"

    A zero usage count means there are no placed keynote tags using that code. It does not prove that no element or type keynote parameter uses the code.

------------------------------------------------------------------------

## Remove Multiple Keynotes

You can select multiple keynote entries within the same category.

1.  Hold **Ctrl**.
2.  Select the required keynotes.
3.  Click **Remove**.
4.  Confirm the removal.

If you Ctrl-select an item from another category, Flow resets the
selection rather than creating a multi-category selection.

------------------------------------------------------------------------

## Clean a Category

**Clean Selected Category** removes keynote entries with blank
descriptions.

To clean a category:

1.  Select the category.
2.  Open **File → Maintenance**.
3.  Choose **Clean Selected Category...**.
4.  Review the number of blank entries found.
5.  Confirm the operation.
6.  Save the keynote file.

Cleaning deliberately leaves the remaining numbering unchanged.

For example:

``` text
45-01    Window
45-02
45-03    Exterior door
```

becomes:

``` text
45-01    Window
45-03    Exterior door
```

Use **Renumber** separately if you also want consecutive numbering.

------------------------------------------------------------------------

## Renumber a Category

Use **Renumber** to reorganise the keynote codes in the selected
category into consecutive numbering.

For example:

``` text
45-01
45-03
45-07
```

can become:

``` text
45-01
45-02
45-03
```

To renumber:

1.  Select the category.
2.  Click **Renumber**.
3.  If blank keynote entries exist, choose **Clean & Renumber** or
    **Renumber Only**.
4.  Review the proposed changes in the Renumber Preview.
5.  Confirm the changes.
6.  Save the keynote file.
7.  Use **Sync** if existing Revit references need to follow the changed
    codes.

<!-- SCREENSHOT: Renumber Preview.
Show several old-to-new keynote code changes before confirmation. -->

Flow records the old-to-new code changes created by the renumber
operation so they can be reviewed by Sync.

!!! warning "Save before Sync"

    Sync is unavailable while Keynote Manager contains unsaved changes.

------------------------------------------------------------------------

## Save Your Changes

Changes made in Keynote Manager are not automatically written to disk.

Use **Save** to write them to the currently loaded keynote `.txt` file.

Use **Save As...** when the current keynote information should be
written to another file.

If an operation would discard unsaved work, Keynote Manager prompts you
before continuing.

------------------------------------------------------------------------

## Refresh After External Changes

Use **Refresh** when the keynote file has changed outside Keynote
Manager or when Revit needs to reload the current keynote table.

Refresh is unavailable while Keynote Manager contains unsaved changes.

See [**Project Keynote Files**](project-keynote-files.md) for the
difference between Save, Refresh and Sync.

------------------------------------------------------------------------

## Related Help

-   [Keynote Manager](index.md)
-   [Project Keynote Files](project-keynote-files.md)
-   [Troubleshooting](troubleshooting.md)

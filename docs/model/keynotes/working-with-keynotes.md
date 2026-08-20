# Working with Keynotes

Use **Keynote Manager** to browse, search and maintain the keynote information available in the currently loaded keynote file.

---

## Open Keynote Manager

On the Revit ribbon:

**Flow → Model → Keynotes**

---

## Browse the Keynote Hierarchy

Keynote Manager displays the keynote file as a hierarchy of **categories** and **keynotes**.

Expand a category to view the keynote entries contained within it.

Selecting a keynote allows you to edit or remove that entry. Selecting a category allows you to add keynotes to it and use category-level maintenance tools such as **Clean** and **Renumber**.

!!! info "Categories and keynotes"

	Categories form the top level of the keynote hierarchy. Individual keynote entries are displayed beneath their parent category.

---

## Search for a Keynote

Use the **Search** box to find keynote entries without manually browsing the complete hierarchy.

Search matches both:

* keynote codes
* keynote descriptions

As you type, Keynote Manager filters the displayed information to matching results.

Press **Esc** to clear the current search.

!!! tip "You do not need the complete keynote"

	Search using any recognisable part of the keynote code or description. For example, searching for `insulation` can be used to locate keynote descriptions containing that term.

---

## Review Keynote Usage

Keynote Manager can identify keynote entries currently referenced by the Revit project.

Use the **Used** and **Unused** filters to control which keynote entries are displayed.

This can be useful when reviewing a large project keynote file or identifying entries that are not currently referenced by the model.

The usage information is refreshed from the current Revit project.

!!! info "Usage does not remove keynotes"

	The Used and Unused controls only filter what is displayed in Keynote Manager. They do not modify the keynote file.

---

## Add a Keynote

To add a keynote:

1. Select the category that should contain the new keynote.
2. Click **Add**.
3. Choose **Add Keynote**.
4. Review the suggested keynote code.
5. Enter the keynote description.
6. Click **Add**.

Keynote Manager suggests the next available numbered keynote within the selected category.

For example, if the category already contains:

```text
45-01
45-02
45-03
```

the suggested code will be:

```text
45-04
```

You can change the suggested code before adding the keynote.

Keynote codes must be unique within the loaded keynote file.

---

## Add a Category

To create a new category:

1. Click **Add**.
2. Choose **Add Category**.
3. Enter the category key.
4. Enter the category description.
5. Click **Add**.

The new category is inserted into the keynote hierarchy according to its key.

A category key must not duplicate an existing key in the keynote file.

---

## Edit a Keynote

Double-click a keynote, or select it and use the available edit control, to open the keynote editor.

You can update the keynote description and, where supported by the selected keynote operation, move the keynote to another valid position in the hierarchy.

Apply the change to return to Keynote Manager.

Changes remain unsaved until the keynote file is saved.

!!! warning "Changing keynote codes can affect project references"

	If a keynote code is changed, existing Revit elements or keynote tags may still reference the previous code.

	Use the keynote synchronisation workflow after saving when references need to be updated. See [**Project Keynote Files**](project-keynote-files.md).

---

## Remove a Keynote

Select the required keynote and choose **Remove**.

Keynote Manager asks for confirmation before removing the entry.

Removing a keynote changes the keynote file but does not automatically renumber the remaining entries.

!!! warning "Check project usage before removing keynotes"

	A keynote may already be referenced by elements or keynote tags in the Revit project. Review its usage before removing it.

---

## Remove Multiple Keynotes

Multiple keynote entries within the same category can be selected using **Ctrl**.

To remove several entries:

1. Hold **Ctrl**.
2. Select the required keynotes.
3. Choose **Remove**.
4. Confirm the removal.

Multi-selection is limited to keynote entries within the same category.

---

## Clean a Category

Categories can contain empty keynote entries.

To remove them:

1. Select the category.
2. Choose **Clean Category**.
3. Review the number of empty entries found.
4. Confirm the removal.

Cleaning removes the empty keynote entries without changing the numbering of the remaining keynotes.

For example:

```text
45-01    Window
45-02
45-03    Exterior door
```

becomes:

```text
45-01    Window
45-03    Exterior door
```

The remaining keynote is **not** automatically changed from `45-03` to `45-02`.

---

## Renumber a Category

Use **Renumber** to reorganise the keynote codes within a selected category into consecutive numbering.

For example:

```text
45-01
45-03
45-07
```

can become:

```text
45-01
45-02
45-03
```

To renumber a category:

1. Select the category, or a keynote within that category.
2. Choose **Renumber**.
3. If empty keynote entries exist, choose whether to **Clean & Renumber** or **Renumber Only**.
4. Review the proposed changes in the renumber preview.
5. Confirm the changes.
6. Save the keynote file.

Keynote Manager records the relationship between the old and new codes so that affected Revit references can subsequently be synchronised.

!!! warning "Save before synchronising"

	Renumbering changes the keynote information in Keynote Manager first.

	Save the keynote file before using **Sync** to update affected references in the Revit project.

---

## Save Your Changes

Changes made through Keynote Manager are not automatically written to the keynote file.

Use **Save** to write the changes to the current file.

The Keynote Manager status indicates when there are unsaved changes.

You can also use **Save As** when the keynote information should be written to a different file.

!!! warning "Unsaved changes"

	If you attempt to open, refresh or close the current keynote file while unsaved changes exist, Keynote Manager asks whether those changes should be discarded.

---

## Refresh After External Changes

If the keynote text file has been changed outside Keynote Manager, use **Refresh** to reload it.

Refresh also requests that Revit reload its keynote table so that the current keynote information is available to the project.

Refresh is unavailable while Keynote Manager contains unsaved changes.

---

## Related Help

* [Keynote Manager](index.md)
* [Project Keynote Files](project-keynote-files.md)
* [Troubleshooting](troubleshooting.md)
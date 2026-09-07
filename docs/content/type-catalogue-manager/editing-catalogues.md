# Editing Catalogues

Use **Type Catalogue Manager** to modify catalogue values and manage the type rows contained within an existing catalogue.

---

## Before Editing

Open the required catalogue and review its current validation status.

See [**Opening and Reviewing Catalogues**](opening-and-reviewing.md).

---

## Edit a Value

Catalogue values can be edited directly in the main grid.

1. Locate the required type and parameter.
2. Select the cell you want to change.
3. Enter the new value.
4. Complete the cell edit.

Flow marks the catalogue as having **Unsaved Changes** and refreshes validation as required.

---

## Use Value Suggestions

When editing a cell, Type Catalogue Manager can suggest values already used in the same catalogue column.

Start entering a value to display matching suggestions.

You can then:

* use **Up** and **Down** to move through the suggestions;
* press **Enter** or **Tab** to use the selected value;
* press **Esc** to close the suggestions;
* double-click a suggestion to use it.

Suggestions are based on matching values already present in that column and are intended to make repeated catalogue values easier to enter consistently.

<!-- SCREENSHOT: Cell editing with the suggestion popup visible.
Use a parameter column with several repeated real values so the suggestion behaviour is obvious. -->

---

## Add a Type Row

To create a new blank row:

1. Select the row near where the new type should be added.
2. Open the **Rows** menu.
3. Choose **Insert Row Below**.
4. Enter the required **Type Name**.
5. Enter the required catalogue values.

If no row is selected, the new row is added at the end of the catalogue.

Validation is refreshed after the row is added.

---

## Duplicate a Type Row

Use **Duplicate Row** when a new type is similar to an existing one.

1. Select the row you want to copy.
2. Open the **Rows** menu.
3. Choose **Duplicate Row**.
4. Change the copied **Type Name**.
5. Edit any other values that need to differ.

The duplicated row is inserted immediately below the source row.

!!! warning "Use a unique Type Name"

    A duplicated row initially contains the same Type Name as the source row.

    Duplicate Type Names are validation errors, so change the copied name before completing the catalogue.

---

## Delete a Type Row

To remove a type:

1. Select the required row.
2. Open the **Rows** menu.
3. Choose **Delete Row**.

Validation is refreshed after the row is removed.

---

## Save the Catalogue

Use **File → Save Catalogue** to write changes to the current file.

Before an existing catalogue is replaced, Flow creates a backup copy.

When saving, Flow preserves the Revit data type and unit information stored in the catalogue parameter headers.

After saving, the catalogue is reloaded and validation is refreshed.

!!! warning "Validation and saving are separate"

    Saving a catalogue does not mean every value is valid.

    Review the **Validation** panel before treating the catalogue as complete.

---

## Save as a New Catalogue

Use **Save As** when the edited catalogue should become a separate file.

1. Choose **File → Save As**.
2. Select the destination and file name.
3. Save the catalogue.
4. Continue working with the newly saved file.

If the destination already exists, Flow asks whether you want to replace it.

After **Save As**, the new file becomes the active catalogue for subsequent saves and reloads.

---

## Reload the Catalogue

Use **File → Reload** to read the current catalogue from disk again.

This is useful where the source file has changed outside Type Catalogue Manager or where you want to discard the current in-memory version and return to the saved file.

If the catalogue contains unsaved changes, Flow asks how you want to proceed before reloading so that edits are not discarded accidentally.

---

## Close with Unsaved Changes

If you close Type Catalogue Manager while the catalogue contains unsaved edits, Flow asks what you want to do.

Choose:

* **Save Changes** to save before closing;
* **Discard Changes** to close without saving;
* **Cancel** to return to Type Catalogue Manager.

---

## Recommended Editing Workflow

For routine catalogue editing:

1. open the catalogue;
2. review Validation;
3. make the required value or row changes;
4. resolve any new validation issues;
5. run **Conform Catalogue** if structural clean-up is required;
6. review Validation again;
7. save the catalogue.

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)

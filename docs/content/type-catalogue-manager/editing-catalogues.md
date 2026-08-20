# Editing Catalogues

Use **Type Catalog Manager** to modify catalogue values and manage the type rows contained within an existing catalogue.

---

## Before Editing

Open the required catalogue in **Type Catalog Manager**.

See [**Opening and Reviewing Catalogues**](opening-and-reviewing.md).

---

## Edit a Value

Catalogue values can be edited directly in the main grid.

1. Locate the required type and parameter.
2. Select the cell you want to change.
3. Edit the value.
4. Complete the cell edit.

The catalogue is marked as having **Unsaved Changes**.

---

## Use Value Suggestions

When editing a cell, Type Catalog Manager can suggest existing values from the same catalogue column.

Start entering a value to display matching suggestions.

You can then:

* use **Up** and **Down** to move through the suggestions;
* press **Enter** or **Tab** to use the selected value;
* press **Esc** to close the suggestions;
* double-click a suggestion to use it.

!!! tip "Keep repeated values consistent"

	Suggestions are taken from values already used in the same catalogue column.

	This can be useful when several types use the same material, operation or other repeated value.

---

## Add a Type Row

To create a new blank row:

1. Select the row near where the new type should be added.
2. Open the **Rows** controls.
3. choose **Insert Row Below**.
4. Enter the required Type Name and catalogue values.

If no row is selected, the new row is added at the end of the catalogue.

Validation is refreshed after the row is added.

---

## Duplicate a Type Row

Use **Duplicate Row** when a new type is similar to an existing one.

1. Select the row you want to copy.
2. Open the **Rows** controls.
3. Choose **Duplicate Row**.
4. Edit the copied Type Name and any values that need to change.

The duplicated row is inserted immediately below the original.

!!! warning "Give the duplicated row a unique Type Name"

	A duplicated row initially contains the same Type Name as the source row.

	Change the Type Name before saving the final catalogue. Duplicate type names are reported as validation errors.

---

## Delete a Type Row

To remove a type:

1. Select the required row.
2. Open the **Rows** controls.
3. Choose **Delete Row**.

Validation is refreshed after the row is removed.

---

## Save the Catalogue

Use **Save** to write the changes back to the current catalogue.

When an existing catalogue is saved, Flow creates a backup copy before replacing the file.

Catalogue parameter definitions, including their Revit data type and unit information, are preserved when the catalogue is edited and saved.

After saving, Type Catalog Manager reloads the catalogue data and refreshes its validation results.

A confirmation displays the saved catalogue location.

---

## Save as a New Catalogue

Use **Save As** when the edited catalogue should be written to a different `.txt` file.

1. Choose **Save As**.
2. Select the destination and file name.
3. Save the catalogue.

If the selected destination already exists, Flow asks whether you want to replace it.

---

## Close with Unsaved Changes

If you close Type Catalog Manager while the catalogue contains unsaved edits, Flow asks what you want to do.

Choose:

* **Save Changes** to save before closing;
* **Discard Changes** to close without saving;
* **Cancel** to return to Type Catalog Manager.

!!! warning "Check validation before finishing"

	Saving a catalogue does not mean that all catalogue values are valid.

	Review the **Validation** panel before completing your changes.

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)
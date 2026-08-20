# Type Catalog Manager Troubleshooting

Use the following checks if Type Catalog Manager or a type catalogue is not behaving as expected.

---

## Type Catalog Manager Is Not Open

Open Type Catalog Manager from the Revit ribbon:

**Flow → Content → Types**

You can also search for **Type Catalog Manager** using the **Command Palette**.

---

## A Catalogue Cannot Be Opened

Confirm that:

1. the `.txt` file still exists;
2. you have access to its location;
3. the file contains a catalogue header and catalogue data.

Type Catalog Manager requires a readable type catalogue file before it can load the catalogue grid.

---

## The Catalogue Shows Validation Issues

Review the **Validation** panel.

Select an issue to navigate to the affected row or cell.

Common problems include:

* duplicate column headers;
* duplicate Type Names;
* missing values;
* empty values.

See [**Validation and Inspection**](validation-and-inspection.md).

---

## A Catalogue Contains Structural Problems

Use **Conform Catalogue** to clean up structural problems that Flow can resolve safely.

Conform can correct issues such as duplicate columns, missing cells and completely empty rows while preserving the existing Revit parameter definitions contained in the catalogue header.

Blank or duplicate Type Names still require manual review.

See [**Conforming Catalogues**](conforming-catalogues.md).

---

## A Duplicated Row Shows an Error

Duplicating a row initially copies all of its existing values, including its Type Name.

Change the copied row to a unique Type Name.

Duplicate Type Names are reported as validation errors.

---

## Changes Have Not Been Saved

When a catalogue has been edited, Type Catalog Manager identifies it as having **Unsaved Changes**.

Use **Save** to update the current catalogue or **Save As** to create a separate catalogue file.

If you try to close the Manager with unsaved edits, choose **Save Changes** to save before closing.

---

## Generate Catalogue Does Not Work

When generating directly from Type Catalog Manager, make sure the active Revit document is a **family document**.

If you are working with a family in the content library, you can instead start **Generate Type Catalog** from Content Browser.

---

## A Parameter Is Missing from Catalogue Generation

Formula-driven and reporting parameters are intentionally excluded from the available parameter list.

These parameters cannot be selected for catalogue generation.

If the parameter is otherwise eligible, use the parameter search to locate it in the selection window.

---

## A Preset Does Not Select the Expected Parameters

A preset can only select parameters that are available in the current family.

Review the selected parameters after applying the preset and adjust the selection before generating the catalogue.

---

## Content Browser Cannot Edit a Catalogue

The selected library family must have an associated `.txt` type catalogue.

If the catalogue cannot be found, Content Browser reports:

**Type catalog not found.**

You can generate a new catalogue from the family where appropriate.

---

## Content Browser Cannot Conform a Catalogue

The selected family must have an associated type catalogue.

If no catalogue is found, Flow reports:

**No type catalogue found for this family.**

Generate a catalogue first if the family requires one.

---

## Still Having Problems?

Check that the family and catalogue files are available and that you have access to their storage location.

If the catalogue opens successfully, use the **Validation** panel to identify catalogue-data problems before making further changes.

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Generating Catalogues**](generating-catalogues.md)
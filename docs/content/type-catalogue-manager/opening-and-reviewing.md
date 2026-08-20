# Opening and Reviewing Catalogues

Use **Type Catalog Manager** to open an existing Revit type catalogue and review its types, parameter values and validation status.

---

## Open Type Catalog Manager

On the Revit ribbon:

**Flow → Content → Types**

You can also launch **Type Catalog Manager** through the **Command Palette**.

---

## Open a Catalogue

From Type Catalog Manager:

1. Open the **File** menu.
2. Choose the option to open a catalogue.
3. Browse to the required `.txt` type catalogue.
4. Select the file and open it.

The catalogue is loaded into the main grid.

The status area identifies the loaded file and reports the number of validation issues found.

---

## Review the Catalogue

Each catalogue type is displayed as a row in the main grid.

The first column represents the **Type Name**, followed by the parameter columns contained in the catalogue.

Use the grid to review the values assigned to each type.

---

## Search the Catalogue

Use the **Search** box to find information within the loaded catalogue.

Search checks the values across the catalogue columns and filters the grid to matching rows.

Clear the search to return to the complete catalogue.

!!! tip "Search by any known value"

	You do not need to know the exact type name.

	Search can be useful when you know part of a type name, dimension, material or another value contained within the catalogue.

---

## Inspect a Row

Select a catalogue row to review it in the **Inspector**.

The Inspector displays the values for the selected row.

If validation issues have been identified for that row, those issues are also shown in the Inspector.

---

## Review Validation Issues

The **Validation** panel lists problems identified in the loaded catalogue.

Each issue identifies its:

* severity;
* affected row, where applicable;
* affected column, where applicable;
* validation message.

Select a validation issue to navigate to the affected location in the catalogue.

See [**Validation and Inspection**](validation-and-inspection.md) for details of the checks performed.

---

## Open from Content Browser

If a library family already has an associated type catalogue, you can open it directly from **Content Browser**.

Use the type-catalogue editing action for the selected family.

Flow resolves the corresponding `.txt` file and opens it directly in **Type Catalog Manager**.

!!! info "Associated catalogue"

	The type catalogue is expected to use the same base file name as its Revit family, with the `.txt` file located as the associated catalogue.

---

## Next Steps

To modify the catalogue, see [**Editing Catalogues**](editing-catalogues.md).

To clean up structural catalogue problems, see [**Conforming Catalogues**](conforming-catalogues.md).

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)
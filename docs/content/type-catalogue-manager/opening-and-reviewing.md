# Opening and Reviewing Catalogues

Use **Type Catalogue Manager** to open an existing Revit type catalogue and review its types, parameter values and validation status before making changes.

---

## Open Type Catalogue Manager

On the Revit ribbon:

**Flow → Content → Types**

You can also launch **Type Catalogue Manager** through the **Command Palette**.

---

## Open a Catalogue

From Type Catalogue Manager:

1. Open the **File** menu.
2. Choose **Open Catalogue**.
3. Browse to the required `.txt` type catalogue.
4. Select the file and open it.

The catalogue is loaded into the main grid and validated automatically.

The first catalogue field is displayed as **Type Name**, followed by the parameter columns defined in the catalogue header.

!!! info "Opening does not change the file"

    Opening a catalogue is a review operation. The source file is not changed unless you later save changes or run an operation that explicitly writes to the catalogue.

---

## What Happens When a Catalogue Opens

Flow reads the catalogue structure and prepares it for review.

It:

* reads the catalogue header;
* identifies the catalogue columns;
* preserves Revit data type and unit information contained in parameter headers;
* reads the type rows;
* displays the catalogue in the main grid;
* runs catalogue validation;
* populates the **Validation** panel.

If the file cannot be interpreted as a readable type catalogue, Flow reports the problem rather than opening an incomplete grid.

---

## Review the Catalogue Grid

Each family type is displayed as a row.

The first column is **Type Name**. The remaining columns contain the parameter values stored for that type.

Use the grid to check:

* type names;
* dimensions;
* materials;
* other catalogue-driven parameter values;
* whether values are consistent between similar types.

For a wide catalogue, use the horizontal grid controls together with the **Inspector** to avoid having to review every value directly in the row.

---

## Search the Catalogue

Use the **Search** box to filter the loaded catalogue.

Search checks values across the displayed catalogue columns and keeps matching rows visible.

Clear the search to return to the complete catalogue.

!!! tip "Search by any known value"

    You do not need to know the exact Type Name. Search can be useful when you know part of a type name, dimension, material or another value contained in the catalogue.

---

## Inspect a Row

Select a catalogue row to review it in the **Inspector**.

The Inspector displays:

1. validation issues associated with the selected row, where present; and
2. the values contained in the catalogue columns for that row.

This is particularly useful for catalogues with many columns.

---

## Review Validation Issues

The **Validation** panel lists issues found during the automatic catalogue check.

Each issue identifies its:

* severity;
* message;
* affected row, where applicable;
* affected column, where applicable.

Select a validation issue to navigate to the affected row or cell.

<!-- SCREENSHOT: Validation review.
Use a catalogue containing at least one duplicate Type Name and one blank value.
Show the Validation panel, the selected affected row and the Inspector. -->

See [**Validation and Inspection**](validation-and-inspection.md) for the checks performed.

---

## Open from Content Browser

If a library family has an associated type catalogue, you can open it directly from **Content Browser**.

Use the type-catalogue editing action for the selected family.

Flow resolves the catalogue associated with the family and opens it in **Type Catalogue Manager**.

!!! info "Associated catalogue"

    The family and catalogue are expected to use the same base file name, for example:

    `ADa_Window_Awning.rfa`

    `ADa_Window_Awning.txt`

---

## Next Steps

To modify catalogue data, see [**Editing Catalogues**](editing-catalogues.md).

To understand identified problems, see [**Validation and Inspection**](validation-and-inspection.md).

To clean up structural problems, see [**Conforming Catalogues**](conforming-catalogues.md).

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)

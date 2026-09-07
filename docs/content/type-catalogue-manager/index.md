# Type Catalogue Manager

The **Type Catalogue Manager** provides tools for creating, reviewing, editing and maintaining Revit family type catalogues.

Use it to open an existing catalogue, review and edit type data, identify validation problems, conform catalogue structure, or generate a new catalogue directly from a Revit family.

---

## Open Type Catalogue Manager

On the Revit ribbon:

**Flow → Content → Types**

You can also find **Type Catalogue Manager** through the **Command Palette**.

<!-- SCREENSHOT: Main Type Catalogue Manager window.
Show the File, Rows and Tools menus, Search box, populated catalogue grid,
Inspector panel, Validation panel and status area. -->

---

## Understand the Window

The Type Catalogue Manager is organised around the catalogue grid.

### File

Use the **File** menu to:

* open an existing catalogue;
* save the current catalogue;
* save the catalogue to a new location;
* reload the current file from disk.

### Rows

Use the **Rows** menu to:

* duplicate the selected type row;
* insert a new row below the selected row;
* delete the selected row.

The same row actions are also available from the grid context menu.

### Tools

Use the **Tools** menu to:

* **Conform Catalogue** — clean up structural catalogue problems that Flow can resolve safely;
* **Generate Catalogue** — generate a new catalogue from the active Revit family.

### Search

The **Search** box filters the catalogue grid using values across the displayed columns.

Clear the search to return to the complete catalogue.

### Inspector

Select a row to review its values in the **Inspector**.

If the selected row has validation issues, these are also displayed in the Inspector.

### Validation

The **Validation** panel lists problems identified in the loaded catalogue.

Select an issue to navigate to the affected row or cell.

---

## First-Time Workflow — Existing Catalogue

For an existing `.txt` type catalogue:

1. Open **Type Catalogue Manager**.
2. Choose **File → Open Catalogue**.
3. Select the required `.txt` file.
4. Review the catalogue grid.
5. Review the **Validation** panel.
6. Select individual rows and use the **Inspector** where more detail is required.
7. Use **Search** to filter a large catalogue if required.
8. Edit values or manage type rows where changes are required.
9. Run **Conform Catalogue** if the catalogue contains structural problems that Flow can safely correct.
10. Review any remaining validation issues.
11. Choose **Save** when the catalogue is ready.

Opening a catalogue does not alter the source file. Changes are written only when you save the catalogue or run an operation that explicitly updates it, such as **Conform Catalogue**.

!!! tip "Open directly from Content Browser"

    For library families, you can open the associated type catalogue directly from **Content Browser** rather than browsing to the `.txt` file manually.

---

## First-Time Workflow — Generate a Catalogue

You can generate a type catalogue in two ways.

### From an open Revit family

1. Open the required family in Revit.
2. Open **Type Catalogue Manager**.
3. Choose **Tools → Generate Catalogue**.
4. Select the parameters to include.
5. Use a parameter preset where appropriate.
6. Choose **Generate**.
7. Select the catalogue file location.
8. Review the generated catalogue and its validation results.

### From Content Browser

1. Locate the required library family in **Content Browser**.
2. Choose **Generate Type Catalog**.
3. Select the parameters to include.
4. Choose **Generate**.
5. Confirm the catalogue destination or replacement where required.
6. Review the generated catalogue in **Type Catalogue Manager**.

Content Browser handles the temporary family-opening process automatically.

See [**Generating Catalogues**](generating-catalogues.md) for the complete workflow.

---

## What Flow Does Automatically

When a catalogue is opened or generated, Flow:

* reads the catalogue header and type rows;
* displays the first catalogue field as **Type Name**;
* preserves the Revit data type and unit information stored in parameter headers;
* validates the catalogue;
* populates the **Validation** panel;
* updates the **Inspector** as rows are selected.

During catalogue generation, Flow also:

* creates one catalogue row for each family type;
* filters out parameters that are not suitable type-catalogue inputs;
* provides category-relevant saved presets where available;
* loads the generated catalogue back into the Manager for review.

---

## Important Limitations

Type Catalogue Manager manages the contents and structure of a type catalogue. It does **not** compare an opened catalogue against the complete parameter definition of its Revit family.

In particular, validation does not confirm that:

* every catalogue parameter still exists in the family;
* every eligible family parameter has been included;
* a parameter name should be automatically replaced with a different family parameter;
* catalogue values produce the intended family geometry after loading.

For generated catalogues, review the finished file before treating it as final library content.

---

## What do you want to do?

### Open and Review a Catalogue

Open an existing `.txt` type catalogue, search its contents, inspect individual rows and review identified problems.

➡️ [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)

### Edit a Catalogue

Change catalogue values or add, duplicate and remove type rows.

➡️ [**Editing Catalogues**](editing-catalogues.md)

### Check a Catalogue

Review validation issues including empty values, duplicate type names and catalogue-header problems.

➡️ [**Validation and Inspection**](validation-and-inspection.md)

### Clean Up a Catalogue

Use **Conform Catalogue** to correct structural problems that can be resolved safely and identify rows that still require attention.

➡️ [**Conforming Catalogues**](conforming-catalogues.md)

### Generate a Catalogue

Create a new type catalogue from the types and selected parameters in a Revit family.

➡️ [**Generating Catalogues**](generating-catalogues.md)

### Having Problems?

Use the troubleshooting checks if a catalogue cannot be opened, generated, saved or conformed as expected.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Related Help

* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Generating Catalogues**](generating-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)

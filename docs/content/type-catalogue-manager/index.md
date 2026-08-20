# Type Catalogue Manager

The **Type Catalogue Manager** provides tools for creating, reviewing, editing and maintaining Revit family type catalogues.

Use it to open an existing catalogue, review and edit type data, identify validation problems, conform catalogue structure, or generate a new catalogue from a Revit family.

---

## Open Type Catalogue Manager

On the Revit ribbon:

**Flow → Content → Types**

You can also find **Type Catalogue Manager** through the **Command Palette**.

---

## What do you want to do?

### Open and Review a Catalogue

Open an existing `.txt` type catalogue, search its contents, inspect individual rows and review any identified problems.

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

Create a new type catalogue directly from the types and selected parameters in a Revit family.

➡️ [**Generating Catalogues**](generating-catalogues.md)

### Having Problems?

Use the troubleshooting checks if a catalogue cannot be opened, generated, saved or conformed as expected.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Type Catalogue Manager at a Glance

A typical existing-catalogue workflow is:

1. Open **Type Catalogue Manager**.
2. Open the required type catalogue.
3. Review the catalogue grid and validation results.
4. Search or inspect the catalogue as required.
5. Edit catalogue values or manage type rows.
6. Use **Conform Catalogue** where structural clean-up is required.
7. Review any remaining validation issues.
8. Save the updated catalogue.

!!! tip "Open directly from Content Browser"

	For library families, you can open the associated type catalogue directly from **Content Browser** rather than browsing to the `.txt` file manually.

	Content Browser also provides actions for generating and conforming type catalogues.

---

## Catalogue Generation

Type Catalogue Manager can also build a catalogue from an existing Revit family.

During generation you can choose which eligible family parameters are included and use saved parameter presets to speed up common selections.

Formula-driven and reporting parameters are excluded automatically because they cannot be driven through the generated type catalogue.

See [**Generating Catalogues**](generating-catalogues.md).

---

## Related Help

* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Generating Catalogues**](generating-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)

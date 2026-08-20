# Conforming Catalogues

Use **Conform Catalogue** to clean up common structural problems within an existing type catalogue.

Conform makes corrections that Flow can apply safely and identifies remaining problems that require review.

---

## Before Conforming

Open the required catalogue in **Type Catalog Manager**.

Review the current validation results before running Conform so you understand the existing catalogue condition.

---

## Conform the Catalogue

From Type Catalog Manager:

1. Open the **Tools** controls.
2. Choose **Conform Catalogue**.
3. Allow Flow to inspect and clean up the catalogue.
4. Review the **Conform Complete** result.
5. Review any remaining warnings or problem rows.

Where Conform makes changes, the updated catalogue is written back to the current file.

Existing catalogue parameter definitions, including their Revit data type and unit information, are preserved during the Conform process.

---

## What Conform Can Fix

Depending on the catalogue contents, Conform can:

* rename an unnamed first column to **Type Name**;
* remove duplicate catalogue columns;
* add missing value cells required by the defined columns;
* remove orphaned values that no longer correspond to a catalogue column;
* trim whitespace from column names;
* remove completely empty catalogue rows.

The result identifies the corrections made.

!!! info "Catalogue definitions are preserved"

    Conform cleans up the catalogue structure without removing the Revit data type and unit information contained in existing parameter headers.

---

## Problems That Are Not Automatically Fixed

Some problems require a decision about the intended catalogue data.

Conform identifies these rather than guessing how they should be corrected.

This includes:

### Blank Type Names

A row without a Type Name is identified as a problem row.

Enter the intended Type Name manually.

### Duplicate Type Names

If the same Type Name is used more than once, Conform identifies the duplicate and reports where that name was first used.

Rename or remove the appropriate row manually.

!!! warning "Conform does not invent catalogue data"

	Flow only applies corrections that can be made safely from the existing catalogue structure.

	It does not create missing Type Names or decide how duplicate types should be renamed.

---

## Review the Conform Result

After the operation, the result can contain:

**Fixed**
Structural corrections applied to the catalogue.

**Warnings**
Problems that require review.

**Problem Rows**
Rows requiring user attention.

If nothing needs to be changed, Flow reports:

**No changes required.**

---

## Review Highlighted Rows

Where Conform identifies problem rows, Type Catalog Manager highlights the affected rows and moves to the first identified problem.

Review those rows and make the required corrections.

---

## Validation After Conforming

Type Catalog Manager validates the catalogue again after the Conform operation.

Review the **Validation** panel for any remaining issues.

See [**Validation and Inspection**](validation-and-inspection.md).

!!! tip "Use Conform before manual clean-up"

	If a catalogue contains several structural problems, run **Conform Catalogue** first.

	Flow can resolve the safe structural corrections, leaving you to concentrate on issues that actually require a decision.

---

## Conform from Content Browser

Type catalogues can also be conformed from **Content Browser**.

For a selected family with an associated type catalogue, use the catalogue conform action.

If no associated `.txt` catalogue is found, Flow reports that no type catalogue is available for the family.

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Troubleshooting**](troubleshooting.md)
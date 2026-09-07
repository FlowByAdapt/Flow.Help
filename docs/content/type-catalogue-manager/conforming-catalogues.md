# Conforming Catalogues

Use **Conform Catalogue** to clean up common structural problems within an existing type catalogue.

Conform applies corrections that Flow can make safely and identifies remaining problems that require a user decision.

---

## Before Conforming

Open the required catalogue in **Type Catalogue Manager** and review the current validation results.

Conform can write changes back to the catalogue, so use it as an intentional clean-up operation rather than as a read-only check.

---

## Conform the Catalogue

From Type Catalogue Manager:

1. Open the **Tools** menu.
2. Choose **Conform Catalogue**.
3. Allow Flow to inspect the catalogue.
4. Review the **Conform Complete** result.
5. Review any remaining warnings or problem rows.
6. Review the refreshed **Validation** panel.

Where Conform makes changes, the updated catalogue is written to the current file and a backup is created before the existing file is replaced.

Existing Revit data type and unit information contained in catalogue parameter headers is preserved.

---

## What Conform Can Fix

Depending on the catalogue contents, Conform can safely correct structural conditions including:

* an unnamed first catalogue column that should represent **Type Name**;
* duplicate catalogue columns;
* missing row cells required by the catalogue header;
* values that no longer correspond to a valid catalogue column;
* unintended whitespace in column names;
* completely empty catalogue rows.

The Conform result identifies the corrections applied.

!!! info "Conform protects catalogue definitions"

    Structural clean-up preserves the Revit data type and unit information stored in existing parameter headers.

---

## Problems That Require Manual Review

Some conditions cannot be corrected safely without knowing the intended catalogue data.

### Blank Type Names

A row without a Type Name is identified for review.

Enter the intended Type Name manually or remove the row if it should not exist.

### Duplicate Type Names

If the same Type Name is used more than once, Flow identifies the duplicates.

Rename or remove the appropriate row manually.

!!! warning "Conform does not invent catalogue data"

    Flow applies only corrections that can be derived safely from the existing catalogue structure.

    It does not invent missing Type Names, decide which duplicate type should remain, or replace catalogue parameters with different family parameters.

---

## Review the Conform Result

The result separates the outcome into information such as:

**Fixed**

Structural corrections that were applied automatically.

**Warnings**

Conditions that still require review.

**Problem Rows**

Rows requiring user attention.

If no structural changes or unresolved problems are found, Flow reports:

**No changes required.**

Warnings and problem rows are still shown where attention is required even when no automatic correction was necessary.

<!-- SCREENSHOT: Conform result.
Use a catalogue with at least one automatically correctable structural issue
and one user-decision issue such as a duplicate Type Name.
Show the result and the highlighted problem row. -->

---

## Review Highlighted Rows

Where Conform identifies problem rows, Type Catalogue Manager navigates to the affected catalogue data.

Correct the remaining issues manually, then review the **Validation** panel again.

---

## Conform from Content Browser

Type catalogues can also be conformed from **Content Browser**.

For a selected family with an associated catalogue:

1. choose the catalogue conform action;
2. Flow resolves the associated `.txt` file;
3. Flow runs the conform process;
4. the Manager opens when review or user action is required.

If no catalogue is associated with the family, Flow reports that no type catalogue was found.

---

## When Not to Use Conform

Conform is not a family-to-catalogue synchronisation tool.

It does not:

* rebuild a catalogue from the family;
* add family parameters that are missing from the catalogue;
* determine that a catalogue parameter should be renamed to a different family parameter;
* confirm that catalogue values create the intended family geometry.

If the catalogue needs to be rebuilt from the family, use [**Generating Catalogues**](generating-catalogues.md).

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Validation and Inspection**](validation-and-inspection.md)
* [**Troubleshooting**](troubleshooting.md)

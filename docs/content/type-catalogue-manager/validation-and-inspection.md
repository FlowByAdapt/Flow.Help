# Validation and Inspection

Type Catalogue Manager automatically checks catalogue structure and values to help identify common problems.

Validation reports problems without changing the catalogue.

---

## When Validation Runs

Validation runs automatically when a catalogue is opened or generated and is refreshed as catalogue data is changed through the Manager.

You do not need to run a separate validation command.

The **Validation** panel always represents the current catalogue state shown in the Manager.

---

## Review Validation Results

Each validation issue includes:

* a severity;
* a description of the problem;
* the affected row, where applicable;
* the affected column, where applicable.

If no problems are found, the Validation panel reports:

**No validation issues found.**

---

## Validation Errors

An **Error** identifies a problem that should be corrected before relying on the catalogue.

Typical errors include:

### Empty Column Headers

A catalogue column does not have a valid header.

### Duplicate Column Headers

The same column header occurs more than once.

Duplicate headers make the intended catalogue structure ambiguous and should be corrected.

### Duplicate Type Names

Two or more catalogue rows use the same **Type Name**.

Each affected duplicate Type Name is identified.

!!! warning "Errors require attention"

    Errors indicate structural or type-identification problems that should be resolved before the catalogue is treated as complete.

---

## Validation Warnings

A **Warning** identifies a condition that requires review but may not always be incorrect.

Typical warnings include:

* a row that does not contain a value for an expected column;
* an empty value in a catalogue column;
* other incomplete row data that requires user review.

An empty value can be intentional in some catalogue structures, so review the affected row before deciding whether it needs to be changed.

---

## Navigate to a Problem

Select an item in the **Validation** panel.

Where the issue relates to a particular row, Type Catalogue Manager selects and scrolls to that row.

Where a column is also identified, Flow navigates to the affected cell.

This allows validation results to be checked directly against the catalogue data.

<!-- SCREENSHOT: Validation navigation.
Show a selected Validation item, the corresponding selected grid cell/row,
and the row information in the Inspector. -->

---

## Inspect the Selected Row

Select any catalogue row to display its information in the **Inspector**.

The Inspector shows:

1. validation issues associated with the selected row, where present; and
2. the values contained in each catalogue column for that row.

Use the Inspector when reviewing a wide catalogue or when several issues affect the same type.

---

## Correct an Issue

The appropriate correction depends on the problem.

For example:

* give duplicate types unique Type Names;
* enter a missing value where one is required;
* correct an invalid or duplicate header;
* remove a row that should not exist.

For catalogue-structure issues that Flow can resolve safely, use **Conform Catalogue**.

See [**Conforming Catalogues**](conforming-catalogues.md).

---

## Validation and Conform Are Different

**Validation** identifies problems and does not change the catalogue.

**Conform Catalogue** can change the catalogue by applying safe structural corrections.

Conform does not guess values where a user decision is required. For example, it will not invent a missing Type Name or decide how duplicate types should be renamed.

---

## What Validation Does Not Check

Validation checks the catalogue itself. It is not a full comparison between the catalogue and the source Revit family.

It does not confirm that:

* every catalogue parameter exists in the family;
* every eligible family parameter has been included;
* catalogue values create the intended geometry when loaded into Revit.

Where family compatibility is important, test the finished catalogue with the intended family.

---

## Related Help

* [**Type Catalogue Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)

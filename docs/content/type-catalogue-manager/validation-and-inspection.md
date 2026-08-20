# Validation and Inspection

Type Catalog Manager automatically checks catalogue structure and values to help identify common problems.

Validation reports problems without changing the catalogue.

---

## Review Validation Results

Open the required catalogue in **Type Catalog Manager**.

The **Validation** panel displays the issues identified in the catalogue.

Each issue includes:

* a severity;
* a description of the problem;
* the affected row, where applicable;
* the affected column, where applicable.

If no problems are found, the Validation panel reports:

**No validation issues found.**

---

## Validation Errors

Type Catalog Manager reports an **Error** when it identifies problems including:

### Empty Column Headers

A catalogue column does not have a valid header.

### Duplicate Column Headers

The same column header occurs more than once.

### Duplicate Type Names

Two or more catalogue rows use the same **Type Name**.

Each affected duplicate Type Name is identified.

!!! warning "Errors require attention"

	Errors indicate structural or identification problems that should be resolved before relying on the catalogue.

---

## Validation Warnings

Type Catalog Manager reports a **Warning** where a catalogue row:

* does not contain a value for an expected column; or
* contains an empty value in a catalogue column.

An empty value may be intentional in some catalogues, so review the affected row before deciding whether a change is required.

---

## Navigate to a Problem

Select an item in the **Validation** panel.

Where the issue relates to a particular row, Type Catalog Manager selects and scrolls to that row.

Where a column is also identified, Flow navigates to the affected cell.

This allows validation results to be reviewed directly against the catalogue data.

---

## Inspect the Selected Row

Select any catalogue row to display its information in the **Inspector**.

The Inspector shows:

1. validation issues associated with the selected row, where present; and
2. the values contained in each catalogue column for that row.

Use the Inspector when you need to review a type without moving across a wide catalogue grid.

---

## Validation After Editing

Validation is refreshed when row operations are performed and during other catalogue-management workflows.

After making corrections, review the Validation panel again to confirm whether the identified issue remains.

---

## Validation and Conform Are Different

**Validation** identifies problems.

**Conform Catalogue** can automatically correct selected structural problems that can be resolved safely.

It does not automatically resolve problems that require a user decision, such as choosing a unique Type Name.

See [**Conforming Catalogues**](conforming-catalogues.md).

!!! info "Review warnings in context"

	Not every warning necessarily means the catalogue is unusable.

	Validation highlights conditions that should be reviewed so you can decide whether the value is intentionally blank or requires correction.

---

## Related Help

* [**Type Catalog Manager**](index.md)
* [**Opening and Reviewing Catalogues**](opening-and-reviewing.md)
* [**Editing Catalogues**](editing-catalogues.md)
* [**Conforming Catalogues**](conforming-catalogues.md)
* [**Troubleshooting**](troubleshooting.md)
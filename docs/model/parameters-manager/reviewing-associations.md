# Reviewing Associations

Use **Review Associations** to inspect the Global Parameter associations found on one Revit element and its type. This is a read-only workflow and makes no changes to the project.

**Ribbon:** Flow → Content → Parameters Manager

---

## When to Use This Tool

Review an element before you:

- Copy its GP setup to other elements
- Remove an association
- Investigate an unexpected parameter value
- Check whether an association belongs to the instance or the type
- Confirm why a Global Parameter is controlling multiple elements

---

## Review an Element

1. Open **Parameters Manager**.
2. Expand **Associations**.
3. Select **Review Associations**.
4. Pick one element in the Revit canvas.
5. Review the associations shown in the **Global Parameter Review** window.
6. Select **Close** when finished.

Parameters Manager temporarily hides while Revit is waiting for the selection. It returns after you pick an element or cancel the selection.

<!-- SCREENSHOT: A representative window selected in Revit immediately after starting Review Associations. -->

---

## Understanding the Results

The review window identifies the selected element by category and, where available, its **Mark**.

The summary reports the number of GP associations found. The grid shows:

| Column | Description |
| --- | --- |
| **Parameter** | Name of the associated Revit parameter. |
| **Global Parameter** | Name of the GP controlling that parameter. |
| **Scope** | Whether the association belongs to the selected **Instance** or its shared **Type**. |
| **Type** | Revit storage type reported for the associated parameter. |

Results are ordered with instance associations before type associations, then by parameter name.

<!-- SCREENSHOT: Global Parameter Review window containing both Instance and Type rows. Ensure all four columns and the summary count are visible. -->

---

## Instance and Type Associations

### Instance

An **Instance** association belongs to the individual selected element.

Changing the associated GP can still affect other elements when those elements are also connected to the same GP, but the association itself is stored on this instance.

### Type

A **Type** association belongs to the selected element's Revit type.

Other instances using that type share the same type parameter and can therefore be affected by changes to the association or its controlling GP.

!!! warning "Check the scope before making changes"

	Review the **Scope** column carefully before using **Remove Associations** or **Copy GP Setup**. Changing a type association can affect more elements than the one you selected.

---

## What Flow Checks

Flow inspects:

1. Parameters on the selected element instance
2. Parameters on the element's Revit type, when a type exists

Flow includes parameters for which Revit reports an associated Global Parameter. Duplicate records with the same parameter name, GP name and scope are consolidated in the review.

Some Revit parameters cannot report GP association information through the API. Flow skips those parameters and continues the review.

---

## Expected Result

If associations are found, a modal review window opens and lists them. Closing the window returns you to Parameters Manager without changing anything.

If no associations are found, Flow displays:

> No global parameter associations were found on the selected element.

No project changes are made in either case.

---

## Cancel the Selection

Press **Esc** while Revit is waiting for an element.

Parameters Manager returns without opening the review window or changing the project.

---

## If an Expected Association Is Missing

Check the following:

1. Confirm that you selected the intended element.
2. Check whether the parameter supports Global Parameter associations.
3. Confirm that the association exists in Revit's native properties or Global Parameters tools.
4. Use **Audit → Refresh Dashboard** if you are comparing the result with dashboard counts.
5. Use **GP Audit** if you need to compare several elements.

Remember that Review Associations reports current associations. It does not assess whether each association matches a Flow preset or office standard.

---

## Related Help

- [Parameters Manager](index.md)
- [Copying GP Setup](copying-gp-setup.md)
- [Removing Associations](removing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

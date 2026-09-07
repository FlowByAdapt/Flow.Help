# Reviewing Global Parameters

Use the **Opening GP Dashboard** to review the Global Parameters included in the current Parameters Manager scope, check their displayed values, and see whether Flow detected any associations.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Open the Revit project you want to inspect. Parameters Manager requires an active project and scans that project when the window opens.

The dashboard is intended as a quick review tool. It does not replace Revit's native Global Parameters interface when you need to inspect every project GP or confirm a type-only association.

---

## Open the Dashboard

1. On the Revit ribbon, select **Flow → Content → Parameters Manager**.
2. Wait for the initial project scan to complete.
3. Review the three summary cards and the dashboard grid.

If Parameters Manager is already open, launching it again activates the existing window.

<!-- SCREENSHOT: Complete Parameters Manager window after its initial scan. Show all three summary cards and several representative dashboard rows. -->

---

## Dashboard Summary

The three summary cards also act as grid filters.

### Total GPs

Shows every Global Parameter included in the Opening GP Dashboard.

Select **Total GPs** to clear an Associated or Unused filter and restore the complete dashboard list.

### Associated

Shows Global Parameters with one or more associations detected during the dashboard scan.

### Unused

Shows Global Parameters for which the dashboard scan detected no associations.

Select any card to filter the grid. The dashboard subtitle reports the number of rows currently shown.

<!-- SCREENSHOT: Dashboard filtered by Associated or Unused, with the selected result count visible in the subtitle. -->

!!! warning "Unused does not always mean safe to delete"

	The dashboard scans parameters on non-type elements. A Global Parameter used only through a type-parameter association may not be detected and can appear **Unused**.

	Treat **Unused** as a review status, not an instruction to delete the GP. Confirm unfamiliar parameters with **Review Associations** or Revit's native Global Parameters tools before removing them.

---

## Review the Grid

| Column | Description |
| --- | --- |
| **GP Name** | Global Parameter name. |
| **Type** | Value type reported by Flow. |
| **Current Value** | Displayed value and, where supported, an editable value. |
| **Associations** | Number of associations detected during the current dashboard scan. |
| **Status** | **Associated** when the detected count is greater than zero; otherwise **Unused**. |

Rows are sorted alphabetically by GP name.

Supported type descriptions include:

- **Text**
- **Length / Number**
- **Integer / Yes-No**
- **Element**
- **Unknown**

Some **Current Value** cells can be edited directly. Editable values display an edit indicator.

See [Editing Global Parameter Values](editing-global-parameter-values.md) before changing a value for the first time.

---

## Dashboard Scope

The dashboard intentionally omits a fixed group of office graphics and project-control Global Parameters that sit outside its opening-focused scope.

As a result:

- **Total GPs** is not the total number of Global Parameters stored in Revit.
- A GP missing from the dashboard may still exist in the project.
- Revit's native Global Parameters editor remains the authoritative place to inspect the complete project list.

Use **Maintenance → Open Native GP Editor** when you need the full Revit interface.

---

## Refresh the Dashboard

The dashboard scans automatically when Parameters Manager opens. It does not automatically rescan after every Parameters Manager operation.

To update it manually:

1. Expand **Audit**.
2. Select **Refresh Dashboard**.
3. Wait for the summary cards and grid to update.

Refresh after:

- Editing a GP value
- Copying or removing associations
- Applying window or door standards
- Applying existing-window standards
- Importing office-standard GPs
- Making relevant changes through Revit's native editor

Confirmed unused-GP cleanup refreshes the dashboard automatically after deletion.

---

## Expected Result

After the scan, the dashboard shows:

- The GPs included in its current scope
- Each GP's reported type and displayed value
- The number of associations detected by this scan
- An **Associated** or **Unused** status

Selecting a summary card changes only the displayed filter. It does not change the Revit project.

---

## Important Limitations

- The dashboard does not show every project Global Parameter.
- Type-only associations may not be included in association counts.
- A GP can therefore appear **Unused** despite having a type-parameter association.
- The dashboard reports whether an association was detected; it does not verify that an element is associated with the correct GP.
- Association counts can become stale until the dashboard is refreshed.
- Double values are displayed as degrees when the GP name contains **Angle**; other double values are displayed as millimetres.

---

## If a Result Looks Wrong

If a GP is missing, appears unused unexpectedly, or has an unexpected count:

1. Select **Refresh Dashboard**.
2. Confirm that the correct Revit project is active.
3. Use **Review Associations** on a representative element.
4. Check whether the association belongs to the element's type.
5. Open Revit's native Global Parameters editor if further confirmation is required.

See [Parameters Manager Troubleshooting](troubleshooting.md) if the issue continues.

---

## Related Help

- [Parameters Manager](index.md)
- [Editing Global Parameter Values](editing-global-parameter-values.md)
- [Reviewing Associations](reviewing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Native Global Parameter Editor](native-global-parameter-editor.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

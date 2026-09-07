# Auditing Global Parameters

Use **GP Audit** to compare the number of Global Parameter associations detected on selected elements with the expected count configured by the current audit rules.

The present audit is calibrated primarily for Revit windows. It is a count-based review, not a full validation of which GP is connected to each parameter.

**Ribbon:** Flow → Content → Parameters Manager

---

## When to Use GP Audit

Use GP Audit to:

- Find windows with no GP associations
- Identify windows whose association count is below the current expected count
- Compare several selected windows in one results grid
- Identify elements for closer inspection with **Review Associations**

Do not use a **Complete** status as proof that every association matches the correct Flow preset.

---

## Audit One Element

1. Open **Parameters Manager**.
2. Expand **Audit**.
3. Select **GP Audit**.
4. At **Audit multiple elements?**, choose **No**.
5. Pick one element in Revit.
6. Review the result in the **Global Parameter Audit** window.
7. Select **Close** when finished.

Parameters Manager temporarily hides while Revit is waiting for the selection and returns afterward.

---

## Audit Multiple Elements

1. Open **Parameters Manager**.
2. Expand **Audit**.
3. Select **GP Audit**.
4. At **Audit multiple elements?**, choose **Yes**.
5. Pick the required elements in Revit.
6. Finish the Revit multi-selection.
7. Review the result grid.
8. Select **Close** when finished.

Duplicate selections are consolidated before the audit runs.

<!-- SCREENSHOT: Audit multiple elements prompt showing Yes = Multiple Elements and No = Single Element. -->

---

## Review the Audit Grid

The audit window shows:

| Column | Description |
| --- | --- |
| **Category** | Revit category of the selected element. |
| **Mark** | Value of the element's Mark parameter, when available. |
| **Family / Type** | Family and type for family instances, or the resolved type name for other elements. |
| **GP Count** | Number of distinct instance and type GP associations detected. |
| **Status** | Result of comparing the detected count with the expected count. |

Rows are ordered by Category, then Mark, then Family/Type.

<!-- SCREENSHOT: Global Parameter Audit window showing representative Complete, Missing and Not Configured windows. Keep the Category, Mark, Family/Type, GP Count and Status columns visible. -->

---

## Audit Statuses

### Not Configured

The element has an expected association count greater than zero, but no GP associations were detected.

### Missing _n_

The detected association count is below the configured expected count. The number reports the difference between expected and detected associations.

### Complete

The detected count meets or exceeds the configured expected count.

### Not Required

The audit has no expected association count configured for the selected category.

The current rules use an expected count of **19** for elements whose category name is **Windows**. Doors, Curtain Walls and other categories currently have an expected count of zero and are reported as **Not Required**.

!!! warning "Complete is a quantity check"

	**Complete** means that the detected association count is at least the configured expected count. GP Audit does not confirm that the correct parameters are associated with the correct Global Parameters.

	A window can therefore meet the count while still containing an incorrect, unrelated or outdated association.

---

## What Flow Checks

For each selected element, Flow:

1. Inspects parameters on the element instance.
2. Inspects parameters on its Revit type, when available.
3. Consolidates duplicate records with the same parameter name, GP name and scope.
4. Counts the discovered associations.
5. Retrieves the expected count for the element category.
6. Calculates the missing count.
7. Assigns the audit status.

Parameters that cannot report GP association information through the Revit API are skipped.

---

## Expected Result

GP Audit opens a read-only modal window. It does not add, change or remove associations.

Use the results to identify elements requiring closer review:

- **Not Configured** — review the element and consider the relevant setup workflow.
- **Missing _n_** — inspect the exact missing or incorrect mappings with **Review Associations**.
- **Complete** — treat as an initial count check, then review exact mappings where compliance matters.
- **Not Required** — no meaningful expected count is currently configured for that category.

---

## Known Summary Limitation

The current summary sentence above the audit grid counts older status names that are no longer produced by the audit service. It may therefore report zero for its summary categories even when the grid contains valid rows.

Use each row's **GP Count** and **Status** as the current audit result.

!!! note "Current window preset counts"

	The audit currently expects 19 associations for a window. Some active Flow window presets can define a different number of potential associations, depending on supported family parameters and wall-type-specific rules.

	GP Audit should therefore be treated as a diagnostic count rather than definitive preset compliance.

---

## Cancel the Selection

Press **Esc** while Revit is waiting for an element or multi-selection.

The audit closes without opening a results window or changing the project.

---

## Refresh the Dashboard

**GP Audit** and **Refresh Dashboard** are separate commands.

- **GP Audit** reviews selected elements in a dedicated results window.
- **Refresh Dashboard** rescans the project-level dashboard counts.

To refresh the dashboard:

1. Expand **Audit**.
2. Select **Refresh Dashboard**.

The dashboard also performs an initial scan when Parameters Manager opens.

---

## If a Result Is Unexpected

1. Confirm that you selected the intended element.
2. Check whether its category is **Windows**.
3. Use **Review Associations** to inspect the exact instance and type mappings.
4. Check whether the window family omits optional parameters included in the standard preset.
5. Check whether unrelated associations are contributing to the count.
6. Run the appropriate Window Standards workflow if setup is incomplete.
7. Refresh the dashboard after making changes.

---

## Current Limitations

- The expected-count rule is currently meaningful only for Windows.
- Window completeness uses a fixed expected count of 19.
- The audit checks association quantity, not mapping correctness.
- Additional unrelated associations can satisfy the expected count.
- Different window presets or family capabilities can involve different potential mappings.
- The audit summary sentence currently uses outdated status categories.
- Category recognition uses the displayed Revit category name.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Associations](reviewing-associations.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Applying Window Standards](applying-window-standards.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

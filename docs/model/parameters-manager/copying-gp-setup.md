# Copying GP Setup

Use **Copy GP Setup** to copy Global Parameter associations from one configured source element to one or more target elements with matching parameters.

**Ribbon:** Flow → Content → Parameters Manager

---

## When to Use This Tool

Use Copy GP Setup when:

- One element already has the required GP associations
- Other elements have matching Revit parameters
- You want to reproduce both supported instance and type associations

This workflow copies associations. It does not copy every parameter value, family type or property from the source element.

---

## Before You Start

Choose a source element whose GP setup you trust.

If you are unsure which associations it contains:

1. Open **Parameters Manager**.
2. Expand **Associations**.
3. Run **Review Associations** on the intended source.
4. Confirm the GP names and whether each association is an **Instance** or **Type** association.

!!! warning "Type associations"

	A copied type association is applied to the target element's Revit type. Other instances using that target type can therefore be affected.

---

## Copy the Setup

1. Open **Parameters Manager**.
2. Expand **Associations**.
3. Select **Copy GP Setup**.
4. Pick the source element first.
5. Pick one or more target elements.
6. Finish the Revit multi-selection.
7. Review the completion message.
8. Select **Audit → Refresh Dashboard** if you want to update the dashboard counts.

Parameters Manager temporarily hides while Revit is waiting for the source and target selections. It returns after the selection is completed or cancelled.

The copy starts immediately when target selection finishes. There is no separate preview or confirmation window.

<!-- SCREENSHOT: Revit canvas showing one clearly identified source element and several intended target elements. Use callouts to make the source-first order unambiguous. -->

---

## What Flow Copies

Flow discovers GP associations on:

- The source element instance
- The source element's Revit type

For each source association, Flow looks for a target parameter with the same name and uses the GP with the same name as the source association.

### Instance Associations

An instance association is applied to the matching parameter on each target element.

### Type Associations

A type association is applied to the matching parameter on each target element's type.

If several selected targets use the same type, they share the resulting type association.

---

## What Flow Does Automatically

For every source-association and target-element combination, Flow:

1. Finds the source GP in the current project.
2. Resolves the target instance or type according to the source scope.
3. Finds the target parameter by name.
4. Checks whether the parameter is read-only.
5. Checks its current GP association.
6. Checks whether Revit allows the requested association.
7. Applies the association when compatible.

All target attempts run inside one Revit transaction. An individual incompatible association is skipped while other valid associations continue.

---

## Associations Flow Does Not Replace

Flow does not overwrite a target parameter that already has a different GP association.

The target attempt is skipped when:

- The required GP cannot be found
- The target or target type cannot be resolved
- No matching parameter exists
- The parameter is read-only
- A different GP is already associated
- Revit reports that the parameter and GP are incompatible
- Revit rejects the association

If the target parameter is already associated with the required GP, Flow leaves it unchanged and treats that attempt as successful.

---

## Completion Message

After processing, Flow reports:

| Result | Meaning |
| --- | --- |
| **Source Associations** | Number of distinct instance and type associations discovered on the source. |
| **Targets Processed** | Number of target elements Flow could resolve. |
| **Associations Applied** | Successful attempts, including targets that were already associated with the required GP. |
| **Skipped / Not Applied** | Missing, read-only, conflicting, incompatible or failed attempts. |

<!-- SCREENSHOT: Copy Global Parameters completion message showing all four result counts. -->

!!! note "Applied does not always mean newly changed"

	A target already associated with the required GP is included as a successful applied result even though Flow did not need to change it.

The current completion window shows totals rather than the stored per-target detail records. If the skipped count is unexpected, review a representative target directly.

---

## Expected Result

Compatible target parameters are associated with the same GPs used by the source element.

After refreshing the dashboard, affected GPs may show updated association counts. Check representative target elements in Revit to confirm the intended result, especially where type associations were copied.

---

## Cancel the Workflow

Press **Esc** while Revit is waiting for either the source or target selection.

If the selection is cancelled before the target selection is completed, no copy request is submitted and the project remains unchanged.

---

## If the Expected Setup Is Not Applied

1. Run **Review Associations** on the source and confirm that it contains the expected associations.
2. Confirm that the target has parameters with matching names.
3. Check whether the association belongs on the target instance or type.
4. Check whether the target parameter already has a different GP association.
5. Review the **Skipped / Not Applied** count.
6. Run **Review Associations** on a representative target.
7. Refresh the dashboard after checking the result.

---

## Current Limitations

- There is no preview or association-selection stage before copying.
- Parameters are matched by name.
- Existing conflicting GP associations are preserved rather than replaced.
- The completion dialog provides totals, not per-target failure details.
- Type associations affect the target type and potentially every instance using it.
- Copy GP Setup does not validate the result against a Flow window or door preset.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Associations](reviewing-associations.md)
- [Removing Associations](removing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

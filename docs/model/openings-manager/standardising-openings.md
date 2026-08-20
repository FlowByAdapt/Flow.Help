# Standardising Openings

Use **Standardise** to bring opening marks into the Flow standard and synchronise associated opening view names.

This is useful before generating or updating opening documentation.

---

## What Standardise Does

Standardise checks the selected openings and corrects marks that do not follow the expected Flow marking system.

The standard mark groups are:

| Opening | New | Existing |
| --- | --- | --- |
| Window | `W##` | `Wx##` |
| Curtain Wall | `W##` | `Wx##` |
| Door | `D##` | `Dx##` |

Standardise also synchronises opening view names after the mark changes have been applied.

!!! info "Standardise affects marks and view names"

    Standardise is not only a mark-cleanup command.

    After standardising the selected openings, Flow also checks the associated opening view names so that the documentation remains aligned with the current marks.

---

## Standardise from Openings Manager

From the Openings Manager:

1. Review or filter the opening register.
2. Click **Standardise**.
3. Choose the required scope.
4. Confirm the operation.
5. Allow Flow to update the selected openings.
6. Review the completion message.

Depending on the current register state, the available scope can include checked, filtered or all openings.

---

## Standardise as a Standalone Command

When **Standardise Openings** is launched outside the Openings Manager, Flow offers:

- **Visible in Active View**
- **All Openings**
- **Cancel**

Choose **Visible in Active View** when you only want to process openings visible in the current Revit view.

Choose **All Openings** to process the complete project opening set.

---

## If the Openings Are Already Standard

If the selected openings already meet the required standard, Flow does not unnecessarily change them.

The completion message reports that the selected openings were already standardised.

---

## Standardise Before Generating Views

Generate Opening Views requires the selected openings to use standard marks.

If non-standard openings are found when you run Generate Views, Flow stops the generation workflow and offers:

**Standardise Now**

or:

**Cancel**

If you choose **Standardise Now**, Flow runs the standardisation workflow before you continue with opening documentation.

!!! tip "Standardise first"

    For a new documentation run, it is usually easier to resolve opening marks before generating views.

    This keeps the opening register, marks and generated view names aligned from the beginning.

---

## View Name Synchronisation

Standardise also synchronises opening view names with the current opening information.

This is useful where:

- an opening mark has changed
- an existing opening view still uses an older mark
- opening numbering has been corrected after views were created

For more extensive view repair and standardisation, use **Conform Views**.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## When to Use Guided Renumber Instead

Standardise is appropriate when Flow can correct the existing opening marks automatically.

Use **Guided Renumber** instead when you need to control the actual numbering order by selecting openings from the model.

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## After Standardising

Refresh the Openings Manager register after significant changes if the dashboard has not already refreshed.

Check that:

- the required openings now have standard marks
- duplicate or mark-related issues have been resolved
- associated opening view names are correct
- the openings are ready for the next documentation workflow

---

## Related Help

- [**Opening Marks**](opening-marks.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
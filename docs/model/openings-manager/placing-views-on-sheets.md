# Placing Opening Views on Sheets

Use **Place on Sheet** to arrange generated Window or Door elevations on their documentation sheets.

Window and Door placement use different workflows. Window placement includes persisted session memory and multi-sheet handling, while Door placement is a simpler single-sheet operation.

---

## Start Place on Sheet

From Openings Manager, click **Place on Sheet**.

Choose:

- **Window Views**
- **Door Views**

If a previous Window placement session exists, the workflow can also offer a reset option.

While placement is running from Openings Manager, the Manager is minimised so you can work directly on the Revit sheets. It is restored when the placement workflow finishes.

!!! note "Register checkboxes are not used"

    Place on Sheet does not use the checked rows in the Opening Register.

    Each placement workflow finds the eligible unplaced views itself.

---

# Window View Placement

Window placement is designed to arrange unplaced New W## opening elevations across the A4-series opening sheets.

This workflow includes placement memory so a large set of opening views can be placed over more than one session.

---

## Required Starting Sheet

The Window placement workflow requires the sheet:

```text
A401
```

Flow uses A401 as the reference and starting sheet for the Window placement sequence.

If A401 cannot be found, the automatic Window placement workflow cannot begin.

---

## Which Views Are Included?

Flow looks for unplaced opening elevation views using the New Window-style naming convention:

```text
W##
```

For example:

```text
W01
W02
W03
```

Views already placed on sheets are excluded.

Existing Window views using the `Wx##` convention are not part of this placement workflow.

Because Curtain Wall elevations also use the W## opening sequence, eligible New Curtain Wall views can participate in the Window placement workflow.

---

## Previous Window Placement Sessions

Flow stores Window placement progress.

If placement memory from an earlier session exists, you can continue working with that recorded session rather than starting the complete workflow again.

Depending on the current state, Flow can offer options such as:

- **Resume Placement**
- **Reset and Start Again**

This allows a large opening schedule to be completed progressively.

!!! info "Placement memory"

    Flow remembers which views it placed and the placement area used by the workflow.

    This memory is specific to the managed Window placement process.

<!-- SCREENSHOT: Window placement prompt showing Resume Placement / Reset and Start Again for a project with an existing session. -->

---

## Define the Placement Area

When a placement area is required, Flow activates the target sheet and asks you to pick:

1. **Top Left**
2. **Bottom Right**

These points define the sheet region available for automatic placement.

Flow uses the actual/estimated paper-space dimensions of the opening elevations when determining how they can be arranged rather than assuming that every viewport has the same size.

<!-- SCREENSHOT: A401 with the user defining the Top Left and Bottom Right placement area. -->

---

## Reuse the Previous Placement Area

After an area has been defined, Flow remembers it for the Window placement workflow.

When placement continues onto another sheet, Flow can offer to reuse that area.

This is useful when the A4-series sheets use the same titleblock and the opening-view region is intended to remain consistent from sheet to sheet.

You can choose a new area where the next sheet requires a different layout.

---

## Automatic Window Layout

Flow calculates which remaining views can fit inside the selected region and places them automatically.

The layout is based on the available sheet area and the paper-space size of the opening elevations.

Where possible, views are arranged into a consistent grid/row layout rather than simply being placed at arbitrary fixed offsets.

The managed placement workflow also records each successfully placed view so it can distinguish completed work from the views still remaining.

---

## Continue onto Additional Sheets

If views remain after the current sheet has been processed, Flow can continue the workflow.

The available actions can include:

- **Continue to Next Sheet**
- **Stop and Resume Later**
- **Reset Placement**

Choose **Continue to Next Sheet** to keep working through the A4-series sequence.

Choose **Stop and Resume Later** when the current placement should be retained but the remaining views will be dealt with in a later session.

---

## Creating the Next Window Sheet

Where another Window sheet is required, Flow can create the next A4-series sheet from A401.

The workflow uses A401 as the reference and duplicates it **with detailing** for the new sheet.

Flow then assigns the required A4-series sheet number while retaining the reference sheet setup needed by the opening documentation workflow.

This allows Window placement to continue without requiring every subsequent opening sheet to be prepared manually beforehand.

!!! important

    A401 is therefore more than just the first destination sheet. It is also the reference used by the managed Window sheet workflow.

---

## Stop and Resume Later

Choose **Stop and Resume Later** when you want to keep the completed placements but end the current run.

Flow retains the placement state so a later session can continue with the remaining unplaced views.

When **Place on Sheet → Window Views** is run again, the existing session can be resumed.

---

## Reset Window Placement

Use the reset option when the managed Window placement session should be discarded and restarted.

The reset workflow uses the stored placement information to remove the Window viewports created by that recorded session and clears the associated placement memory.

!!! warning "Reset does not delete the opening views or sheets"

    Reset removes the recorded **viewports** created by the managed placement session.

    It does not delete the underlying opening elevation views or the sheets themselves.

Use Reset only when you intend to rebuild the managed placement layout.

---

## Viewport Type

Where the Revit viewport type:

```text
No Title
```

is available, Flow uses it for placed Window views.

If the type is unavailable, placement can continue using the viewport state available to Revit rather than creating that type automatically.

---

## Sheet Outline Show

During Window placement, Flow can temporarily enable the Global Parameter:

```text
Sheet Outline Show
```

when it exists in the project.

This supports the sheet-placement workflow while the usable area is being defined and views are being arranged.

Flow then turns the sheet outline back off after the placement operation.

This is automatic behaviour; you do not need to toggle the Global Parameter manually for a normal placement run.

---

# Door View Placement

Door placement uses a separate, simpler workflow.

It does not use the persisted multi-sheet placement session used for Window views.

---

## Required Door Sheet

Flow looks for a sheet named exactly:

```text
Interior Opening Schedule
```

This sheet is used as the Door elevation placement target.

If the required sheet cannot be found, the Door placement workflow cannot proceed normally.

---

## Which Door Views Are Included?

Flow looks for unplaced Door elevation views whose names end with:

```text
-D
```

For example:

```text
01-D
02-D
03-D
```

Views that are already placed are excluded.

Door elevations are type-based, so the placement workflow is working with the generated Door type documentation views rather than every Door instance in the Opening Register.

---

## Define the Door Placement Area

Flow activates **Interior Opening Schedule** and asks you to pick:

1. **Top Left**
2. **Bottom Right**

The selected points define the region available for Door elevation placement.

Flow estimates the paper-space size of the Door elevations and places the views that fit within that region.

<!-- SCREENSHOT: Interior Opening Schedule showing the selected Door placement region and resulting Door elevation grid. -->

---

## Door Viewport Type

Where available, placed Door elevations use:

```text
No Title
```

as their viewport type.

The Door workflow also uses the project **Sheet Outline Show** Global Parameter during placement when that resource is available, returning it to the off state afterwards.

---

## Door Placement Limitations

Door placement does not currently use the same persisted multi-sheet session system as Window placement.

In particular, it does not:

- create a remembered Door placement session equivalent to Window placement
- automatically create additional Door schedule sheets
- provide the same Resume / Reset workflow

Flow places the eligible Door views that fit the selected schedule area and reports the resulting placement outcome.

---

## Window and Door Placement Compared

| Window Views | Door Views |
| --- | --- |
| Uses New `W##` views | Uses `-D` views |
| Starts from `A401` | Uses `Interior Opening Schedule` |
| Can continue across A4-series sheets | Uses the target schedule sheet |
| Can create the next A4-series sheet | Does not automatically create additional Door sheets |
| Stores placement-session progress | No equivalent persisted Door session |
| Can resume or reset the recorded session | No equivalent Resume / Reset workflow |
| Can reuse the previous placement area | Placement area is selected for the Door operation |

---

## Recommended Workflow

Before placing opening views:

1. Generate the required opening elevations.
2. Conform existing views where required.
3. Dimension the standard Window views.
4. Confirm that **A401** and/or **Interior Opening Schedule** exists for the workflow you need.
5. Click **Place on Sheet**.
6. Choose **Window Views** or **Door Views**.
7. Define or reuse the placement area.
8. Review the resulting sheet layout.
9. Continue or resume Window placement until the required views are placed.

➡️ [**Generating Opening Views**](generating-opening-views.md)

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

---

## If Window Placement Cannot Continue

Check that:

- **A401** exists
- eligible `W##` views exist
- the views are not already placed
- the selected placement area is large enough
- the project has not been left in an unexpected previous placement state

If a previous Flow placement session exists but should no longer be used, consider **Reset and Start Again**.

---

## If Door Placement Cannot Continue

Check that:

- a sheet named exactly **Interior Opening Schedule** exists
- eligible `-D` views exist
- the views are not already placed
- the selected placement area is large enough

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Related Help

- [**Generating Opening Views**](generating-opening-views.md)
- [**Conforming Opening Views**](conforming-opening-views.md)
- [**Dimensioning Window Views**](dimensioning-window-views.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)

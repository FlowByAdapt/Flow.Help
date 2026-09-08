# Gutter Caps

**Gutter Caps** creates a small solid cap at a selected end of a Revit gutter.

The cap is generated directly from the gutter-end geometry, so no separate cap family or manually matched cap profile is required.

---

## When to Use Gutter Caps

Use **Gutter Caps** when a Revit gutter needs a closed end for modelling, coordination or documentation.

The tool:

- works with Revit **Gutter** elements;
- processes one gutter at a time;
- allows one or both ends of the selected gutter to be capped in the same run; and
- leaves the original Revit gutter unchanged.

---

## Opening Gutter Caps

You can open Gutter Caps in either of two ways.

### From the Flow ribbon

Go to:

**Flow → Model → Roof**

Select **Gutter Caps** from the Roof window.

### From Flow Hub

Search for and run:

**Gutter Caps**

Flow Hub launches the same Gutter Caps workflow directly without first opening the Roof window.

---

## Before You Start

Gutter Caps requires a suitable Revit plan view whose name contains:

**Roof Plan**

If you are already in a matching Roof Plan, Flow keeps that view active.

If not, Flow searches the project for a suitable non-template Roof Plan and switches to it automatically. Where available, **WORK-11-Roof Plan** is preferred.

If no suitable Roof Plan can be found, the command stops and reports that Gutter Caps requires a Roof Plan view.

You can either:

- preselect exactly one gutter before starting the tool; or
- select the gutter when prompted.

If exactly one valid gutter is preselected, Flow uses it automatically.

---

## First-Time Workflow

### 1. Start Gutter Caps

Open **Flow → Model → Roof → Gutter Caps**, or run **Gutter Caps** directly from Flow Hub.

Flow confirms that a suitable Roof Plan is active and changes view automatically where required.

### 2. Select the Gutter

If exactly one Revit gutter was preselected, Flow uses it automatically.

Otherwise, select the required gutter when Revit prompts:

**Pick a gutter element (TAB to cycle if needed)**

Use **Tab** if the gutter is difficult to highlight among nearby roof elements.

Pressing **Esc** at this stage cancels the command.

### 3. Pick Near the End to Cap

Click close to the physical end of the selected gutter.

You do not need to select the exact end face. Flow analyses the gutter geometry and uses the suitable end nearest to your picked point.

<!-- SCREENSHOT: Roof Plan with the gutter visible, the Revit pick prompt active, and a clear indication of where to click near the required gutter end. -->

### 4. Let Flow Create the Cap

For the selected end, Flow:

- identifies the nearest suitable gutter-end face;
- reads the actual end-profile geometry;
- reconstructs and closes the open gutter profile;
- checks whether a generated cap already exists at that end;
- creates a short solid cap where required; and
- applies a matching gutter material where one can be resolved.

The source gutter is not modified.

### 5. Cap Another End of the Same Gutter

After the first end is processed, Gutter Caps remains active for the same gutter.

Click near another required end and Flow repeats the process.

To work on a different gutter, finish the current run and start Gutter Caps again.

### 6. Finish the Command

Press **Esc** when all required ends of the selected gutter have been processed.

At this stage, Esc **finishes** the current run. It does not remove caps that have already been created.

Flow then selects the newly created cap elements and attempts to bring them into view for review.

### 7. Review the Completion Summary

A completion message reports:

- **Created** — the number of new caps created;
- **Skipped existing** — the number of selected ends where a generated cap was already detected; and
- **Material assigned** — the number of newly created caps where Flow resolved and applied a material.

<!-- SCREENSHOT: Gutter Caps completion summary showing Created, Skipped existing and Material assigned counts. -->

---

## Expected Result

Each newly created cap is a small solid **DirectShape** located at the selected gutter end.

Where Revit permits it, Flow creates the DirectShape using the **Gutter** category. If that category cannot be used, Flow falls back to **Generic Models**.

Where a gutter material can be resolved, the same material is applied to the generated cap.

Generated caps are marked in **Comments** as:

`Flow_GutterCap`

<!-- SCREENSHOT: Selected generated cap with Properties visible and Comments = Flow_GutterCap. -->

The generated cap remains a separate Revit element from the source gutter.

<!-- SCREENSHOT: Close 3D view showing the source gutter and generated end cap as separate geometry. -->

---

## What Flow Does Automatically

During the Gutter Caps workflow, Flow automatically:

- checks for an appropriate Roof Plan and switches to one where required;
- accepts a single preselected gutter where available;
- restricts interactive element selection to Revit gutters;
- identifies the suitable gutter end nearest the picked point;
- derives the cap shape from the actual gutter-end geometry;
- closes the open gutter section to form a solid end profile;
- checks for existing Flow-generated and recognised legacy gutter caps before creating another;
- attempts to use the Gutter category for the generated DirectShape;
- falls back to Generic Models where required;
- applies a matching material where available;
- adds `Flow_GutterCap` to the cap Comments;
- tracks created, skipped and material-assigned counts; and
- selects and frames newly created caps when the run finishes.

---

## Existing Gutter Caps

Before creating a cap, Flow checks for an existing recognised gutter cap near the selected end.

If one is found, that end is skipped rather than creating another cap in the same location.

This means Gutter Caps can be rerun without intentionally stacking duplicate generated caps at previously processed ends.

If a selected end is skipped, it is included in the **Skipped existing** count in the completion summary.

---

## Profile Creation

The cap profile is derived from the geometry at the selected gutter end.

Flow samples the end geometry, determines the outside envelope of the section and closes the open mouth of the gutter to create a solid cap profile.

This allows the workflow to accommodate different gutter profiles without requiring a separate purpose-made cap family.

Complex or unusual profiles should still be checked visually after creation.

---

## Tips and Notes

!!! tip "Preselect the gutter"

    If you already know which gutter you want to cap, select exactly one gutter before running Gutter Caps. Flow will use it automatically and skip the initial gutter-selection prompt.

!!! info "Esc has two different meanings"

    Press **Esc** while choosing the gutter to cancel the command.

    Press **Esc** while picking gutter ends to finish the current run and keep the caps already created.

!!! note "The cap is a separate element"

    Gutter Caps does not modify or extend the native Revit gutter. The generated cap remains a separate DirectShape element.

---

## Limitations

Gutter Caps currently:

- operates on Revit **Gutter** elements;
- processes one selected gutter at a time;
- requires a suitable plan view whose name contains **Roof Plan**;
- requires the user to identify the required end by clicking nearby;
- creates a separate DirectShape rather than modifying the source gutter;
- may fall back to the **Generic Models** category where Revit does not permit a Gutter-category DirectShape; and
- may require visual checking for complex or unusual gutter profiles.

Because the generated cap is a separate element and is not joined to the native Revit gutter, a visible junction or internal edge may remain between the gutter and cap in some model or 3D display conditions. This does not necessarily indicate that the cap was created incorrectly.

---

## Troubleshooting

If Gutter Caps cannot find a suitable Roof Plan, the gutter cannot be selected, a cap is skipped, or the generated geometry does not look as expected, see:

[Roof Tools Troubleshooting](troubleshooting.md)

---

## Related Help

- [Roof Tools](index.md)
- [Roof Outline](roof-outline.md)
- [Roof Tools Troubleshooting](troubleshooting.md)
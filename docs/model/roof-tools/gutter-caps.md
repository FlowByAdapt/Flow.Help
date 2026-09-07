# Gutter Caps

Gutter Caps creates a small solid cap at a selected end of a Revit gutter.

The cap is created directly from the gutter-end geometry, avoiding the need to create and manage a separate cap family.

!!! note "Current documentation status"

	This page describes the established Gutter Caps pyRevit workflow that is being migrated into the native Flow Roof Tools implementation. Behaviour may be refined as the native implementation develops.

## Open Gutter Caps

Go to:

**Flow → Model → Roof → Gutter Caps**

## Before You Start

Gutter Caps operates on Revit **Gutter** elements.

You can either:

* preselect a single gutter before starting the tool; or
* select the gutter when prompted.

If exactly one valid gutter is preselected, Flow uses it automatically.

## Create Gutter Caps

1. Go to **Flow → Model → Roof**.
2. Select **Gutter Caps**.
3. Select the required gutter if one was not already preselected.
4. Click near the end of the gutter that you want to cap.
5. Flow determines the nearest suitable gutter end and creates the cap.
6. Continue clicking near other ends of the **same gutter** if additional caps are required.
7. Press **Esc** when finished.
8. Review the completed caps.

<!-- SCREENSHOT: Close-up of a gutter showing where the user should click near the required end. -->

You do not need to select the exact end face. Pick close to the physical end of the gutter and the tool determines the nearest suitable end geometry.

## What Flow Does Automatically

For each selected gutter end, the established workflow:

* identifies the suitable end face nearest the picked point;
* derives the cap profile from the gutter-end geometry;
* reconstructs and closes the required profile;
* creates a short solid cap with a small overlap into the gutter;
* applies the gutter category where possible;
* uses Generic Models as a fallback where required;
* applies a matching material where available; and
* checks for an existing generated cap before creating another one.

The original Revit gutter is not modified.

## Existing Gutter Caps

Before creating a cap, Flow checks for an existing generated Gutter Cap near the selected gutter end.

If an existing cap is detected, that end is skipped rather than creating a duplicate cap.

This allows the workflow to be rerun without intentionally stacking multiple generated caps at the same end.

## What Flow Creates

Each cap is created as a small solid **DirectShape** element.

Where possible, Flow uses the Gutter category for the generated DirectShape. Generic Models provides a fallback where the Gutter category cannot be used.

Where available, the gutter material is also applied to the generated cap.

The cap remains a separate Revit element from the source gutter.

<!-- SCREENSHOT: Completed gutter cap in a 3D view, clearly showing the cap as a separate solid at the end of the gutter. -->

## Profile Creation

The cap profile is derived from the geometry at the selected gutter end.

Where required, Flow reconstructs the outside envelope of the profile and closes the open part of the gutter section to form a solid cap.

This allows the cap to follow the gutter geometry without requiring a separate purpose-made family.

Complex or unusual gutter profiles should be checked visually after creation.

## Creating More Than One Cap

After creating the first cap, the command remains active for the selected gutter.

Continue clicking near additional ends of that gutter as required.

Press **Esc** when all required ends have been processed.

To work on a different gutter, finish the current operation and run Gutter Caps again.

## Finishing the Command

Press **Esc** when you have finished placing caps on the selected gutter.

The established workflow selects the newly created cap elements and brings them into view, making it easier to review the result.

A completion summary reports the number of caps created, the number skipped because a cap already existed, and the number where a material was assigned.

## Checking the Result

After creating the caps, check that:

* the required gutter ends have been capped;
* the cap follows the expected gutter profile;
* the cap overlaps the gutter cleanly;
* duplicate caps have not been created; and
* the resulting geometry is suitable in the required model and documentation views.

## Limitations

The established Gutter Caps workflow:

* operates on Revit Gutter elements;
* processes one selected gutter at a time;
* requires the user to identify the required ends by picking nearby;
* creates separate DirectShape elements rather than modifying the source gutter; and
* may require visual checking for complex or unusual gutter profiles.

## Related Help

* [Roof Tools](index.md)
* [Roof Outline](roof-outline.md)
* [Roof Tools Troubleshooting](troubleshooting.md)

# Conforming Opening Views

Use **Conform Views** to repair existing opening elevations and bring
them back to the expected Flow documentation standard.

This is useful after opening marks, view settings or model information
have changed.

------------------------------------------------------------------------

## What Conform Views Does

Depending on the opening view, Flow can restore or update:

-   view template
-   view scale
-   crop region
-   level datum extents
-   phase and phase filter
-   view name
-   opening tag
-   window size metadata
-   curtain wall metadata

Conform Views is therefore more than a crop-adjustment tool. It is
intended to reapply the expected opening-view setup to existing
elevations.

------------------------------------------------------------------------

## Choose the Scope

When you run **Conform Views**, choose:

-   **Active View**
-   **All Opening Views**

Use **Active View** when you only need to repair the opening elevation
currently open in Revit.

Use **All Opening Views** to process the recognised opening elevations
throughout the project.

------------------------------------------------------------------------

## Active View

To conform a single view:

1.  Open the required opening elevation.
2.  Run **Conform Views**.
3.  Choose **Active View**.
4.  Review the completion result.

Flow checks whether the active view can be recognised as an opening view
before applying the expected standards.

------------------------------------------------------------------------

## All Opening Views

Use **All Opening Views** when multiple opening elevations need to be
checked or repaired.

Flow reviews the recognised opening views and applies the appropriate
operation to each one.

Views that cannot be resolved to an opening are skipped rather than
modified arbitrarily.

------------------------------------------------------------------------

## View Naming

Flow checks the current view against the associated opening information
and can rename recognised views where required.

Window and curtain wall elevations are associated with their W-style
opening marks.

Door elevations use the door documentation naming convention with the
`-D` suffix.

This is useful after opening marks or door type information have
changed.

------------------------------------------------------------------------

## View Template and Scale

Conform Views reapplies the expected view template and scale for the
recognised opening view.

Use this when an opening elevation has been manually altered or no
longer matches the standard documentation setup.

------------------------------------------------------------------------

## Crop Region

Flow activates and conforms the crop region to the opening.

This can repair opening elevations where the crop has been moved,
resized or otherwise no longer frames the opening correctly.

------------------------------------------------------------------------

## Phase Settings

Conform Views restores the expected opening-view phase setup:

-   **Phase:** New Construction
-   **Phase Filter:** Show Previous + New

This keeps opening documentation consistent across the project.

------------------------------------------------------------------------

## Missing Tags

If the expected opening tag is missing, Flow can restore it while
conforming the view.

The appropriate tagging behaviour depends on whether the view represents
a window, door or curtain wall.

------------------------------------------------------------------------

## Opening Metadata

Conform Views can also update opening-related metadata.

For recognised views this can include:

-   window size metadata
-   curtain wall metadata

This helps keep the generated documentation aligned with the current
model.

------------------------------------------------------------------------

## Completion Summary

After the operation, Flow reports the results of the conform process.

The summary can include:

-   Views Processed
-   Views Renamed
-   Views Retagged
-   Crop Regions Adjusted
-   Metadata Updated
-   Failed
-   Skipped

Review any failed or skipped views before continuing with the
documentation workflow.

------------------------------------------------------------------------

## When to Use Conform Views

Use Conform Views when:

-   an opening mark has changed
-   an opening view name is no longer correct
-   a view template or scale has been changed
-   a crop region needs to be restored
-   an expected opening tag is missing
-   opening metadata needs to be refreshed
-   existing opening elevations need to be brought back to the Flow
    standard

!!! tip "Repair rather than recreate"

    If the required opening elevation already exists, use **Conform Views** before considering whether the view needs to be recreated.

------------------------------------------------------------------------

## After Conforming

After conforming the views:

1.  Review any skipped or failed views.
2.  Dimension window views where required.
3.  Place the opening views on sheets.
4.  Refresh Openings Manager to update the documentation status.

------------------------------------------------------------------------

## Related Help

-   [**Opening Views**](opening-views.md)
-   [**Generating Opening Views**](generating-opening-views.md)
-   [**Dimensioning Window Views**](dimensioning-window-views.md)
-   [**Placing Opening Views on Sheets**](placing-views-on-sheets.md)
-   [**Openings Manager Troubleshooting**](troubleshooting.md)
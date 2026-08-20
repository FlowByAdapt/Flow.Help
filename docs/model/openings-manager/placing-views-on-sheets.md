# Placing Opening Views on Sheets

Use **Place Opening Views on Sheet** to arrange generated Window or Door
elevations on the appropriate opening schedule sheets.

Window and Door placement use different workflows.

------------------------------------------------------------------------

## Start the Placement Tool

Run **Place Opening Views on Sheet**.

Choose whether you want to place:

-   Window Views
-   Door Views

If a previous Window placement session is available, Flow can also
provide an option to reset that session.

------------------------------------------------------------------------

# Window View Placement

Window placement is designed to distribute New window and curtain wall
elevations across the A4-series opening sheets.

------------------------------------------------------------------------

## Required Starting Sheet

The Window placement workflow requires:

``` text
A401
```

to exist in the project.

Flow uses A401 as the starting point for the Window opening-sheet
sequence.

If A401 cannot be found, the automatic Window placement workflow cannot
proceed normally.

------------------------------------------------------------------------

## Which Window Views Are Placed?

Flow looks for unplaced New opening views using the strict:

``` text
W##
```

naming pattern.

For example:

``` text
W01
W02
W03
```

Existing `Wx##` views are not included.

Views that are already placed are excluded.

Views recorded as placed in the current Flow placement session are also
excluded.

------------------------------------------------------------------------

## Define the Placement Area

On the sheet, pick:

1.  **Top Left**
2.  **Bottom Right**

These two points define the usable area in which Flow can arrange the
opening views.

Flow calculates the layout from the estimated paper size of the actual
elevation views rather than treating every viewport as the same size.

------------------------------------------------------------------------

## Automatic Layout

Flow arranges the views into rows within the selected placement area.

The layout can use up to six rows.

Spacing is calculated from the available area and the estimated size of
the opening elevations.

Mixed-height window and curtain wall views are aligned along common row
baselines to produce a more consistent sheet layout.

------------------------------------------------------------------------

## Reuse the Placement Area

After a placement area has been defined, Flow can remember it for the
current placement workflow.

On a subsequent sheet, you may be offered the option to reuse the
previous placement area.

This avoids having to pick the same sheet region repeatedly.

------------------------------------------------------------------------

## Continue onto Additional Sheets

If all remaining views cannot fit on the current sheet, Flow can
continue the placement workflow onto the next A4-series sheet.

The available actions can include:

-   **Continue to Next Sheet**
-   **Stop and Resume Later**
-   **Reset Placement**

------------------------------------------------------------------------

## Creating Additional Window Sheets

Where required, Flow can create additional A4-series sheets from A401.

The new sheet is created by duplicating A401 **with detailing** and
retaining the A401 sheet name while assigning the next required A4 sheet
number.

Existing A4-series sheets can be shifted where necessary to make room in
the sequence.

------------------------------------------------------------------------

## Stop and Resume Later

Window placement state is persisted.

Choose **Stop and Resume Later** when you want to end the current
placement run without losing the recorded placement progress.

The next placement session can continue from the remaining unplaced
views.

------------------------------------------------------------------------

## Reset Previous Session

If a previous Window placement session needs to be undone, choose
**Reset Previous Session** from the initial placement workflow where
available.

Flow removes the Window viewports created by the recorded placement
session and clears the placement memory.

!!! info "Reset does not delete the views or sheets"

    Reset Previous Session removes the recorded placed viewports.

    It does **not** delete the opening elevation views or the sheets themselves.

------------------------------------------------------------------------

## Window Placement Settings

During Window placement, Flow can temporarily enable the project:

``` text
Sheet Outline Show
```

Global Parameter.

Where available, placed views use the:

``` text
No Title
```

viewport type.

------------------------------------------------------------------------

# Door View Placement

Door placement uses a simpler workflow than Window placement.

------------------------------------------------------------------------

## Required Door Sheet

Flow looks for the first sheet named exactly:

``` text
Interior Opening Schedule
```

This is used as the target for Door elevation placement.

------------------------------------------------------------------------

## Which Door Views Are Placed?

Flow looks for unplaced section/elevation views whose names end with:

``` text
-D
```

For example:

``` text
01-D
02-D
03-D
```

Already placed Door views are excluded.

------------------------------------------------------------------------

## Define the Door Placement Area

On the Interior Opening Schedule sheet, pick:

1.  **Top Left**
2.  **Bottom Right**

Flow estimates the paper size of the Door elevations and arranges as
many as possible within the selected region.

Where available, the **No Title** viewport type is used.

------------------------------------------------------------------------

## Door Placement Limitations

The Door placement workflow does not currently use the same persisted
multi-sheet session system as Window placement.

It also does not automatically create additional Door schedule sheets.

Flow places the Door views that fit within the selected area and reports
the result.

The summary can include:

-   Placed
-   Skipped
-   Failed

------------------------------------------------------------------------

## Window and Door Placement Differences

  -----------------------------------------------------------------------
  Window Views                        Door Views
  ----------------------------------- -----------------------------------
  Uses `W##` views                    Uses `-D` views

  Starts from A401                    Uses Interior Opening Schedule

  Can continue across A4-series       Uses the selected schedule sheet
  sheets                              

  Can create additional sheets        Does not automatically create
                                      additional sheets

  Supports persisted placement        No equivalent persisted session
  sessions                            

  Can reset a recorded session        No equivalent placement reset
  -----------------------------------------------------------------------

------------------------------------------------------------------------

## Recommended Workflow

Before placing opening views:

1.  Generate the required opening elevations.
2.  Conform the views where required.
3.  Dimension Window views.
4.  Confirm the required sheets exist.
5.  Run **Place Opening Views on Sheet**.
6.  Review the completed sheet layout.
7.  Refresh Openings Manager.

------------------------------------------------------------------------

## If Placement Cannot Continue

For Window placement, check that:

-   A401 exists
-   the required `W##` views exist
-   the views are not already placed
-   the selected placement area is large enough

For Door placement, check that:

-   a sheet named **Interior Opening Schedule** exists
-   the required `-D` views exist
-   the views are not already placed
-   the selected placement area is large enough

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Related Help

-   [**Opening Views**](opening-views.md)
-   [**Generating Opening Views**](generating-opening-views.md)
-   [**Conforming Opening Views**](conforming-opening-views.md)
-   [**Dimensioning Window Views**](dimensioning-window-views.md)
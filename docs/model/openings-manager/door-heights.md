# Door Heights

Use **Door Heights** to review and standardise the height of New doors
by project level.

Flow creates or reuses appropriately sized door types and then assigns
the affected door instances to those types.

------------------------------------------------------------------------

## Open Door Heights

Run **Door Heights** from the Openings Manager or the corresponding Flow
command.

The Door Height settings window lists the project levels that contain
doors and provides a target height for each level.

------------------------------------------------------------------------

## Proposed Heights

For each populated level, Flow checks the existing door types and looks
for the most common **Panel Height**.

Where a usable height can be determined, that value becomes the proposed
height for the level.

If no usable Panel Height can be determined, Flow falls back to:

-   **2200 mm** for the first populated level
-   **1980 mm** for subsequent populated levels

Review the proposed values before applying the changes.

!!! tip "Review before applying"

    The values shown in the Door Heights window are intended to be reviewed.

    Adjust a level value where the project requires a different door height.

------------------------------------------------------------------------

## Apply Door Heights

1.  Open **Door Heights**.
2.  Review the levels containing doors.
3.  Check the proposed height for each level.
4.  Adjust any values that need to change.
5.  Apply the operation.
6.  Review the completion result.

Flow processes the applicable doors and updates them to the required
type.

------------------------------------------------------------------------

## New Doors Only

Door Height adjustment is intended for **New** doors.

Flow skips doors classified as:

-   Existing
-   Demolished

This prevents the standard New-door height workflow from changing
existing or demolished opening documentation.

------------------------------------------------------------------------

## How Door Types Are Updated

Flow does not simply change the shared Panel Height of every existing
door type.

For each applicable door, it:

1.  reads the current door type's **Panel Width**
2.  combines that width with the required level height
3.  builds the required type name
4.  looks for that type within the same door family
5.  reuses it if it already exists
6.  otherwise duplicates the current type and applies the required Panel
    Height
7.  assigns the door instance to the resulting type

The type naming format is:

``` text
<width>w x <height>h
```

For example:

``` text
810w x 2200h
```

This allows doors of the same width and height to reuse the same family
type.

------------------------------------------------------------------------

## Existing Door Types

If the required type already exists within the same door family, Flow
reuses it.

A duplicate type is only created when the required width-and-height type
cannot already be found.

------------------------------------------------------------------------

## Only Selected Doors

Where the Door Heights workflow is being used with a selected set of
doors, the settings window can provide an **Only Selected Doors**
option.

Use this when the level settings should only be applied to the selected
door instances rather than every applicable door on those levels.

------------------------------------------------------------------------

## Completion Result

The Door Heights result can report information including:

-   Processed doors
-   Updated doors
-   Created types
-   Reused types
-   Skipped - no width
-   Skipped - no level
-   Skipped - no height setting
-   Skipped - existing or demolished

Review skipped items if the number of updated doors is lower than
expected.

------------------------------------------------------------------------

## If a Door Is Not Updated

Check that:

-   the door is New rather than Existing or Demolished
-   the door family provides a usable **Panel Width**
-   the door type provides a usable **Panel Height**
-   a height has been provided for the door's level
-   the door is included in the selected scope where selection is being
    used

For further checks:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Related Help

-   [**Reviewing Openings**](reviewing-openings.md)
-   [**Selecting and Locating
    Openings**](selecting-and-locating-openings.md)
-   [**Opening Global Parameters**](opening-global-parameters.md)
-   [**Openings Manager Troubleshooting**](troubleshooting.md)
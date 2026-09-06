# Dimension Labels

**Dimension Labels** applies descriptive text to individual dimension segments.

The verified source workflow labels a selected dimension segment using the **Room Name** from a selected Revit **Room Tag**.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Dimension Labels**.

------------------------------------------------------------------------

## Before You Start

Open a **Floor Plan** or **Reflected Ceiling Plan** containing:

-   a continuous dimension chain; and
-   the Room Tag for the room name you want to use.

!!! note "Continuous dimension required"

    The selected dimension must contain dimension segments. A single unsegmented dimension cannot receive a segment label through this workflow.

------------------------------------------------------------------------

## Applying a Room Name to a Dimension Segment

1.  Start **Dimension Labels**.
2.  Select the required dimension chain.
3.  Click near the dimension segment you want to label.
4.  Select the required **Room Tag**.
5.  Flow reads the associated Room Name.
6.  The Room Name is written below the selected dimension segment.
7.  Repeat for additional segments.
8.  Press **Esc** when finished.

Flow identifies the dimension segment closest to the point you click, so click close to the intended segment.

------------------------------------------------------------------------

## Room Information

Flow obtains the room from the selected Room Tag and reads its **Name** parameter.

If the selected tag does not resolve to a Room, the label is not applied.

------------------------------------------------------------------------

## Working with Join Dimensions

Labels applied below dimension segments are intended to remain compatible with **Join Dimensions**.

When compatible dimension strings are joined, supported segment labels can be carried across to the recreated continuous dimension.

------------------------------------------------------------------------

## Finishing the Workflow

Press **Esc** to finish.

The workflow reports how many dimension segments were labelled during the session.

------------------------------------------------------------------------

## Related Help

-   [Dimension Labels Troubleshooting](troubleshooting.md)
-   [Join Dimensions](join-dimensions.md)
-   [Annotation](index.md)
# Identifying Risk Faces

Use **Risk Matrix** to identify exterior walls that form the building
faces used by the risk assessment workflow.

Processing a face assigns coordinated model information, a Risk Face
number, view graphics and a Risk Face tag.

------------------------------------------------------------------------

## Open a Risk View

Open Risk Matrix from:

**Flow → Model → Risk**

Flow attempts to activate:

**RISK-01-Elevation**

Risk Matrix recognises Risk Views whose names begin with **RISK-**. Use
**Previous View** and **Next View** to move through them.

------------------------------------------------------------------------

## Before Selecting Walls

Confirm the project Wind Zone and review the five editable Risk Matrix
values:

-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

Also review the **Cladding** tab so the required exterior wall types are
included and mapped correctly.

➡️ See [**Assigning Risk Information**](assigning-risk-information.md)

------------------------------------------------------------------------

## Pick Exterior Walls

Click:

**Pick Walls**

Risk Matrix accepts eligible exterior walls based on wall types
beginning with:

**ADa_E\_**

Select walls **one at a time**.

Each accepted pick receives a temporary pale-blue highlight and the
Revit prompt reports how many walls have been selected.

Press **Esc** when finished.

!!! info "Esc completes the selection"

    During Pick Walls, Esc ends the wall-picking loop and processes the walls already selected. It does not discard the completed selection.

<!-- SCREENSHOT: Pick Walls in progress showing the temporary selection highlight and Revit prompt. -->

------------------------------------------------------------------------

## How Walls Are Grouped

After selection, Risk Matrix groups the accepted walls according to
their geometry in the active Risk View.

Walls can form one Risk Face when they are approximately:

-   parallel and coplanar;
-   close in plane; and
-   spatially continuous when projected into the view.

This allows related wall segments, including vertically related walls,
to share one Risk Face where they form a continuous building face.

A genuine break or change of plane normally creates a separate group.

!!! info "Risk Faces represent building faces"

    A Risk Face can contain more than one Revit wall. The face number identifies the coordinated building face rather than an individual wall element.

------------------------------------------------------------------------

## Selection Order and Face Numbering

New Risk Faces are normally numbered sequentially:

**Face 1**, **Face 2**, **Face 3** and so on.

Risk Matrix orders newly discovered wall groups using the earliest
selected wall in each group. This means the order in which you select
the building faces influences their numbering.

Where practical, work around the building in the Risk Face order you
want.

Already processed walls retain their existing Risk Face information
rather than receiving new risk values.

------------------------------------------------------------------------

## Reprocessing a Reset Face

Risk Matrix records enough reset history to recognise some previously
reset faces.

If all newly selected unprocessed walls belong to one previously reset
Risk Face, Flow can display a **Risk Face Number** dialog.

Choose:

**Next Available**\
Use the next available face number.

**Restore Original**\
Restore the previous face number. Later faces are shifted where
necessary to make room.

**Choose Number...**\
Insert the face at a selected position between Face 1 and the next
available number.

<!-- SCREENSHOT: Risk Face Number options after reselecting a previously reset face. -->

------------------------------------------------------------------------

## Colours and Tags

When a new Risk Face is processed, Risk Matrix coordinates:

-   the Risk Face number;
-   the selected Risk Matrix values;
-   applicable cladding information;
-   a distinct Risk Face colour;
-   projection line graphics; and
-   a **Risk Face label** tag where possible.

Risk Matrix uses:

**ADa_TAG_Wall_Risk : Risk Face label**

The colour identifies the Risk Face number. It does not indicate the
final E2 risk score.

<!-- SCREENSHOT: Completed Risk View showing colours, labels and a multi-wall Risk Face. -->

------------------------------------------------------------------------

## Copy an Existing Face

Use **Copy Face** when another wall genuinely belongs to an existing
Risk Face.

1.  Click **Copy Face**.
2.  Select a processed **ADa_E\_** source wall.
3.  Select the target walls one at a time.
4.  Press **Esc** when finished.

The target walls inherit the source Risk Face assignment and associated
Risk Matrix/cladding information.

Do not use Copy Face when you only need to correct a visible wall-end
colour.

------------------------------------------------------------------------

## Match a Wall End

Use **Match Wall End** for graphical continuity where an exposed wall
end should display the colour of another Risk Face.

1.  Click **Match Wall End**.
2.  Select a processed source wall.
3.  Select the exposed target **wall face**.

This changes the view graphics only. It does not copy the source Risk
Face assignment or Risk Matrix parameters.

------------------------------------------------------------------------

## Reset a Risk Face

Use the selected-face reset when one Risk Face needs to be rebuilt.

After confirmation, select any processed **ADa_E\_** wall belonging to
that face.

Risk Matrix clears the face's risk values, face name, cladding
values/category, Risk View overrides and associated Risk Wall tags.
Other processed faces and the project-wide cladding setup are preserved.

When the walls are processed again, the previous face number may be
offered for restoration.

------------------------------------------------------------------------

## Related Help

-   [**Risk Matrix**](index.md)
-   [**Assigning Risk Information**](assigning-risk-information.md)
-   [**Reviewing Risk Results**](reviewing-risk-results.md)
-   [**Risk Documentation**](risk-documentation.md)
-   [**Troubleshooting**](troubleshooting.md)

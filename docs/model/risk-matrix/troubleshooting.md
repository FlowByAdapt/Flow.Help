# Risk Matrix Troubleshooting

Use these checks if Risk Matrix cannot process the expected walls or the
Risk Face information is not behaving as expected.

------------------------------------------------------------------------

## Risk Matrix Does Not Open on the Expected View

Risk Matrix attempts to activate:

**RISK-01-Elevation**

Risk Views must begin with:

**RISK-**

Confirm that the default view exists. Use **Previous View** and **Next
View** to move through the available Risk Views.

------------------------------------------------------------------------

## Pick Walls Will Not Start

Check the project **Wind Zone** first.

Risk Matrix requires a recognised value from:

**Revit Project Information → Wind Zone**

Accepted standard values are:

-   Low
-   Medium
-   High
-   Very High
-   Extra High

If the value changed while Risk Matrix was open, click **Refresh**.

------------------------------------------------------------------------

## Wind Zone Is Not Set or Unrecognised

Risk Face processing remains blocked while Wind Zone cannot be resolved.

1.  Open Revit **Project Information**.
2.  Set **Wind Zone** to the required recognised value.
3.  Return to Risk Matrix.
4.  Click **Refresh**.

------------------------------------------------------------------------

## Wind Zone Shows SED

**SED** indicates Specific Engineering Design.

Risk Matrix intentionally blocks the standard E2 Risk Matrix processing
workflow when the project Wind Zone is SED.

This is expected behaviour rather than a processing error.

------------------------------------------------------------------------

## A Wall Cannot Be Selected

Risk Matrix uses an eligibility filter during **Pick Walls**.

Confirm that the wall type begins with:

**ADa_E\_**

Also confirm that you are selecting a wall element rather than another
model category.

------------------------------------------------------------------------

## I Pressed Esc During Pick Walls

This is the normal way to finish the selection.

During **Pick Walls**, walls are selected one at a time. Pressing
**Esc** ends the selection loop and processes the walls already
selected.

If no eligible walls were selected, there is nothing to process.

------------------------------------------------------------------------

## The Temporary Blue Highlight Disappeared

The pale-blue override is temporary selection feedback only.

It is applied while you are choosing walls and is not the final Risk
Face colour. After processing, Risk Matrix applies the coordinated Risk
Face graphics.

------------------------------------------------------------------------

## Walls Are Grouped into the Wrong Face

Risk Matrix groups walls according to their geometry in the active Risk
View.

Check whether the walls are:

-   approximately coplanar;
-   close in plane; and
-   spatially continuous when projected into the view.

Small geometric differences can affect grouping. A genuine break or
change of plane should normally produce a separate Risk Face.

------------------------------------------------------------------------

## Face Numbers Are Unexpected

For new groups, selection order influences processing order. Risk Matrix
uses the earliest selected wall in each group when ordering the groups.

Where practical, select building faces in the numbering order you want.

Already processed walls retain their existing Risk Face information.

If the walls were previously reset, Flow may display **Next Available**,
**Restore Original** or **Choose Number...** before processing them
again.

------------------------------------------------------------------------

## A Previously Processed Wall Kept Its Old Values

This is intentional.

Already processed walls are protected from having their stored Risk
Matrix values overwritten when they are selected again. They can still
be updated for presentation in the active view.

If the wall genuinely needs a different Risk Face assignment, use the
appropriate **Copy Face** or reset workflow.

------------------------------------------------------------------------

## Copy Face Does Not Start

The first selection must be a processed **ADa_E\_** wall with a valid
Risk Face assignment.

After selecting the source, select target walls one at a time and press
**Esc** when finished.

Selecting no target walls cancels the operation.

------------------------------------------------------------------------

## Match Wall End Does Not Work

The workflow requires two different kinds of selection:

1.  a processed source **wall**; then
2.  the exposed target **wall face**.

Match Wall End cannot be used in a view template.

Remember that it changes view graphics only. If the target wall
genuinely belongs to the source Risk Face, use **Copy Face** instead.

------------------------------------------------------------------------

## A Risk Face Has the Wrong Colour

Risk Face colours are based on the face number.

If the face assignment is correct but an exposed wall end needs
graphical continuity, use **Match Wall End**.

If the wall genuinely belongs to another Risk Face, use **Copy Face** or
reset and reprocess the face.

------------------------------------------------------------------------

## A Risk Face Tag Is Missing

Risk Matrix uses:

**ADa_TAG_Wall_Risk : Risk Face label**

Check that this family/type is available in the project.

A tag can also fail where Revit cannot determine or create a suitable
tag in the current view.

------------------------------------------------------------------------

## Cladding Mapping Is Unexpected

Open the **Cladding** tab and check:

-   whether the wall type is included;
-   its cladding description;
-   its selected **Cladding 1--4** group;
-   the resulting **Wall Type Cladding Mapping**; and
-   **Project Cladding Health**.

Wall types sharing the same description should normally use the same
group.

------------------------------------------------------------------------

## More Than Four Cladding Descriptions Are Required

The current workflow supports a maximum of four coordinated project
cladding descriptions.

Reduce or coordinate the project descriptions so the required included
wall types can be represented by **Cladding 1--4**.

------------------------------------------------------------------------

## Cladding Changes Were Lost

The cladding setup is saved into the Revit project through the Risk
Matrix workflow and should be restored when the tool is reopened.

A full **Reset Risk Matrix** deliberately clears the saved cladding
configuration.

A selected-face reset does not.

------------------------------------------------------------------------

## I Reset the Wrong Face Number

When a selected face is reset, Risk Matrix can retain reset history on
its former walls.

If those walls are subsequently processed together, the **Risk Face
Number** dialog may allow you to **Restore Original** or **Choose
Number...**.

------------------------------------------------------------------------

## I Only Need to Correct One Face

Do not use a full project reset.

Use the selected-face reset so the chosen Risk Face can be cleared and
rebuilt while other processed faces and the project cladding
configuration remain intact.

------------------------------------------------------------------------

## Related Help

-   [**Risk Matrix**](index.md)
-   [**Identifying Risk Faces**](identifying-risk-faces.md)
-   [**Assigning Risk Information**](assigning-risk-information.md)
-   [**Reviewing Risk Results**](reviewing-risk-results.md)
-   [**Risk Documentation**](risk-documentation.md)

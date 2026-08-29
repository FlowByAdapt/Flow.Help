# Identifying Risk Faces

Use **Risk Matrix** to identify exterior walls that form the building
faces used by the risk assessment workflow.

Processing a face assigns a coordinated face number, model parameters,
colour and Risk Face tag.

------------------------------------------------------------------------

## Open a Risk View

Open Risk Matrix from:

**Flow → Model → Risk**

Risk Matrix works with views whose names begin with:

**RISK-**

The default view is:

**RISK-01-Elevation**

Use **Previous View** and **Next View** in the **Current Risk View**
card to move through the available Risk Views.

------------------------------------------------------------------------

## Set the Project Risk Values

Before selecting walls, review the values shown under **Project Risk
Values**.

The project **Wind Zone** is read automatically from Revit Project
Information.

Select the remaining values required for the walls you are about to
process:

-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

These values are written to the walls when **Pick Walls** is completed.

➡️ See [**Assigning Risk Information**](assigning-risk-information.md)
for more information.

------------------------------------------------------------------------

## Review the Cladding Setup

Before processing Risk Faces, review the **Cladding** tab and confirm that the
required exterior wall types are included and mapped to the intended project
cladding descriptions and groups.

The saved project cladding mapping is used automatically during **Pick Walls**.

➡️ See [**Assigning Risk Information**](assigning-risk-information.md#cladding-information)
for more information.

------------------------------------------------------------------------

## Pick Exterior Walls

Click:

**Pick Walls**

Then select the exterior walls that make up the Risk Face or faces you
want to process.

Risk Matrix discovers exterior wall types whose names begin with:

**ADa_E\_**

The **Cladding** tab can then be used to control which discovered wall types
participate in the project cladding configuration.

The selected walls are analysed and grouped according to their position
in the current Risk View.

------------------------------------------------------------------------

## How Walls Are Grouped

Walls can be treated as one Risk Face when they are:

-   approximately coplanar;
-   spatially continuous in the current Risk View; and
-   close enough to touch or overlap within the tool's grouping
    tolerance.

This allows related wall segments, including vertically related
segments, to share the same Risk Face where their projected extents form
a continuous face.

A genuine break or change of plane creates a separate group.

!!! info "Risk Faces are based on the building face"

    A Risk Face can contain more than one Revit wall.

    The face number identifies the coordinated building face rather than an individual wall element.

------------------------------------------------------------------------

## Face Numbering

New Risk Faces are assigned sequential numbers:

**Face 1**, **Face 2**, **Face 3** and so on.

Risk Matrix keeps track of the next available face number in the
project.

If a processed group already contains a Risk Face number, that existing
number is retained rather than automatically creating a new one.

When a face is removed, the remaining face numbers can be compacted so
the sequence does not contain unnecessary gaps.

------------------------------------------------------------------------

## Colours and Tags

When a Risk Face is processed, Risk Matrix automatically:

-   applies a distinct colour to the walls in the current Risk View;
-   uses consistent projection line graphics;
-   writes the Risk Face information to the walls; and
-   places a **Risk Face label** tag where possible.

The colours identify **Risk Face numbers**. They do not represent the
final E2 risk score.

Risk Matrix uses the tag:

**ADa_TAG_Wall_Risk : Risk Face label**

Only one Risk Matrix tag is created for a Risk Face in the relevant
view.

------------------------------------------------------------------------

## Copy an Existing Face

Use **Copy Face** when another wall should belong to an existing Risk
Face.

The workflow copies the source face assignment and its Risk
Matrix/cladding information to the target wall or walls and applies the
corresponding face graphics.

If moving walls between faces leaves an old face empty, Risk Matrix
compacts the remaining face numbering.

!!! warning "Copy Face changes model information"

    **Copy Face** is not just a graphical match.

    The target walls receive the source Risk Face assignment and associated Risk Matrix/cladding parameter values.

------------------------------------------------------------------------

## Match a Wall End

Use **Match Wall End** when a wall end or adjoining wall needs to
display the same Risk Face colour for graphical continuity.

This operation applies the source face graphics to the target wall in
the current view.

It does **not**:

-   assign the target wall to that Risk Face;
-   copy Risk Matrix parameters; or
-   create a Risk Face tag for the target wall.

!!! tip "Use Match Wall End for presentation"

    Use **Copy Face** when the wall genuinely belongs to the same Risk Face.

    Use **Match Wall End** when only the view graphics need to match.

------------------------------------------------------------------------

## Resetting Faces

Risk Matrix supports resetting processed Risk Face information.

Resetting an individual face clears its Risk Matrix wall parameters,
removes its Risk Face graphics and tags, and then compacts the remaining
face numbering.

**Reset Risk Matrix** performs a much broader project-wide reset. It also
clears the saved project cladding configuration, which is then rebuilt from the
automatic wall-type discovery and default mappings.

➡️ See [**Troubleshooting**](troubleshooting.md) before using a full
reset if you only need to correct one face.

------------------------------------------------------------------------

## Related Help

-   [Risk Matrix](index.md)
-   [Assigning Risk Information](assigning-risk-information.md)
-   [Reviewing Risk Results](reviewing-risk-results.md)
-   [Risk Documentation](risk-documentation.md)
-   [Troubleshooting](troubleshooting.md)
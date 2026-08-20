# Risk Matrix Troubleshooting

Use the following checks if Risk Matrix cannot process the expected
walls or the Risk Face information is not behaving as expected.

------------------------------------------------------------------------

## Risk Matrix Does Not Open on the Expected View

Risk Matrix recognises Risk Views whose names begin with:

**RISK-**

The default Risk View is:

**RISK-01-Elevation**

If the active view is not already a Risk View, confirm that the default
Risk View exists in the project.

Use **Previous View** and **Next View** to move between the available
Risk Views.

------------------------------------------------------------------------

## Pick Walls Will Not Continue

Check the project **Wind Zone** first.

Risk Matrix requires a recognised Wind Zone from:

**Revit Project Information → Wind Zone**

Accepted standard values are:

-   Low
-   Medium
-   High
-   Very High
-   Extra High

If the value was changed while Risk Matrix was already open, click
**Refresh** beside Wind Zone.

------------------------------------------------------------------------

## Wind Zone Shows Not Set

The project Wind Zone is blank or could not be resolved.

1.  Open Revit **Project Information**.
2.  Set **Wind Zone** to the required project value.
3.  Return to Risk Matrix.
4.  Click **Refresh**.

Risk Face processing remains blocked while Wind Zone is unresolved.

------------------------------------------------------------------------

## Wind Zone Shows SED

**SED** indicates Specific Engineering Design.

Risk Matrix intentionally blocks the standard E2 Risk Matrix processing
workflow when the project Wind Zone is SED.

This is not an error in the tool.

------------------------------------------------------------------------

## A Wall Cannot Be Processed

Confirm that the wall is an exterior wall type expected by Risk Matrix.

The current workflow identifies exterior wall types using the prefix:

**ADa_E\_**

Also check that the wall has valid geometry that can be interpreted in
the current Risk View.

------------------------------------------------------------------------

## Walls Are Grouped into the Wrong Face

Risk Matrix groups selected walls when they are approximately coplanar
and spatially continuous in the current Risk View.

If two walls are unexpectedly grouped together, check:

-   whether they are effectively on the same plane;
-   whether their projected extents touch or overlap; and
-   whether the model geometry contains only a very small gap.

If walls that should form one face are separated by a genuine model gap,
they may be treated as separate Risk Faces.

------------------------------------------------------------------------

## Face Numbers Are Unexpected

Risk Matrix retains an existing face number where the selected group
already contains processed Risk Face information.

When a face is removed, the remaining face numbers can be compacted to
close the gap.

If a face has been assigned incorrectly, use the individual face-reset
or **Copy Face** workflow rather than manually editing the face number
where possible.

------------------------------------------------------------------------

## A Risk Face Has the Wrong Colour

Risk Face colours are based on the face number.

If the face number is correct but a wall needs to display another face
colour only for graphical continuity, use:

**Match Wall End**

If the wall genuinely belongs to another Risk Face, use:

**Copy Face**

Do not use **Match Wall End** to correct model data because it changes
only the view graphics.

------------------------------------------------------------------------

## A Risk Face Tag Is Missing

Risk Matrix uses:

**ADa_TAG_Wall_Risk : Risk Face label**

Check that this family and type are available in the project.

A tag may also fail to appear if:

-   the view is a template;
-   a representative wall cannot be determined;
-   a suitable tag position cannot be determined; or
-   Revit cannot create the tag in the current view.

Risk Matrix avoids creating a duplicate Risk Matrix tag when one already
exists for the face in that view.

------------------------------------------------------------------------

## Copy Face Does Not Work

The source wall must already belong to a valid Risk Face.

**Copy Face** copies:

-   the Risk Face assignment;
-   Risk Matrix parameter values;
-   cladding information; and
-   the corresponding face graphics.

A target already belonging to the same face is skipped.

If the operation removes the last wall from another face, the remaining
face numbering is compacted.

------------------------------------------------------------------------

## Match Wall End Does Not Change the Face Number

This is expected.

**Match Wall End** is a graphics-only tool. It applies the source Risk
Face colour to the target wall in the current view.

It does not change:

-   Risk Face Name;
-   Risk Matrix parameters;
-   cladding information; or
-   Risk Face tags.

Use **Copy Face** when the target wall should actually belong to the
same Risk Face.

------------------------------------------------------------------------

## Cladding Information Is Unexpected

Risk Matrix builds the project cladding legend from processed Risk
Faces.

Check the **Cladding** tab and review the wall type cladding mapping.

The current workflow supports a maximum of **four unique cladding
descriptions**.

Unused project slots are shown as **N/A**.

If more than four unique cladding descriptions are present, the cladding
normalisation workflow cannot complete normally.

------------------------------------------------------------------------

## Risk Face Graphics Are Missing

Risk Matrix requires a Revit solid fill pattern to apply the Risk Face
surface colour.

Also check that:

-   the current view supports element overrides;
-   the view is not a template; and
-   the affected wall has been processed as a Risk Face.

Remember that the overrides are view-specific.

------------------------------------------------------------------------

## Reset Risk Matrix Removed More Than Expected

**Reset Risk Matrix** is intentionally a project-wide reset.

It clears Risk Matrix information from exterior walls, clears associated
Risk Matrix project parameters, removes Risk Face graphical overrides
from Risk Views, removes Risk Matrix tags and clears the Risk Face
numbering state.

For a local correction, use the individual face-reset workflow instead.

!!! warning "Use the full reset carefully"

    **Reset Risk Matrix** is intended for clearing the Risk Matrix workflow across the project, not for correcting a single wall.

------------------------------------------------------------------------

## I Cannot Find a Final Risk Score

The current version of Risk Matrix does not yet calculate and present
the completed E2 score for each Risk Face.

The current workflow prepares the Risk Faces, model parameters, cladding
coordination, colours and tags used by the assessment/documentation
process.

Automated per-face scoring and confirmation are planned for future
development.

------------------------------------------------------------------------

## Reporting a Problem

If the problem continues, record:

-   the Revit version;
-   the active Risk View;
-   the affected Risk Face or wall;
-   the Project Information Wind Zone;
-   the Project Risk Values selected in Risk Matrix;
-   what you expected to happen;
-   what happened instead;
-   any message displayed by Flow; and
-   a screenshot of Risk Matrix and the affected Risk View where useful.

------------------------------------------------------------------------

## Related Help

-   [Risk Matrix](index.md)
-   [Identifying Risk Faces](identifying-risk-faces.md)
-   [Assigning Risk Information](assigning-risk-information.md)
-   [Reviewing Risk Results](reviewing-risk-results.md)
-   [Risk Documentation](risk-documentation.md)
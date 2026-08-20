# Visibility Manager Troubleshooting

Use the following checks if Visibility Manager or one of its controls is
not behaving as expected.

------------------------------------------------------------------------

## Visibility Manager Is Not Open

Open Visibility Manager from the Revit ribbon:

**Flow → Content → Visibility**

Visibility Manager reads the available controls for the current Revit
context when it opens.

------------------------------------------------------------------------

## The Displayed State Does Not Look Correct

Select **Refresh** in Visibility Manager.

This reads the current visibility states again and updates the controls.

!!! tip "Refresh after changing Revit context"

    Refresh is particularly useful after changing the active view or after a related setting has been changed elsewhere in Revit.

------------------------------------------------------------------------

## A Control Is Disabled or Unavailable

Some controls are only available when the Revit setting, parameter,
category, element or view required by that control can be changed.

Check the control information for its current state.

For **3D Doors**, **Draft Graphics** and **NFC Graphics**, confirm that
the project contains the required Flow global parameter.

For **Section Box**, confirm that you are working in an applicable 3D
view with a section box that can be shown or hidden.

!!! info "Unavailable does not always mean an error"

    A control may be unavailable because it does not apply to the current project or active view.

------------------------------------------------------------------------

## A Project Graphics Control Does Not Work

The **3D Doors**, **Draft Graphics** and **NFC Graphics** controls rely
on project global parameters.

The required parameters are:

-   **3D Doors** --- `3D Doors Show`
-   **Draft Graphics** --- `Draft Graphics Show`
-   **NFC Graphics** --- `NFC Show`

If the required parameter is missing or is not available as the expected
Yes/No setting, the control cannot perform its normal toggle.

See [**Project Controls**](project-controls.md).

------------------------------------------------------------------------

## An Active View Control Affects the Wrong View

Check which Revit view is currently active.

The **Reference Planes**, **Room Layout Mode**, **Grid Bubbles** and
**Section Box** controls use the active Revit view as their working
context.

1.  Open the required Revit view.
2.  Return to Visibility Manager.
3.  Select **Refresh** if required.
4.  Apply the control again.

------------------------------------------------------------------------

## Reference Planes Behave Differently Than Expected

Check whether the active view has an assigned view template.

The **Reference Planes** control is configured to prefer the assigned
view template where applicable.

A change may therefore be associated with the template-controlled
visibility rather than only the individual active view.

!!! note "Check the view template"

    If several views use the same template, a template-controlled visibility change may be relevant to those views as well.

------------------------------------------------------------------------

## Room Layout Mode Changes More Than One Setting

This is expected.

**Room Layout Mode** is a coordinated working mode rather than a simple
Room Separation Lines visibility switch.

It manages room separation line visibility together with the related
floor visibility required by the room-layout workflow.

See [**Active View Controls**](active-view-controls.md).

------------------------------------------------------------------------

## Grid Bubbles Are Not Where I Expected

The **Grid Bubbles** control does more than show or hide the bubbles.

When grid bubbles are shown, the control also manages their displayed
position for vertical and horizontal grids.

If the result appears incorrect, confirm that you are in the intended
view and select **Refresh** before trying the control again.

------------------------------------------------------------------------

## Section Box Is Unavailable

The **Section Box** control is intended to show or hide the section box
boundary in the active 3D view.

Check that:

1.  The active view is an applicable 3D view.
2.  A section box is present.
3.  The section box can be shown or hidden in that view.

------------------------------------------------------------------------

## Colour Tabs Does Not Affect Model Visibility

This is expected.

**Colour Tabs** is an **Application** control. It colours open Revit
document tabs to make projects easier to distinguish.

It does not change visibility inside the Revit model or active view.

------------------------------------------------------------------------

## I Am Not Sure Which Control to Use

Use:

-   **Project Graphics** for 3D Doors, Draft Graphics and NFC Graphics.
-   **Working Aids** for Reference Planes and Room Layout Mode.
-   **Datum Graphics** for Grid Bubbles.
-   **View Controls** for Section Box.
-   **Application** for Colour Tabs.

Hover over an individual control for additional information about what
it affects.

------------------------------------------------------------------------

## Still Having Problems?

If the problem continues, record:

-   The visibility control involved
-   Your Revit version
-   Your Flow version
-   The active Revit view
-   What you expected to happen
-   What happened instead

Where relevant, also note whether the view has an assigned view
template.

A screenshot showing both Visibility Manager and the affected Revit view
can help identify the problem.

!!! info "Screenshots are useful"

    Where possible, include both Visibility Manager and the affected Revit view.

    This helps show the control state and the Revit context in which it was being used.

------------------------------------------------------------------------

## Related Help

-   [**Visibility Manager**](index.md)
-   [**Project Controls**](project-controls.md)
-   [**Active View Controls**](active-view-controls.md)
-   [**Flow Hub**](../flow-hub/index.md)
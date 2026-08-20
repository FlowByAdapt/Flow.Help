# Active View Controls

The active-view controls in Visibility Manager provide quick access to
working and visibility settings for the Revit view you are currently
using.

They are organised under **Working Aids**, **Datum Graphics** and **View
Controls**.

------------------------------------------------------------------------

## Open Active View Controls

Open:

**Flow → Content → Visibility**

The active-view controls are:

### Working Aids

-   **Reference Planes**
-   **Room Layout Mode**

### Datum Graphics

-   **Grid Bubbles**

### View Controls

-   **Section Box**

!!! info "The active view determines the context"

    Check that the required Revit view is active before changing an active-view control.

------------------------------------------------------------------------

## Reference Planes

Use **Reference Planes** to show or hide reference planes in the active
view.

Where the active view has an assigned view template, the control is
designed to prefer the view template so the visibility setting remains
consistent with the template-controlled view.

!!! note "View templates can affect the result"

    Reference Plane visibility may be controlled through the active view's assigned view template rather than only the individual view.

------------------------------------------------------------------------

## Room Layout Mode

Use **Room Layout Mode** when working with room layouts.

Enabling the mode shows room separation lines and coordinates the
related floor visibility required for the room-layout workflow.

Disabling the mode returns the coordinated visibility state.

Because this is a working mode rather than a simple visibility switch,
the control uses **Enable** and **Disable** rather than Show and Hide.

------------------------------------------------------------------------

## Grid Bubbles

Use **Grid Bubbles** to show or hide grid bubbles in the active view.

The control works with both vertical and horizontal grids and manages
the position of the displayed grid bubbles when they are shown.

!!! tip "Use this for view-specific grid presentation"

    Grid Bubble changes apply to the active view rather than changing grid presentation throughout the project.

------------------------------------------------------------------------

## Section Box

Use **Section Box** to show or hide the section box boundary in the
active 3D view.

This changes the visibility of the section box element without removing
the section box itself.

!!! info "Section Box requires an applicable 3D view"

    The control is intended for an active 3D view containing a section box that can be shown or hidden.

------------------------------------------------------------------------

## Change an Active View Control

1.  Open the Revit view you want to work with.
2.  Locate the required control in Visibility Manager.
3.  Review its current state and description.
4.  Select the switch.
5.  Visibility Manager applies the change and refreshes the displayed
    state.

If you change to another Revit view while Visibility Manager is open,
use **Refresh** if you need to immediately confirm the controls for the
new view.

------------------------------------------------------------------------

## Project or Active View?

Use **Project Graphics** when you want to change the project-wide Flow
graphics settings for **3D Doors**, **Draft Graphics** or **NFC
Graphics**.

Use the active-view controls when the setting relates specifically to
the view you are currently working in.

See [**Project Controls**](project-controls.md).

------------------------------------------------------------------------

## Related Help

-   [**Visibility Manager**](index.md)
-   [**Project Controls**](project-controls.md)
-   [**Troubleshooting**](troubleshooting.md)
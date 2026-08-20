# Project Controls

The project controls in Visibility Manager provide quick access to Flow
graphics settings that apply across the current Revit project.

They are grouped under **Project Graphics**.

------------------------------------------------------------------------

## Open Project Controls

Open:

**Flow → Content → Visibility**

Locate the **Project Graphics** group.

The group contains:

-   **3D Doors**
-   **Draft Graphics**
-   **NFC Graphics**

------------------------------------------------------------------------

## Change a Project Control

1.  Locate the required control under **Project Graphics**.
2.  Review its current state.
3.  Select the switch to show or hide the graphics.
4.  Visibility Manager applies the change and refreshes the displayed
    state.

!!! tip "The switch reflects the current project setting"

    Visibility Manager reads the underlying Revit setting rather than maintaining a separate visibility preference.

------------------------------------------------------------------------

## 3D Doors

Use **3D Doors** to show or hide the project's 3D door graphics.

The control operates the Flow project setting associated with the **3D
Doors Show** global parameter.

Turn the control **on** when 3D door graphics are required.

Turn the control **off** when those graphics should be hidden.

------------------------------------------------------------------------

## Draft Graphics

Use **Draft Graphics** to show or hide drafting graphics across the
project.

The control operates the Flow project setting associated with the
**Draft Graphics Show** global parameter.

Turn the control **on** when the project's drafting graphics should be
shown.

Turn the control **off** when they should be hidden.

------------------------------------------------------------------------

## NFC Graphics

Use **NFC Graphics** to show or hide NFC graphics across the project.

The control operates the Flow project setting associated with the **NFC
Show** global parameter.

Turn the control **on** when NFC graphics should be shown.

Turn the control **off** when they should be hidden.

------------------------------------------------------------------------

## If a Project Control Is Unavailable

Project Graphics controls rely on the corresponding Flow global
parameters being available in the current project.

If a required parameter is unavailable or cannot be controlled, the
corresponding Visibility Manager control may not be available for use.

See [**Troubleshooting**](troubleshooting.md).

!!! info "Project controls are not active-view controls"

    These controls operate project graphics settings.

    For controls that apply specifically to the current view, use the controls under **Working Aids**, **Datum Graphics** and **View Controls**.

See [**Active View Controls**](active-view-controls.md).

------------------------------------------------------------------------

## Related Help

-   [**Visibility Manager**](index.md)
-   [**Active View Controls**](active-view-controls.md)
-   [**Troubleshooting**](troubleshooting.md)
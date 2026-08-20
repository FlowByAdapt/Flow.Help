# Visibility Manager

The **Visibility Manager** brings common Revit visibility and working
controls together in one place.

It provides controls for project graphics, active-view working aids,
datum graphics, view controls and application-level document tab
colouring.

------------------------------------------------------------------------

## Open Visibility Manager

On the Revit ribbon:

**Flow → Content → Visibility**

Visibility Manager opens and reads the current state of the available
controls.

!!! tip "Refresh the displayed states"

    If Revit has changed since Visibility Manager was opened, select **Refresh** to read the current control states again.

------------------------------------------------------------------------

## Available Controls

Visibility Manager organises controls according to their purpose.

### Project Graphics

These controls affect project-wide graphics driven by Flow project
parameters:

-   **3D Doors** --- show or hide 3D door graphics across the project.
-   **Draft Graphics** --- show or hide drafting graphics across the
    project.
-   **NFC Graphics** --- show or hide NFC graphics across the project.

See [**Project Controls**](project-controls.md).

### Working Aids

These controls affect the active view or, where applicable, its assigned
view template:

-   **Reference Planes** --- show or hide reference planes.
-   **Room Layout Mode** --- coordinate room separation line and floor
    visibility for room-layout work.

### Datum Graphics

-   **Grid Bubbles** --- show, hide and reposition grid bubbles in the
    active view.

### View Controls

-   **Section Box** --- show or hide the section box boundary in the
    active 3D view.

See [**Active View Controls**](active-view-controls.md).

### Application

-   **Colour Tabs** --- enable or disable coloured Revit document tabs
    to make open projects easier to distinguish.

!!! info "Colour Tabs is an application control"

    Colour Tabs applies to the Revit application rather than only the current project or active view.

------------------------------------------------------------------------

## Change a Control

Each available control is shown as a switch.

1.  Locate the required control.
2.  Review its current state and description.
3.  Select the switch.
4.  Visibility Manager applies the change and refreshes the displayed
    state.

Most visibility controls use **Show** and **Hide** behaviour.

**Room Layout Mode** and **Colour Tabs** use **Enable** and **Disable**
because they control a working mode or application feature rather than
the visibility of a single item.

!!! tip "Check the control information"

    Hover over an individual control for additional information about what it affects.

------------------------------------------------------------------------

## Understand Control Scope

Visibility Manager contains three control scopes.

**Project** controls affect graphics more broadly across the current
Revit project.

**Active View** controls affect the currently active view or, where
supported, its assigned view template.

**Application** controls affect the wider Revit interface rather than a
single project or view.

!!! info "Groups and scope are different"

    Controls are grouped in Visibility Manager by purpose, such as **Project Graphics**, **Working Aids**, **Datum Graphics**, **View Controls** and **Application**.

    The scope determines where the change is applied.

------------------------------------------------------------------------

## Use Controls from Flow Hub

Visibility Manager controls can also be configured as shortcuts in
**Flow Hub**.

Select **Hub Shortcuts** in Visibility Manager to choose the visibility
controls you want available from the Hub.

This is useful for controls you use frequently without needing to open
the full Visibility Manager each time.

------------------------------------------------------------------------

## Use Controls from Command Palette

Visibility Manager controls are also available through the **Command
Palette**.

Use Command Palette when you know the control you want and prefer to
find and run it directly.

------------------------------------------------------------------------

## Acknowledgements

Visibility Manager brings a number of visibility and interface controls
into a unified Flow workflow.

Some individual features were inspired by tools and concepts from the
wider Revit development community.

### Section Box

The **Section Box** visibility control was inspired by functionality
available through pyRevit.

Flow's implementation has been independently developed and integrated
into Visibility Manager.

### Colour Tabs

The **Colour Tabs** control was inspired by document tab colouring
functionality available through pyRevit.

Flow's implementation has been independently developed and integrated
into Visibility Manager.

------------------------------------------------------------------------

## Getting Help

Hover over **Visibility** on the Flow ribbon and press **F1** to return
directly to this page.

------------------------------------------------------------------------

## Related Help

-   [**Project Controls**](project-controls.md)
-   [**Active View Controls**](active-view-controls.md)
-   [**Troubleshooting**](troubleshooting.md)
-   [**Workspace Panel**](../index.md)
-   [**Flow Hub**](../flow-hub/index.md)
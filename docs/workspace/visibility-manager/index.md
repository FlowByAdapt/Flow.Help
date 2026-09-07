# Visibility Manager

The **Visibility Manager** brings common Revit visibility, working and interface controls together in one place.

It provides controls for project graphics, active-view working aids, datum graphics, view controls and application-level document tab colouring.

---

## Open Visibility Manager

On the Revit ribbon:

**Flow → Content → Visibility**

Visibility Manager opens and reads the current state of all registered controls from Revit.

<!-- SCREENSHOT: Visibility Manager overview.
Show the complete window with Project Graphics, Working Aids, Datum Graphics,
View Controls and Application visible. -->

---

## First-Time Workflow

A typical workflow is:

1. Open the Revit project and view you want to work with.
2. Open **Flow → Content → Visibility**.
3. Review the current state of the required control.
4. Select its switch.
5. Flow applies the change through Revit.
6. Visibility Manager refreshes the displayed control states.

Controls that cannot be used in the current Revit context are shown as unavailable rather than applying an unsupported change.

---

## Available Controls

Visibility Manager organises controls according to their purpose.

### Project Graphics

These controls operate Flow project graphics settings backed by project global parameters:

- **3D Doors** — show or hide 3D door graphics across the project.
- **Draft Graphics** — show or hide drafting graphics across the project.
- **NFC Graphics** — show or hide NFC graphics across the project.

See [**Project Controls**](project-controls.md).

### Working Aids

These controls relate to the active view or, where applicable, its assigned view template:

- **Reference Planes** — show or hide reference planes.
- **Room Layout Mode** — coordinate Room Separation Line visibility and, when working through an assigned view template, related Floor visibility.

### Datum Graphics

- **Grid Bubbles** — show or hide grid bubbles and standardise the displayed bubble end in the active view.

### View Controls

- **Section Box** — show or hide the section box boundary in the active 3D view.

See [**Active View Controls**](active-view-controls.md).

### Application

- **Colour Tabs** — enable or disable coloured Revit document tabs to make open projects easier to distinguish.

---

## Change a Control

Each available control is shown as a switch.

1. Locate the required control.
2. Review its current state and description.
3. Select the switch.
4. Flow applies the requested change.
5. Visibility Manager reads the resulting states from Revit again.

Most visibility controls use **Show** and **Hide** behaviour.

**Room Layout Mode** and **Colour Tabs** use **Enable** and **Disable** because they control a working mode or application feature rather than the visibility of a single item.

!!! tip "Check the control information"

    Hover over an individual control for additional information about what it affects.

---

## Control States and Refresh

Visibility Manager reads control state from Revit rather than maintaining a separate display preference.

It refreshes automatically:

- when the Visibility Manager opens;
- after a Visibility Manager control is changed successfully; and
- while the window is visible when Flow reports a shared command-state change.

You can also select **Refresh** manually.

!!! tip "When to use Refresh"

    Manual **Refresh** is particularly useful after changing the active Revit view or after a related setting has been changed directly in Revit.

---

## Understand Control Scope

Visibility Manager contains three main control scopes.

**Project** controls affect Flow graphics settings across the current Revit project.

**Active View** controls use the currently active Revit view as their working context. Some controls deliberately operate through the view's assigned template when one is present.

**Application** controls affect the wider Revit interface rather than a single project or view.

!!! info "Groups and scope are different"

    Controls are grouped in Visibility Manager by purpose, such as **Project Graphics**, **Working Aids**, **Datum Graphics**, **View Controls** and **Application**.

    The scope describes where the underlying change is applied.

---

## Colour Tabs

**Colour Tabs** colours open Revit document tabs so different open documents are easier to distinguish.

Use the Colour Tabs switch to:

- **Enable** document tab colouring; or
- **Disable** document tab colouring.

Colour Tabs is an **Application** control. It does not change model or view visibility.

---

## Tab Colour Settings

Visibility Manager also provides dedicated settings for how Project and Family document tabs are presented.

Open **Tab Colour Settings** to configure the tab style for:

- **Project tabs**
- **Family tabs**

The default styles are:

- **Project tabs — Background Fill**
- **Family tabs — Top Bar Medium**

The settings window provides previews so the two styles can be reviewed before saving.

<!-- SCREENSHOT: Tab Colour Settings window.
Show both Project Tab Style and Family Tab Style selectors and their previews. -->

### Save Settings

Select **Save** to store the current tab-style choices.

If Colour Tabs is already enabled, Flow immediately reapplies the saved settings to the currently open Revit document tabs.

### Reset Defaults

Select **Reset Defaults** to return the settings shown in the window to the default Project and Family tab styles.

Save the settings when you are ready to apply and retain the selection.

!!! info "Colour settings are user settings"

    Flow stores the document tab colour settings in the current user's Flow configuration.

    If no valid saved settings are available, Flow uses the default styles.

---

## Use Controls from Flow Hub

Visibility Manager controls can also be configured as shortcuts in **Flow Hub**.

Select **Hub Shortcuts** in Visibility Manager to choose up to three eligible controls that you want available directly from the Hub.

This is useful for controls you use frequently without needing to open the full Visibility Manager each time.

See [**Flow Hub Workspace Controls**](../flow-hub/workspace-controls.md).

---

## Use Controls from Command Palette

Visibility Manager controls are also exposed through **Command Palette**.

Use Command Palette when you know the control you want and prefer to find and run it directly.

See [**Command Palette**](../command-palette/index.md).

---

## Acknowledgements

Visibility Manager brings a number of visibility and interface controls into a unified Flow workflow.

Some individual features were inspired by tools and concepts from the wider Revit development community.

### Section Box

The **Section Box** visibility control was inspired by functionality available through pyRevit.

Flow's implementation has been independently developed and integrated into Visibility Manager.

### Colour Tabs

The **Colour Tabs** control was inspired by document tab colouring functionality available through pyRevit.

Flow's implementation has been independently developed and integrated into Visibility Manager.

---

## Getting Help

Hover over **Visibility** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

- [**Project Controls**](project-controls.md)
- [**Active View Controls**](active-view-controls.md)
- [**Troubleshooting**](troubleshooting.md)
- [**Workspace Panel**](../index.md)
- [**Flow Hub**](../flow-hub/index.md)

# Workspace

The **Workspace** tool helps you save, restore and recover the arrangement of supported Revit and Flow windows across your monitors.

It is particularly useful when you regularly move between different monitor setups or want to return Revit to a known working arrangement.

---

## Open Workspace

On the Revit ribbon:

**Flow → Workspace → Workspace**

The Workspace window provides access to:

- the current Revit and Flow window environment;
- saved workspace layouts;
- workspace save, restore and management controls; and
- window recovery tools.

<!-- SCREENSHOT: Workspace overview.
Show the full Workspace window with the window explorer and Saved Workspaces area visible. -->

---

## What Is a Workspace?

A saved workspace records a supported window arrangement together with the monitor configuration it was created for.

A workspace can include:

- supported Revit floating windows and palettes;
- recognised Flow windows;
- registered Flow dockable panes;
- their saved positions and sizes; and
- the monitor arrangement used when the workspace was captured.

The **Workspace window itself is not included** in the saved window arrangement.

!!! info "Workspaces are monitor-specific"

    A saved workspace can only be restored when the current monitor arrangement matches the arrangement for which it was saved.

    This prevents windows from being restored to coordinates that do not belong to the current desktop.

---

## First-Time Workflow

A typical Workspace workflow is:

1. Arrange Revit and Flow windows the way you want them.
2. Open **Flow → Workspace → Workspace**.
3. Select **Save Workspace**.
4. Give the layout a meaningful name.
5. Continue working normally.
6. When you want to return to the arrangement, select the saved layout and choose **Restore**.

For example, you might save separate layouts for:

- **Office Dual Monitor**
- **Home**
- **Laptop**

See [**Saving a Workspace**](saving-a-workspace.md) and [**Restoring a Workspace**](restoring-a-workspace.md).

---

## Saved Workspace Suggestion

When saved layouts are loaded, Flow tries to select one that matches the current monitor arrangement.

If more than one saved workspace matches, Flow prefers the most recently created matching layout.

If no saved workspace matches the current monitors, Flow falls back to the first available saved layout.

!!! warning "Selection does not guarantee compatibility"

    Always check the selected workspace before restoring it.

    Flow performs a full monitor compatibility check when the restore is requested.

---

## Save a Workspace

Use **Save Workspace** to capture the current supported window and monitor arrangement as a new named layout.

Workspace names must be unique.

If the name already exists, select the existing layout and use **Update** instead.

➡️ [**Saving a Workspace**](saving-a-workspace.md)

---

## Restore a Workspace

Select a saved workspace and choose **Restore** to return supported windows and Flow panes to the saved arrangement.

Before restoration begins, Flow verifies that the current monitor topology matches the saved one.

Recognised Flow windows that formed part of the saved arrangement may be reopened if required.

➡️ [**Restoring a Workspace**](restoring-a-workspace.md)

---

## Manage Saved Workspaces

Existing layouts can be:

- **Updated**
- **Renamed**
- **Deleted**

Updating a workspace captures the current environment again and replaces the selected saved arrangement.

➡️ [**Managing Saved Workspaces**](managing-saved-workspaces.md)

---

## Recover Windows

Recovery is different from restoring a workspace.

Use **Recover** when a Revit or Flow window has opened outside the visible desktop.

You can recover:

- a selected window; or
- all off-screen windows.

A saved workspace is **not required** for window recovery.

➡️ [**Recovering Windows**](recovering-windows.md)

---

## Flow Hub

Common Workspace functions are also available directly from **Flow Hub**.

The Hub can:

- suggest a saved layout for the current monitor arrangement;
- restore a selected workspace;
- open the full Workspace interface; and
- recover off-screen windows.

See [**Flow Hub Workspace Controls**](../flow-hub/workspace-controls.md).

---

## Saved Workspace Data

Saved workspaces are stored as settings for the current Windows user.

They are not embedded in the Revit project.

This allows different users to maintain workspace arrangements appropriate to their own monitors and working environment.

---

## Getting Help

Hover over **Workspace** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

- [**Saving a Workspace**](saving-a-workspace.md)
- [**Restoring a Workspace**](restoring-a-workspace.md)
- [**Managing Saved Workspaces**](managing-saved-workspaces.md)
- [**Recovering Windows**](recovering-windows.md)
- [**Flow Hub**](../flow-hub/index.md)

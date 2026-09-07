# Saving a Workspace

Save a workspace when you want to return later to the current arrangement of supported Revit and Flow windows.

Each saved workspace also records the monitor configuration it was created for.

---

## Before You Save

Arrange your Revit environment the way you want it.

For example:

1. Position Revit on the required monitor.
2. Arrange supported floating Revit and Flow windows.
3. Show or hide registered Flow dockable panes as required.
4. Position the Flow Hub and other supported dockables.
5. Check that the overall arrangement is the one you want to return to.

Then open:

**Flow → Workspace → Workspace**

---

## Save the Current Workspace

1. Select **Save Workspace**.
2. Enter a meaningful workspace name.
3. Confirm the save.
4. Flow captures the current supported window and monitor arrangement.
5. The new workspace is added to the Saved Workspaces list.

<!-- SCREENSHOT: Saved Workspaces area.
Show several sensibly named layouts such as Office Dual Monitor, Home and Laptop. -->

---

## Naming Workspaces

Use names that describe the environment rather than the task.

Good examples include:

- **Office Dual Monitor**
- **Office Single Monitor**
- **Home**
- **Laptop**

This makes it easier to select an appropriate layout later.

### Duplicate Names

Workspace names must be unique regardless of capitalisation.

If you try to save a name that already exists, Flow does not overwrite it automatically.

Select the existing workspace and use **Update** if you want to replace its saved arrangement.

---

## What Flow Saves

A saved workspace records the current monitor topology and supported window arrangement.

This includes information such as:

- monitor positions and sizes;
- which monitor is the primary display;
- supported window positions and sizes;
- recognised Flow window identity where available; and
- registered Flow dockable-pane shown/hidden state.

Flow also captures information relating to the Revit **Properties** and **Project Browser** panes for the workspace model.

!!! info "Not every native window is a workspace candidate"

    Workspace is designed around supported Revit and Flow working windows.

    It does not attempt to save every temporary dialog, message or operating-system window that happens to be open.

---

## Workspace Window Exclusion

The **Flow Workspace** window itself is deliberately excluded from the saved window arrangement.

This prevents the management window from becoming part of the workspace it is being used to create.

---

## Monitor Configuration

The saved monitor topology includes more than the number of connected displays.

For restoration, Flow compares:

- monitor count;
- monitor position;
- monitor width and height; and
- which monitor is the primary display.

A workspace saved for one physical desktop arrangement therefore may not restore after the monitors have been rearranged, even if the same number of displays is still connected.

!!! tip "Save layouts for the environments you actually use"

    If you regularly work with substantially different monitor arrangements, save a workspace for each arrangement.

---

## Saved Workspaces Are User-Specific

Saved layouts belong to the current Windows user's Flow configuration.

They are not saved inside the Revit project.

The workspace library is stored under the user's Flow application data.

---

## Change an Existing Workspace

Do not create a new workspace merely because the window positions have changed.

If you want to replace an existing saved layout with the current arrangement, use **Update**.

See [**Managing Saved Workspaces**](managing-saved-workspaces.md).

---

## Next Step

When you want to return to the saved arrangement, see:

➡️ [**Restoring a Workspace**](restoring-a-workspace.md)

---

## Related Help

- [**Workspace**](index.md)
- [**Restoring a Workspace**](restoring-a-workspace.md)
- [**Managing Saved Workspaces**](managing-saved-workspaces.md)
- [**Recovering Windows**](recovering-windows.md)

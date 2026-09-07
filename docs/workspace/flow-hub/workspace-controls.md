# Workspace Controls

Flow Hub provides quick access to common **Workspace** and **Visibility Manager** functions.

These controls allow you to restore a saved workspace, open the main Workspace tool, recover windows and operate selected visibility controls without leaving the Hub.

---

## Restore a Saved Workspace

The **Layout** selector displays your available saved workspace layouts.

To restore one:

1. Review the layout currently selected.
2. Choose another saved layout if required.
3. Click **Restore**.
4. Flow submits the workspace restoration through Revit's external-event workflow.

The layout must already have been saved using the Flow Workspace tools.

See [**Restoring a Workspace**](../workspace/restoring-a-workspace.md).

---

## Suggested Workspace

When saved layouts are loaded, Flow tries to select a layout that matches the current monitor arrangement.

If more than one saved layout matches, Flow prefers the most recently created matching layout.

If no monitor match is found, the first available saved layout is selected.

!!! info "Check the selected layout"

    The suggested layout is only a starting selection.

    You can choose another saved layout before clicking **Restore**.

---

## Restore Already Pending

Only one workspace restore request can be pending at a time.

If another restore is already waiting to run, Flow shows:

**Workspace Restore Pending**

Wait until the current restore has completed before requesting another.

---

## Manage Workspaces

Select:

**Manage**

to open the full Flow Workspace interface.

Use the main Workspace tool when you need to create, manage or review saved layouts rather than simply restoring one from the Hub.

See [**Workspace**](../workspace/index.md).

---

## Recover Windows

Select:

**Recover**

when Revit or Flow windows have opened outside the visible desktop.

Flow captures the current application window state and attempts to move affected windows back onto the available desktop area.

This can be useful after:

- changing monitor configurations;
- disconnecting a laptop from external monitors;
- moving between workstations; or
- opening a window that was previously positioned on a monitor that is no longer connected.

See [**Recovering Windows**](../workspace/recovering-windows.md).

---

## Visibility Manager Shortcuts

Flow Hub can display up to **three** preferred Visibility Manager controls.

Only Visibility Manager controls specifically configured as eligible Hub shortcuts can be selected.

The shortcuts are live controls. Flow requests their current state from Revit and updates the Hub to reflect whether each setting is currently on or off.

---

## Configure Visibility Shortcuts

Select:

**Configure**

to choose which eligible Visibility Manager controls appear in Flow Hub.

1. Select **Configure**.
2. Review the available shortcut options.
3. Select up to **three** controls.
4. Click **Save**.

The Hub updates when the settings are saved.

<!-- SCREENSHOT: Hub Shortcut Settings window.
Show the list of eligible controls, the “X of 3 shortcuts selected” message, Save and Cancel. -->

### Three-Shortcut Limit

The settings window actively enforces the three-shortcut limit.

Once three controls are selected:

- the selected controls remain enabled so they can be deselected;
- unselected controls become disabled; and
- another control cannot be selected until one of the existing three is cleared.

---

## Default Visibility Shortcuts

If no saved shortcut settings are available, Flow starts with three predefined shortcut selections corresponding to:

- **3D Doors**
- **Colour Tabs**
- **NFC**

These defaults can be changed at any time using **Configure**.

---

## Saving Shortcut Settings

Shortcut settings are stored as user configuration.

Saving the settings raises a shared change notification, allowing the Hub shortcut list to refresh without needing to reopen Revit.

---

## Open Visibility Manager

Use the full **Visibility Manager** when you need access to controls beyond the three shortcuts shown in Flow Hub.

The Hub shortcuts are intended for frequently used controls rather than replacing the full Visibility Manager.

---

## Hub Position

Flow Hub itself is a Revit dockable panel.

Its position can be included when saving a Flow workspace, allowing the Hub to return to its preferred location when that workspace is restored.

See [**Saving a Workspace**](../workspace/saving-a-workspace.md).

---

## Related Help

- [**Flow Hub**](index.md)
- [**Workspace**](../workspace/index.md)
- [**Saving a Workspace**](../workspace/saving-a-workspace.md)
- [**Restoring a Workspace**](../workspace/restoring-a-workspace.md)
- [**Recovering Windows**](../workspace/recovering-windows.md)
- [**Visibility Manager**](../visibility-manager/index.md)

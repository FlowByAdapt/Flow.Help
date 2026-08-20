# Workspace Controls

Flow Hub provides quick access to common **Workspace** and **Visibility Manager** functions.

These controls allow you to restore a saved workspace, recover windows and operate selected visibility controls without leaving the Hub.

---

## Restore a Saved Workspace

The **Layout** selector displays your available saved workspace layouts.

To restore a workspace:

1. Select the required workspace from the **Layout** list.
2. Click **Restore**.
3. Flow restores the selected Revit workspace layout.

The selected workspace must already have been saved using the Flow Workspace tools.

See [**Restoring a Workspace**](../workspace/restoring-a-workspace.md).

---

## Suggested Workspace

When available workspace layouts are loaded, Flow attempts to select a layout that matches the current monitor arrangement.

If more than one matching layout is available, the most recently created matching layout is preferred.

If no matching layout is found, the first available saved layout is selected.

!!! info "Check the selected layout"

    The Layout list provides a convenient starting selection, but you can choose another saved workspace before selecting **Restore**.

---

## Manage Workspaces

Select:

**Manage**

to open the main Flow Workspace interface.

Use the full Workspace tools when you need to manage saved layouts rather than simply restoring one from the Hub.

See [**Workspace**](../workspace/index.md)

---

## Recover Windows

Select:

**Recover**

when a Revit or Flow window has opened outside the visible desktop.

Flow attempts to bring affected windows back onto the available screen area.

This can be useful after:

- changing monitor configurations;
- disconnecting a laptop from external monitors;
- moving between different workstations; or
- opening a window that was previously positioned on a monitor that is no longer connected.

See [**Recovering Windows**](../workspace/recovering-windows.md).

---

## Visibility Manager Shortcuts

Flow Hub can display up to **three** of your preferred Visibility Manager controls.

These are live controls, allowing frequently used visibility settings to be switched directly from the Hub without opening the full Visibility Manager.

The current state of each shortcut is refreshed from Revit so the Hub reflects whether the corresponding visibility setting is currently on or off.

---

## Configure Visibility Shortcuts

Select:

**Configure**

to choose which Visibility Manager controls appear in Flow Hub.

1. Select **Configure**.
2. Review the Visibility Manager controls available as Hub shortcuts.
3. Select up to **three** controls.
4. Click **Save**.

The selected controls are then displayed in the Hub.

!!! info "Maximum of three"

    Flow Hub is intentionally limited to three Visibility Manager shortcuts so the Workspace area remains compact.

    When three controls are selected, additional controls cannot be selected until one of the existing selections is cleared.

---

## Default Visibility Shortcuts

A new configuration initially includes three predefined Visibility Manager shortcuts.

These can be changed at any time using **Configure**.

!!! tip "Choose controls you use throughout the day"

    The Hub shortcuts are most useful for Visibility Manager controls that you regularly switch while working.

    Less frequently used visibility controls remain available through the full Visibility Manager.

---

## Open Visibility Manager

Use the full **Visibility Manager** when you need access to controls beyond the three shortcuts displayed in Flow Hub.

The Hub shortcuts are intended as quick access to your preferred controls rather than a replacement for the full Visibility Manager.

---

## Hub Position

Flow Hub itself is a Revit dockable panel.

Its position can be included when saving a Flow workspace, allowing the Hub to return to its preferred position when that workspace is restored.

See [**Saving a Workspace**](../workspace/saving-a-workspace.md).

---

## Related Help

- [**Flow Hub**](index.md)
- [**Workspace**](../workspace/index.md)
- [**Saving a Workspace**](../workspace/saving-a-workspace.md)
- [**Recovering Windows**](../workspace/recovering-windows.md)
- [**Visibility Manager**](../visibility-manager/index.md)
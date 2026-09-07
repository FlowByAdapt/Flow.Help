# Managing Saved Workspaces

Use the Workspace management controls to update, rename or delete existing saved layouts.

Open:

**Flow → Workspace → Workspace**

Then select the required workspace from the Saved Workspaces list.

---

## Update a Workspace

Use **Update** when you want an existing workspace name to represent the arrangement you are using now.

1. Arrange the current Revit and Flow environment as required.
2. Select the saved workspace you want to replace.
3. Select **Update**.
4. Confirm the update.
5. Flow captures the current workspace again.
6. The selected saved layout is replaced while retaining its name.

!!! warning "Update replaces the saved arrangement"

    Update performs a new workspace capture.

    It can replace the saved:

    - monitor topology;
    - supported window positions and sizes; and
    - registered Flow pane state.

    It is not limited to updating one moved window.

Use **Update** only when the current environment is the arrangement you want stored under that workspace name.

---

## Rename a Workspace

Use **Rename** when the saved arrangement is correct but its name should change.

1. Select the workspace.
2. Select **Rename**.
3. Enter the new name.
4. Confirm the change.

Renaming changes the stored workspace name without recapturing the current Revit environment.

The saved monitor and window arrangement is retained.

### Duplicate Names

Workspace names must remain unique regardless of capitalisation.

Flow rejects a new name when another saved workspace already uses it.

---

## Delete a Workspace

Use **Delete** when a saved layout is no longer required.

1. Select the workspace.
2. Select **Delete**.
3. Review the confirmation.
4. Confirm the deletion.

The selected workspace is removed from the saved workspace library.

!!! warning "Delete removes the saved layout"

    Deleting a workspace does not move or close the windows currently open in Revit.

    It removes the saved arrangement so it can no longer be restored.

---

## Save or Update?

Use **Save Workspace** when:

- the arrangement is new; or
- you want to keep the existing saved workspace and create another one.

Use **Update** when:

- the selected saved workspace should be replaced by the current arrangement.

If you try to save a workspace using an existing name, Flow directs you to use **Update** rather than silently overwriting it.

---

## Changing Monitor Setups

Because Update performs a complete new capture, it can also change the monitor topology associated with the workspace.

For example, if a workspace was originally saved for a dual-monitor office setup and you update it while using a single-monitor laptop setup, the workspace will then represent the newly captured monitor arrangement.

In many cases, keeping separately named workspaces for genuinely different environments is clearer.

---

## Related Help

- [**Workspace**](index.md)
- [**Saving a Workspace**](saving-a-workspace.md)
- [**Restoring a Workspace**](restoring-a-workspace.md)
- [**Recovering Windows**](recovering-windows.md)

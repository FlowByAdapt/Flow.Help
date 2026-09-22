# Connecting and Browsing

The **Browse** tab connects to a selected Revit Server version and presents its folders and models as a searchable tree.

Selecting an item displays information about the server, folder or model and enables the actions that apply to that item.

---

## Connecting to Revit Server

1. Enter the host address or IP address in **Server**.
2. Select **2025**, **2026** or **2027** from **Version**.
3. Select **Refresh**.
4. Wait for the connection status to show **Connected**.

Flow reloads the complete folder and model tree for the selected Revit Server version.

The connection indicator reports **Disconnected**, **Connecting**, **Connected** or **Connection failed**.

!!! info "Connection details are remembered"

    After a successful connection, Flow remembers the server address and selected Revit Server version for the next session.

---

## Browsing Server Content

Expand folders in the server tree to locate the required project or model.

When you select an item, the details panel can display information including:

- item name and type
- storage and free space for the server
- folder and model counts
- REST path
- model size
- model lock state
- model product version

A lock icon beside a model indicates that it is administratively locked and unavailable to users.

<!-- Screenshot recommended:
Show the Browse tab connected to an example server.
Include an expanded project folder, a selected model, its details panel and one locked-model indicator.
Replace project and server information with fictional examples.
-->

---

## Searching Folders and Models

Enter part of a folder or model name in **Search folders and models...**.

Flow filters the tree to matching items and preserves the parent folders required to show where each match is located. Matching branches are expanded automatically.

Clear the search text to return to the full server tree.

---

## Reviewing Model History

1. Select a model in the server tree.
2. Select **Load History**.
3. Review the latest history information in the details panel.
4. Select **View History** to open the complete revision history.

The latest history summary includes the date, user, version and comment where available.

---

## Opening Available Actions

Right-click a model or folder to display the actions available for that item.

Model actions include:

- **Add to Archive Workflow**
- **Add to Upgrade Workflow**
- **Lock Model**
- **Unlock Model**
- **Delete Model**

Folder actions include:

- **Add Folder to Archive Queue**
- **Add Folder to Upgrade Workflow**
- **Create Folder**
- **Rename Folder**
- **Move Folder**
- **Delete Folder**

Actions remain unavailable when they do not apply to the selected item, while the server is busy, or when the selected Revit Server version does not support write operations.

---

## Refreshing the Server

Select **Refresh** after server content has changed or when you want to retry a failed connection.

Flow reloads the server tree and attempts to preserve expanded folder locations where they still exist.

---

## Related Help

- [Flow Server](index.md)
- [Reviewing Server Activity](reviewing-activity.md)
- [Managing Server Content](managing-server-content.md)
- [Troubleshooting](troubleshooting.md)
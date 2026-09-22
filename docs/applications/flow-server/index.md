# Flow Server

**Flow Server** provides a central interface for browsing and administering Autodesk Revit Server content.

It brings server browsing, activity review, archiving, model upgrades and common administration tasks together in a standalone desktop application.

**Application:** **Flow Server**

---

## When to Use Flow Server

Use Flow Server when you need to:

- browse folders and models on Revit Server
- search for a project or model
- review recent project activity and model history
- create, rename, move or delete server folders
- lock or unlock a model
- archive an individual model or a complete project folder
- upgrade Revit Server models to a supported later version
- delete a model after confirming that the required archive is available

Flow Server is intended for controlled Revit Server administration. Operations that change or delete server content remain explicit and require confirmation where appropriate.

---

## Main Areas

### Browse

Connect to a Revit Server version, search its folder structure, inspect selected items and access model or folder administration commands.

[Connecting and Browsing](connecting-and-browsing.md)

### Activity

Scan the connected Revit Server for recent project activity, review model usage and open detailed model revision history.

[Reviewing Server Activity](reviewing-activity.md)

### Archive Queue

Prepare and run standalone archive jobs for individual models or complete folders. Successful standalone archives can optionally lock their source models.

[Archiving Projects](archiving-projects.md)

### Upgrade Workflow

Archive, upgrade and publish selected Revit Server models through a managed workflow while preserving the required project folder structure.

[Upgrading Projects](upgrading-projects.md)

---

## Server Administration

The **Browse** tab also provides commands for:

- creating folders
- renaming folders
- moving folders
- locking and unlocking models
- deleting models
- deleting folders and their contents

[Managing Server Content](managing-server-content.md)

---

## Changes Are Deliberate

Connecting, refreshing, searching and inspecting content do not modify Revit Server.

Actions that create, move, rename, lock, unlock, archive, upgrade or delete content must be started explicitly. Destructive and access-changing actions require confirmation.

!!! warning "Deletion is separate from archiving"

    Deleting a model or folder does not create an archive automatically.

    Confirm that any required archive has completed successfully and has been verified before deleting Revit Server content.

---

## Related Help

- [Getting Started](getting-started.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Troubleshooting](troubleshooting.md)
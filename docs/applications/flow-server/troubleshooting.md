# Flow Server Troubleshooting

This page covers common connection, archive, upgrade and administration issues in **Flow Server**.

For the normal workflow, start with [Flow Server](index.md).

---

## Flow Server Does Not Connect

Check:

- that the **Server** address or IP address is correct
- that the correct Revit Server **Version** is selected
- that the workstation can reach the server network
- that the matching Revit Server service is available at that address

Select **Refresh** to try the connection again.

If the attempt fails, the status area displays **Connection failed** together with the reported error.

---

## A Server Action Is Unavailable

Check that:

- Flow Server shows **Connected**
- the correct model or folder is selected
- no other Flow Server operation is running
- the selected Revit Server version is 2025, 2026 or 2027
- the action applies to the selected item

For upgrades, the target version must be later than the selected source version.

---

## The Archive Is Blocked Before It Starts

Flow checks source-model availability before running an immediate archive or archive queue.

The source may be:

- administratively locked
- temporarily unavailable
- affected by model locks in progress
- unable to be confirmed by the server

Resolve the reported condition, select **Refresh**, and try again.

For a queue, every pending source must pass this check before processing begins.

---

## The Archive Worker Fails

Check:

- that the matching Revit version is installed
- that Revit 2026 is version 2026.5 or later when archiving a 2026 model
- that the archive destination is accessible and writable
- that sufficient disk space is available
- that another application is not using the proposed output file
- the error shown in the queue or completion dialog

The archive source is not saved, synchronised, moved or deleted when the archive fails.

---

## The Folder Archive Destination Is Not Empty

When a complete server folder is queued, Flow creates a project archive location beneath the selected parent folder.

That project location must not already contain files. Choose another parent folder or review and remove the unwanted previous test archive before trying again.

---

## The Archive Succeeded but the Source Was Not Locked

Automatic source locking occurs only after Flow verifies that the standalone archive output exists and is non-empty.

If locking then fails, Flow keeps the successful archive result and reports the locking error separately.

Check the model's current lock state after selecting **Refresh**. If appropriate, use **Lock Model** manually.

---

## Run Workflow Is Unavailable

Check that:

- at least one item shows **Ready to Archive** or **Ready to Upgrade**
- another Flow Server operation is not running
- the selected target version is later than the source version
- the workflow has not already completed or been cleared

---

## The Upgrade Destination Already Exists

Flow blocks the workflow when the target project folder already exists.

The message identifies whether Flow found:

- an incomplete earlier Flow upgrade
- a completed earlier Flow upgrade
- an existing folder without a matching recovery record

Flow does not overwrite, add to or automatically remove the destination. Inspect the target carefully and remove it manually only when you have confirmed that it is safe to do so.

!!! warning "Do not remove a destination simply to clear the message"

    First confirm whether it contains a completed project, a recoverable partial upgrade or other server content that must be retained.

---

## An Upgrade Fails After Archiving

Review the **Status** and **Error** columns on the **Upgrade Workflow** tab.

The source archive and upgrade are separate stages. A successful archive does not guarantee that the later upgrade or publish stage will succeed.

Confirm:

- Revit 2027 and the upgrade worker are installed
- the target server is reachable
- the target project folder remains available
- the model can be upgraded by Revit
- linked models required by the project were included in the workflow

---

## Stop Does Not Close the Current Archive Immediately

**Stop Queue** requests cancellation after the current archive finishes. Remaining archive jobs are then cancelled.

This is expected behaviour and avoids interrupting the active Revit archive operation midway through processing.

---

## A Folder Cannot Be Renamed, Moved or Deleted

Some server folders are protected from these actions.

A move can also be blocked when:

- no valid destination folder is available
- the destination already contains a folder with the same name
- the source folder no longer exists at its original location

Select **Refresh** and review the current server structure before trying again.

---

## Reporting a Problem

Include:

- Flow Server version shown in **About**
- selected Revit Server version
- the workflow and command used
- the status or error message displayed by Flow
- whether the issue affects one model or a complete folder
- a screenshot with confidential project and server information obscured

---

## Related Help

- [Flow Server](index.md)
- [Getting Started](getting-started.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Archiving Projects](archiving-projects.md)
- [Upgrading Projects](upgrading-projects.md)
- [Managing Server Content](managing-server-content.md)
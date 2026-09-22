# Archiving Projects

The **Archive Queue** creates local `.rvt` archives from Revit Server models. You can archive one selected model or queue every model beneath a selected server folder.

Archive jobs run sequentially using the Revit version associated with their source server.

---

## Before You Start

Confirm that:

- Flow Server is connected to the correct server and Revit Server version
- the corresponding compatible Revit version is installed
- the source model is available and not locked or currently being processed
- the archive destination is accessible and has sufficient free space

For Revit 2026 archives, Revit 2026.5 or later is required by the current installer.

---

## Archiving a Selected Model Immediately

1. Open **Browse** and select the required model.
2. Select **Archive Model** in the details panel.
3. Choose the output `.rvt` file.
4. Review the source, output location and locking information.
5. Select **Archive**.
6. Wait for Flow to report the result.

Flow checks the source model before launching the archive worker. If the model is locked, unavailable or has model locks in progress, the archive is blocked before processing begins.

The source Revit Server model is not saved, synchronised, moved or deleted by the archive operation.

---

## Adding One Model to the Archive Queue

1. Select the model in **Browse**.
2. Right-click and select **Add to Archive Workflow**, or open **Archive Queue** and select **Add Selected Model**.
3. Choose the output `.rvt` file.
4. Review the new queue row.

If the same model is already pending for the selected Revit Server version, Flow does not add another pending copy.

---

## Adding a Folder to the Archive Queue

1. Select the project or folder in **Browse**.
2. Right-click and select **Add Folder to Archive Queue**.
3. Choose the parent folder for the archive.
4. Review the number of models and proposed project archive destination.
5. Select **Add to Queue**.

Flow includes models recursively and preserves the Revit Server subfolder structure beneath the selected folder.

The selected project archive destination must be empty. Flow blocks queue preparation if that destination already contains files.

!!! info "Existing pending models are skipped"

    When a folder is added, Flow skips models that are already pending in the standalone archive queue and reports how many items were added or skipped.

---

## Running the Archive Queue

1. Open **Archive Queue**.
2. Review each model, source, output location and status.
3. Set **Lock source models after successful standalone archives** as required.
4. Select **Run Queue**.
5. Review the confirmation and select **Run Queue** again.
6. Allow each Revit worker session to finish.
7. Review the completion summary and any errors shown in the queue.

Before starting, Flow checks every pending source. If any source is unavailable, the entire queue remains unchanged and does not start.

Each model is processed sequentially in a separate Revit session. A failed archive does not prevent the remaining jobs from running.

<!-- Screenshot recommended:
Show the Archive Queue containing several example models with different output paths.
Include the automatic source-locking checkbox and queue controls.
-->

---

## Automatic Source Locking

When **Lock source models after successful standalone archives** is selected, Flow locks each source model only after its archive job succeeds and the output file can be verified as present and non-empty.

Automatic locking applies only to standalone archive jobs. Archives created as prerequisites for the **Upgrade Workflow** are excluded.

The setting is remembered for the next Flow Server session.

!!! note "An archive can succeed even if locking fails"

    If the archive succeeds but the source cannot be locked, Flow retains the successful archive result and reports the locking failure separately.

---

## Removing or Clearing Queue Items

- Select a standalone archive job and choose **Remove Selected** to remove only that row.
- Choose **Clear Queue** to remove all standalone archive jobs.

Removing queue items does not affect the source models or delete completed archive files.

Archive jobs belonging to the Upgrade Workflow cannot be removed from this tab. Use **Clear Workflow** on the **Upgrade Workflow** tab instead.

---

## Stopping the Queue

Select **Stop Queue** to request cancellation.

The archive currently being processed is allowed to finish. Remaining jobs are then cancelled.

---

## Archive Queue Statuses

| Status | Meaning |
|---|---|
| **Pending** | The archive is ready to run. |
| **Running** | The model is currently being archived. |
| **Succeeded** | The archive completed successfully. |
| **Failed** | The archive did not complete. Review the Error column. |
| **Cancelled** | The job was cancelled before completion. |

---

## Related Help

- [Flow Server](index.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Managing Server Content](managing-server-content.md)
- [Upgrading Projects](upgrading-projects.md)
- [Troubleshooting](troubleshooting.md)
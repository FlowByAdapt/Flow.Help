# Upgrading Projects

The **Upgrade Workflow** manages the complete process of archiving a source Revit Server model, upgrading the local archive and publishing the result as a new central model on the target Revit Server version.

The current workflow upgrades supported source models to Revit 2027.

---

## Before You Start

Confirm that:

- Flow Server is connected to the correct source Revit Server version
- Revit 2027 and the Flow upgrade worker are installed
- the target version is later than the source version
- the source models are available for processing
- the intended target project folder does not already exist

!!! warning "The target project folder must be available"

    Flow does not add to, replace or modify an existing target project folder.

    This protects completed projects and prevents an upgrade from being published into an ambiguous destination.

---

## Adding One Model

1. Select the source model in **Browse**.
2. Confirm the required **Target version** on the **Upgrade Workflow** tab.
3. Right-click the model and select **Add to Upgrade Workflow**.
4. Review the source and proposed target RSN paths.
5. Select **Add to Workflow**.

Flow creates a linked archive job and an upgrade job. The upgrade row initially shows **Ready to Archive**.

The confirmation identifies that Flow will:

- archive the source model
- upgrade the local archive
- create the target Revit Server folder when required
- publish the upgraded model as a new central model

---

## Adding a Folder

1. Select the project folder in **Browse**.
2. Right-click and select **Add Folder to Upgrade Workflow**.
3. Review the number of contained models, source folder and target version.
4. Select **Add to Workflow**.

Flow includes models recursively, preserves the Revit Server subfolder structure and prepares source-to-target mappings for the models in the selected folder.

Models already pending in the upgrade workflow are skipped and included in the reported skipped count.

!!! tip "Queue the complete project folder for linked projects"

    When a project contains Revit links, add the project folder so Flow can prepare the models together and preserve their server folder relationships.

---

## Running the Upgrade Workflow

1. Open **Upgrade Workflow**.
2. Review the model, source, output, source version, target version and current status for each item.
3. Select **Run Workflow**.
4. Allow Flow to complete the archive, upgrade and publish stages.
5. Review the final status and any error reported for each model.

For queued Browse items, Flow first runs the required source archives. Successful archives then move to **Ready to Upgrade** before the upgrade worker begins.

Upgrade jobs can take substantially longer than ordinary server administration actions. Flow allows up to two hours for each upgrade job.

<!-- Screenshot recommended:
Show the Upgrade Workflow with several example models.
Include Ready to Archive, Ready to Upgrade and Completed states if they can be reproduced safely.
-->

---

## Destination Preflight

Before processing starts, Flow checks each unique target project folder.

The workflow is blocked when Flow finds:

- an incomplete Flow upgrade destination
- a previously completed Flow upgrade destination
- an existing target project folder without a matching Flow recovery record
- a destination that cannot be verified

Flow reports the affected target and does not start the upgrade.

---

## Upgrade Statuses

| Status | Meaning |
|---|---|
| **Ready to Archive** | The source archive prerequisite is queued. |
| **Archiving** | Flow is creating the local source archive. |
| **Ready to Upgrade** | The required archive succeeded and the upgrade can run. |
| **Upgrading** | Revit is upgrading and publishing the model. |
| **Completed** | The upgraded model was published successfully. |
| **Failed** | An archive, upgrade or publish stage failed. |
| **Cancelled** | The item was cancelled before completion. |

If a required archive fails, the linked upgrade item is marked **Failed** and is not upgraded.

---

## Clearing the Workflow

Select **Clear Workflow** when the workflow is not running to remove all upgrade items and their linked archive queue items.

Clearing the workflow does not delete source models or completed target models.

---

## Stopping the Workflow

Select **Stop Workflow** to request cancellation of the current archive, upgrade or publish stage.

When cancellation completes, Flow removes the cancelled workflow items and their linked archive jobs from the active queues.

---

## Related Help

- [Flow Server](index.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Archiving Projects](archiving-projects.md)
- [Troubleshooting](troubleshooting.md)
# Revit Upgrade

**Revit Upgrade** provides tools for upgrading Revit content for use in **Revit 2027**.

Use **Quick Upgrade** to process selected files from a single folder, or **Batch Upgrade** to process supported content throughout a complete folder structure.

Upgraded content is written to a separate **NewFiles** folder so that the original source files are retained.

!!! note "Revit 2027 only"

	Revit Upgrade is available only when running Flow in **Revit 2027**.

---

## Open Revit Upgrade

On the Revit ribbon:

**ADAPT → Content → Upgrade**

When Revit Upgrade opens, choose the required mode:

* **Quick Upgrade (selected files)** — process specific files from a single folder.
* **Batch Upgrade (folder + subfolders)** — process supported content throughout a selected folder structure.

---

## What Do You Want to Do?

### Upgrade Selected Files

Use **Quick Upgrade** when you only need to process specific files from one folder.

Select the required files and Flow creates upgraded copies beneath a **NewFiles** folder inside that source folder.

➡️ [**Upgrading Revit Content**](upgrading-revit-content.md)

### Upgrade a Folder Structure

Use **Batch Upgrade** to process supported content from a selected folder and its subfolders.

The existing folder structure is recreated beneath **NewFiles**, allowing a content library or group of folders to be upgraded together.

Associated PNG and TXT supporting files are copied with the upgraded content so that the corresponding library structure can be retained.

➡️ [**Upgrading Revit Content**](upgrading-revit-content.md)

### Review or Retry a Previous Batch

Batch Upgrade can also:

* View the summary recorded for the last new batch.
* Retry files that failed or could not be confidently confirmed as successful.

➡️ [**Upgrading Revit Content**](upgrading-revit-content.md)

### Having Problems?

Find help if content cannot be processed, Batch Upgrade reports failures, or a previous batch cannot be reviewed or retried.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Getting Help

Hover over **Upgrade** on the ADAPT ribbon and press **F1** to return directly to this page.

# Extracting Drafting Views

Use **Drafting View Extractor** to process drafting views contained within one or more Revit library files.

Flow reviews the selected files, identifies their drafting views and shows what will be created, updated or skipped before extraction begins.

---

## Open Drafting View Extractor

On the Revit ribbon:

**Flow → Content → Drafting**

---

## Select the Source Files

Start by selecting the Revit files containing the drafting views you want to extract.

1. Open **Drafting View Extractor**.
2. Select one or more source `.rvt` files.
3. Click **Open**.
4. Allow Flow to review the selected files.

Multiple source files can be processed in the same extraction run.

!!! info "Drafting views are found automatically"

	Flow finds the drafting views within each selected source file.

	Drafting view templates are ignored and do not form part of the extraction.

---

## Review the Drafting Views

Before making any changes, Flow shows a preview of the drafting views found across the selected files.

Each drafting view is given one of the following statuses:

| Status                | What will happen                                                                   |
| --------------------- | ---------------------------------------------------------------------------------- |
| **[MISSING]**         | The extracted drafting-view file does not exist and will be created.               |
| **[EXISTS - OLD]**    | An existing extracted file is more than seven days old and will be updated.        |
| **[EXISTS - RECENT]** | An existing extracted file is seven days old or less and will normally be skipped. |

!!! tip "Use the normal extraction for routine updates"

	**Extract Missing / Old Only** creates missing content and updates older
	content while leaving recently extracted files unchanged.

	This is the recommended option for normal library maintenance.

---

## Choose the Extraction Mode

After reviewing the preview, choose how Flow should proceed.

### Extract Missing / Old Only

Select **Extract Missing / Old Only** for the normal extraction workflow.

Flow will:

* Create missing drafting-view files.
* Update existing drafting-view files that are more than seven days old.
* Skip recently created or updated drafting-view files.

### Force Extract All

Select **Force Extract All** when every drafting view from the selected source files needs to be regenerated.

!!! note "Force Extract All ignores the recent-file check"

	Existing extracted files are regenerated even when they were created or
	updated within the last seven days.

	Use this when you specifically need to refresh all of the selected content.

### Cancel

Select **Cancel** to leave the extraction without processing the drafting views.

---

## Extraction

Once extraction begins, Flow processes the drafting views automatically.

For each drafting view, Flow:

1. Creates an individual Revit file using the configured drafting-view template.
2. Copies the drafting-view content into the new file.
3. Retains the drafting view's name, scale and detail level.
4. Removes unused content from the extracted file.
5. Saves the resulting RVT into the Flow content library.

The progress window shows the source file and drafting view currently being processed.

!!! info "Each drafting view becomes reusable content"

	Each extracted drafting view is saved as its own Revit file rather than
	remaining dependent on the original source file.

---

## Preview Images

After the drafting-view files have been processed, Flow automatically starts the second stage of the workflow:

**Generating preview images...**

Preview images are generated for the successfully extracted drafting-view files.

!!! info "Preview generation is automatic"

	You do not need to run Preview Generator separately after a normal
	Drafting View Extractor run.

	Flow passes the successfully extracted files directly into the preview
	generation workflow.

---

## Review the Results

When processing is complete, Flow displays an extraction summary including:

* **Files processed**
* **Views found**
* **Created / Updated**
* **Skipped**
* **Failed**
* **Purged elements**
* Preview images **Generated**
* Preview images **Skipped**
* Preview images **Failed**

If individual drafting views could not be extracted, the first errors are also shown in the completion summary.

---

## What Next?

After reviewing the results, choose one of the available actions.

### Extract Another File

Select **Extract Another File** to choose another source file or group of files and start another extraction.

### Open Output Folder

Select **Open Output Folder** to open the extracted-content location in File Explorer.

### Close

Select **Close** when the extraction workflow is complete.

---

## Related Help

* [Drafting View Extractor](index.md)
* [Managing Extracted Views](managing-extracted-views.md)
* [Troubleshooting](troubleshooting.md)

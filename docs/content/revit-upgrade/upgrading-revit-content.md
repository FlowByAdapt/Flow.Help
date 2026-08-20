# Upgrading Revit Content

Use **Revit Upgrade** to create Revit 2027 copies of existing Revit content.

Choose **Quick Upgrade** for selected files from a single folder, or **Batch Upgrade** to process a complete folder structure.

!!! note "Revit 2027 only"

    This workflow is available only when running Flow in **Revit 2027**.

---

## Open Revit Upgrade

On the Revit ribbon:

**Flow → Content → Upgrade**

Choose:

* **Quick Upgrade (selected files)**
* **Batch Upgrade (folder + subfolders)**

---

## Quick Upgrade

Use **Quick Upgrade** when you want to upgrade specific files rather than an entire folder structure.

### Select the Files

1. Open **Revit Upgrade**.
2. Select **Quick Upgrade (selected files)**.
3. Select the files you want to process.
4. Confirm the selection.

Multiple files can be selected together.

All selected files must be located in the **same source folder**.

!!! warning "Files must be in the same folder"

    Quick Upgrade cannot process a selection containing files from different folders.

    If content needs to be processed across multiple folders, use **Batch Upgrade** instead.

### Start the Upgrade

Once the selection is accepted, Flow:

1. Creates a **NewFiles** folder inside the source folder.
2. Creates the upgrade job.
3. Launches the batch processor.
4. Processes the selected content using Revit 2027.
5. Writes the resulting files to **NewFiles**.

The original source files are not used as the output location.

---

## Batch Upgrade

Use **Batch Upgrade** when you want to process a folder and its subfolders together.

### Start a New Batch

1. Open **Revit Upgrade**.
2. Select **Batch Upgrade (folder + subfolders)**.
3. Select **Start New Batch**.
4. Select the root folder containing the content to upgrade.
5. Confirm the folder.

Flow searches the selected folder and its subfolders for supported content.

Existing **NewFiles** folders and numbered Revit backup files are excluded from the search.

If no supported files are found, the batch is not started.

### Output Folder

Flow creates:

**[Selected Folder] → NewFiles**

The source folder structure is reproduced beneath **NewFiles**.

For example:

```
Content Library
├── Doors
│   └── Door-A.rfa
└── Windows
    └── Window-A.rfa
```

is processed into:

```
Content Library
└── NewFiles
    ├── Doors
    │   └── Door-A.rfa
    └── Windows
        └── Window-A.rfa
```

This allows an existing content-library structure to be retained in the upgraded output.

---

## How Revit Files Are Processed

Revit content is opened using Revit 2027 and saved to the corresponding location beneath **NewFiles**.

Where applicable, Flow also attempts to purge unused content before saving the upgraded file.

If a Revit document cannot be opened normally, Flow makes a further attempt to open it using Revit's audit option.

A problem processing one file does not prevent the remaining files in the batch from being attempted.

!!! info "Existing output files"

    If a file already exists at the corresponding location beneath **NewFiles**, Flow replaces the existing output file.

    The original file in the source library is not replaced.

---

## Revit Templates

Revit project templates require additional processing during upgrade.

Flow opens the template as a new project document and creates the upgraded output.

Where the upgraded template can be successfully saved back to **RTE**, the intermediate RVT file created during processing is removed.

If the RTE save cannot be completed, the available RVT output may be retained.

---

## Revit Backup Files

Numbered Revit backup files are excluded when Batch Upgrade searches the source folders.

Flow also removes numbered Revit backup files created within the **NewFiles** output during processing.

This keeps the upgraded output library free from unnecessary Revit backup files.

---

## When the Upgrade Starts

After the job has been created, Flow displays information including:

* Number of files found.
* Run folder.
* Job file location.
* Expected result file location.
* Output folder.

The actual processing is performed by Flow's batch processor.

You can continue to review the result of the batch through the **Batch Upgrade** actions after processing has completed.

---

## View the Last Batch Summary

To review the most recent Batch Upgrade:

1. Open **Revit Upgrade**.
2. Select **Batch Upgrade (folder + subfolders)**.
3. Select **View Last Batch Summary**.

The summary reports:

* Job identifier.
* Total files.
* Number succeeded.
* Number failed.

Where files have failed, the summary also provides the failed filename, source path and available error information.

---

## Retry Failed Files

You do not need to run the entire folder again if individual files failed during the last batch.

1. Open **Revit Upgrade**.
2. Select **Batch Upgrade (folder + subfolders)**.
3. Select **Retry Failed Files from Last Batch**.

Flow identifies the failed files from the previous batch and creates a new job containing those files.

The retry uses the same source and output locations as the original batch.

!!! tip "Review the summary first"

    Use **View Last Batch Summary** to identify the files that failed and review the available error information before retrying them.

---

## Review the Upgraded Content

When processing has finished, review the content beneath **NewFiles** before replacing or updating your existing library.

Check that:

* The required files were created.
* The expected folder structure has been retained.
* Revit content opens correctly in Revit 2027.
* Any reported failures have been reviewed or retried.

!!! warning "Check upgraded content before replacing library files"

    Revit Upgrade deliberately keeps the upgraded output separate from the source library.

    Review the upgraded content before using it to replace existing library files.

---

## Related Help

* [Revit Upgrade](index.md)
* [Troubleshooting](troubleshooting.md)
* [Content Browser](../content-browser/index.md)
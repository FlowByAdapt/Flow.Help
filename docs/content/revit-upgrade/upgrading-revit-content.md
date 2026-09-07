# Upgrading Revit Content

Revit Upgrade provides two workflows for creating Revit 2027 versions of existing content:

* **Quick Upgrade** — process selected files from one folder.
* **Batch Upgrade** — process supported content throughout a folder and its subfolders.

Both workflows create upgraded output beneath a separate **NewFiles** folder. The original source files are not replaced.

!!! note "Revit 2027 only"

    Revit Upgrade is available only when running Flow in **Revit 2027**.

---

## Open Revit Upgrade

On the Revit ribbon:

**ADAPT → Content → Upgrade**

Choose:

* **Quick Upgrade (selected files)**
* **Batch Upgrade (folder + subfolders)**

---

## Files Processed by Revit Upgrade

The current Revit Upgrade workflow is intended primarily for:

* **RVT** — Revit project files.
* **RFA** — Revit family files.
* **RTE** — Revit project templates.
* **PNG** — supporting image files.
* **TXT** — supporting text files, including files such as type catalogues.

PNG and TXT files are not opened or modified by Revit. They are copied into the corresponding **NewFiles** location.

!!! note "Family templates"

    RFT files can currently appear in the Revit Upgrade file-selection and discovery workflow. Their final upgrade/output behaviour should be treated as unverified until the RFT workflow has been confirmed separately.

---

## Quick Upgrade

Use **Quick Upgrade** when you only need to process specific files from one folder.

### 1. Start Quick Upgrade

Open:

**ADAPT → Content → Upgrade**

Select:

**Quick Upgrade (selected files)**

### 2. Select the Files

Select the files you want to process.

All selected files must be located in the **same folder**.

If files from different folders are selected, Flow reports:

**All selected files must be in the same folder.**

Use Batch Upgrade instead when files need to be processed from several folders.

### 3. Start the Upgrade

After the selection is confirmed, Flow creates:

**[Source Folder] → NewFiles**

A batch job is created and passed to Flow's Revit Upgrade batch processor.

The original files remain in their existing location.

---

## Batch Upgrade

Use **Batch Upgrade** when you want to process an entire content-library structure.

### 1. Open Batch Upgrade

Open:

**ADAPT → Content → Upgrade**

Select:

**Batch Upgrade (folder + subfolders)**

### 2. Start a New Batch

Select:

**Start New Batch**

Then select the root folder containing the content to process.

Flow searches the selected folder and its subfolders for supported content.

Existing **NewFiles** folders and numbered Revit backup files are excluded from the search.

If no supported content is found, Flow reports:

**No supported files found.**

---

## Output Folder

Flow creates:

**[Selected Folder] → NewFiles**

For Batch Upgrade, the source folder structure is reproduced beneath **NewFiles**.

For example:

```text
Content Library
├── Doors
│   ├── Door-A.rfa
│   └── Door-A.png
└── Windows
    ├── Window-A.rfa
    └── Window-A.txt
```

is processed into:

```text
Content Library
└── NewFiles
    ├── Doors
    │   ├── Door-A.rfa
    │   └── Door-A.png
    └── Windows
        ├── Window-A.rfa
        └── Window-A.txt
```

This allows an existing library structure and its associated supporting files to be retained in the upgraded output.

---

## How Revit Files Are Processed

Revit content is opened using Revit 2027 and saved to the corresponding location beneath **NewFiles**.

For standard Revit files Flow:

1. Attempts to open the source file normally.
2. If the normal open fails, attempts to open the file again using Revit's **Audit** option.
3. Attempts to purge unused content.
4. Saves the upgraded document beneath **NewFiles**.
5. Closes the upgraded document before continuing.

A problem processing one file does not normally prevent the remaining files from being attempted.

### Purge Unused

Flow performs a Revit **Purge Unused** operation before saving applicable content.

The purge operation is repeated until Revit reports no further unused elements.

If purge cannot be completed, Flow attempts to continue with the upgrade where possible.

A purge warning therefore does not automatically mean that the file upgrade failed.

### Existing Output Files

If a corresponding file already exists beneath **NewFiles**, Flow replaces that output with the newly processed version.

The original source file is not replaced.

!!! warning "NewFiles may contain previous output"

    Running Revit Upgrade again can replace output from an earlier run.

    Move or copy any upgraded content that must be retained before repeating the upgrade.

---

## Supporting PNG and TXT Files

PNG and TXT files are treated as supporting content.

They are:

* Not opened in Revit.
* Not modified by the upgrade process.
* Copied to the corresponding location beneath **NewFiles**.
* Replaced if a corresponding output file already exists.

This is useful for content libraries that keep preview images, type catalogues or other supporting text files beside their Revit content.

---

## Revit Project Templates

RTE project templates require additional processing.

Flow:

1. Opens the source template as a new Revit project.
2. Attempts to purge unused content.
3. Saves an upgraded RVT representation.
4. Attempts to save the upgraded document back as an RTE template.

If the RTE save succeeds, the intermediate RVT file is removed.

If the RTE save cannot be completed, the RVT may remain as the available upgraded output.

Review upgraded templates in Revit 2027 before replacing production-library content.

---

## Revit Backup Files

Numbered Revit backup files are excluded when Batch Upgrade searches the source folder.

For example:

```text
Family.0001.rfa
Project.0002.rvt
```

are treated as backup files rather than source content.

Flow also removes numbered Revit backup files created beneath **NewFiles** during processing.

This keeps the upgraded output free from unnecessary Revit backup files.

---

## When the Upgrade Starts

After a new job has been created, Flow displays information including:

* Number of files found.
* Run folder.
* Job file location.
* Expected result file location.
* Output folder.

Processing is then performed by Flow's external batch processor.

!!! note "Cancelling an upgrade"

    You can cancel the file, folder or mode selection before the batch starts.

    Once the external batch job has been launched, the current Revit Upgrade workflow does not provide a Flow Cancel button.

---

## Batch Results

A batch can contain three general result states.

### Succeeded

The file was processed successfully and an output result was recorded.

### Failed

Flow received a definite processing failure for the file.

Where available, error information is recorded with the result.

### Suspected Failed

Flow may sometimes be unable to confirm the result of a group of files processed through Revit.

For example, this can occur if the Revit worker process does not return a usable result.

Those files are treated as **suspected failures** so that they can be retried rather than being assumed successful.

A suspected failure does not necessarily mean that every affected source file is damaged.

---

## View the Last Batch Summary

To review the result recorded for the last new Batch Upgrade:

1. Open **Revit Upgrade**.
2. Select **Batch Upgrade (folder + subfolders)**.
3. Select **View Last Batch Summary**.

The current summary reports:

* Job identifier.
* Total files.
* Number succeeded.
* Number failed.

Where normal failures are present, it also displays the failed filename, source path and available error information.

!!! warning "Suspected failures"

    The current summary does not separately display files marked as suspected failed.

    These files can still be included by **Retry Failed Files from Last Batch**.

---

## Retry Failed Files

You do not need to process the entire source folder again if individual files were unsuccessful.

To retry:

1. Open **Revit Upgrade**.
2. Select **Batch Upgrade (folder + subfolders)**.
3. Select **Retry Failed Files from Last Batch**.

Flow creates a new job containing files from the recorded batch that were:

* **Failed**, or
* **Suspected failed**.

The retry uses the same source and output locations as the original batch.

!!! tip "Review the output as well as the summary"

    Because suspected failures are not currently listed separately in the Last Batch Summary, the number of files included in a retry can be greater than the failures shown in that summary.

!!! note "Last Batch Summary after a retry"

    Starting a retry does not currently replace the recorded original batch used by **View Last Batch Summary**.

    The Last Batch Summary therefore continues to refer to the previously recorded new batch rather than automatically switching to the retry result.

---

## Review the Upgraded Content

After processing:

1. Open the **NewFiles** folder.
2. Confirm that the expected folder structure has been created.
3. Check that the required Revit files and associated supporting files are present.
4. Review important upgraded files in Revit 2027.
5. Pay particular attention to templates and any files that previously reported warnings or failures.

Revit Upgrade is intended to create a separate upgraded content set rather than automatically replace the production source library.

---

## Related Help

* [Revit Upgrade](index.md)
* [Troubleshooting](troubleshooting.md)
* [**Content Browser**](../index.md)

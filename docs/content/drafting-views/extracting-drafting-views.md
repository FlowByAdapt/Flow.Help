# Extracting Drafting Views

Use **Drafting View Extractor** to create or update individually managed library files from drafting views in one or more source RVT containers.

---

## Open Drafting View Extractor

On the Revit ribbon:

**Flow → Content → Drafting**

---

## Select the Source Files

1. Open **Drafting View Extractor**.
2. Select one or more source `.rvt` files.
3. Click **Open**.
4. Allow Flow to scan the selected files.

The picker also offers **All files**, but the extraction workflow is intended for Revit project files inside the current version-specific Flow library.

Flow opens each selected source during scanning and collects its non-template drafting views automatically. Other view types and drafting-view templates are ignored.

<!-- SCREENSHOT: Source selection.
Show multiple RVT container files selected in the file picker. -->

---

## Review the Drafting Views

Flow reports the total number of drafting views found and lists up to the first 50 in the confirmation dialogue.

| Status | What will happen in normal mode |
| --- | --- |
| **[MISSING]** | No extracted RVT exists, so it will be created |
| **[EXISTS - OLD]** | The existing RVT is more than seven days old and will be replaced |
| **[EXISTS - RECENT]** | The existing RVT is seven days old or less and will be skipped |

The preview includes non-template drafting views even when they are empty. An empty view can appear in the list but fail later because it contains no drawable elements.

<!-- SCREENSHOT: Extraction confirmation.
Show Missing, Old and Recent entries together with all three action buttons. -->

---

## Choose the Extraction Mode

### Extract Missing / Old Only

Use this for routine library maintenance. Flow creates missing output, replaces output older than seven days and skips recent RVTs.

### Force Extract All

Use this when every output RVT should be regenerated regardless of age.

!!! note "Existing previews are not forced"

    **Force Extract All** forces RVT replacement, but the automatic preview stage still skips an existing PNG. Remove or separately regenerate a stale preview when required.

### Cancel

Select **Cancel** to close the confirmation without extracting content.

---

## Extraction Stage

Flow reopens each source file and processes its drafting views alphabetically.

For each view, Flow attempts to:

1. determine its mirrored `_draftingviews` output path;
2. create a new project from the configured drafting-view template;
3. create a drafting view using the source name, scale and detail level;
4. copy the source view's drawable elements;
5. retain destination types when duplicate type names are encountered;
6. repeatedly purge unused elements;
7. replace any existing output selected for update; and
8. save the individual RVT.

The progress window shows both the current source file and drafting view.

!!! warning "Verify generated RVTs"

    The current implementation's final drafting-view cleanup is under review. Open and check generated RVTs before treating them as published library content.

---

## Preview-Generation Stage

After extraction, Flow passes successful output paths into preview generation.

For each supported output file:

- a missing PNG is generated alongside the RVT;
- an existing PNG is reported as skipped; and
- a preview error is recorded separately from the RVT extraction result.

The drafting-view preview is exported at 2200 pixels from the alphabetically first non-template drafting view found in the output RVT.

---

## Cancelling Progress

You can cancel from the progress window. Files already created remain in place.

Cancellation is normally checked between source files, drafting views and preview files. The current implementation may still continue into preview generation when cancellation occurs during the final or only source file, so review the displayed progress and results before closing.

---

## Review the Results

The completion dialogue displays:

- **Files processed**
- **Views found**
- **Created / Updated**
- **Skipped**
- **Failed**
- **Purged elements**
- preview **Generated**
- preview **Skipped**
- preview **Failed**

Up to the first five per-view extraction errors are included.

!!! note "Review totals with care"

    The current Created/Updated total can omit successful outputs that purged zero elements. A source-level failure may also be shown earlier without appearing in the final Failed count.

---

## What Next?

- **Extract Another File** — reopen the source picker and begin another run.
- **Open Output Folder** — open the first available extracted-content folder.
- **Close** — finish the workflow.

**Open Output Folder** requires at least one result containing a valid output path.

---

## Getting Help

Hover over **Drafting** on the Flow ribbon and press **F1** to open Drafting View Extractor help.

---

## Related Help

- [**Drafting View Extractor**](index.md)
- [**Managing Extracted Views**](managing-extracted-views.md)
- [**Troubleshooting**](troubleshooting.md)

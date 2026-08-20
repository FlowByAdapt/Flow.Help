# Preview Generator Troubleshooting

Use the following checks if Preview Generator cannot process content or an expected preview image is not created.

---

## No Content Is Processed

Confirm that the selected folder contains supported Revit content.

Preview Generator processes:

* Revit family files (`.rfa`).
* Extracted drafting-view container files (`.rvt`).

The selected folder and its subfolders are searched automatically.

Other file types are ignored.

---

## A Preview Is Skipped

Preview Generator checks for an existing PNG before processing each Revit file.

If a corresponding preview already exists, that file is skipped.

For example:

```text
ADa_Door.rfa
ADa_Door.png
```

Because `ADa_Door.png` already exists, `ADa_Door.rfa` does not need to be processed.

!!! info "Skipped does not mean failed"

	Skipped content is reported separately from failed content in the completion summary.

	A skipped item normally means that a valid preview filename already exists beside the source file.

---

## I Need to Regenerate an Existing Preview

Normal batch processing preserves existing preview images.

To regenerate a preview:

1. Locate the PNG beside the source Revit file.
2. Remove the existing PNG.
3. Run **Preview Generator** again.
4. Select the content folder containing the source file.

Preview Generator will detect that the preview is missing and generate a replacement.

!!! warning "Check the file before removing it"

	Make sure you are removing the preview PNG rather than the source `.rfa` or `.rvt` file.

---

## A Family Preview Fails

Preview Generator must be able to open the family in Revit before it can create the preview.

If a family fails:

1. Confirm that the `.rfa` file is accessible.
2. Confirm that the file can be opened in the current version of Revit.
3. Review the completion information displayed by Flow.
4. Try opening the family manually if further investigation is required.

Opening or upgrading some family files may take longer than others.

---

## A Drafting View Preview Fails

Preview Generator expects an `.rvt` content file to contain an extracted drafting view.

If no suitable drafting view is found, the preview cannot be generated.

Confirm that the RVT was created as a drafting-view content container and contains the expected drafting view.

For help creating drafting-view content, see:

➡️ [**Drafting View Extractor**](../index.md)

---

## Some Content Succeeds and Other Content Fails

Preview Generator handles each supported file separately.

If an individual item fails, Flow records the failure and continues with the remaining content.

When processing finishes, review the completion summary for the number of:

* Succeeded items.
* Skipped items.
* Failed items.

This makes it possible to process a large content folder even if an individual source file requires attention.

---

## Preview Generator Appears to Pause

Revit may take some time to open or upgrade individual family or drafting-view files.

During this part of the process, Preview Generator may appear to pause while Revit completes the operation.

Allow the current file time to open before assuming that processing has stopped.

---

## Cancel Preview Generation

Use the cancel control in the Preview Generator progress window if you need to stop the batch.

Preview Generator stops before processing the next content item and reports the batch as cancelled.

Content that was successfully processed before cancellation remains available.

---

## Reporting a Problem

If the problem continues, record:

* The Revit version.
* The source `.rfa` or `.rvt` file.
* The selected content folder.
* What you expected to happen.
* What happened instead.
* Any error message displayed by Flow.
* The completion summary.
* A screenshot where useful.

---

## Related Help

* [Preview Generator](index.md)
* [Generating Preview Images](generating-previews.md)
* [**Content Browser**](../index.md)
* [**Drafting View Extractor**](../index.md)
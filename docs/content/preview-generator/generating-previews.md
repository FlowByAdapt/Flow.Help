# Generating Preview Images

Use **Preview Generator** to create consistent preview images for supported Revit content.

Preview Generator processes a selected content folder, creates missing preview images and stores each generated PNG alongside its source file.

---

## Open Preview Generator

On the Revit ribbon:

**Flow → Content → Preview Generator**

A folder selection window opens.

---

## Select a Content Folder

Select the folder containing the Revit content you want to process.

Preview Generator searches:

* The selected folder.
* All subfolders within the selected folder.

Supported content includes:

* Revit family files (`.rfa`).
* Extracted drafting-view container files (`.rvt`).

Select the folder and confirm the selection to begin processing.

!!! tip "Process a complete content library"

	You can select a folder containing multiple content folders.

	Preview Generator searches through the complete folder structure and automatically finds supported content.

---

## Existing Preview Images

Before processing each file, Preview Generator checks whether a corresponding PNG preview already exists.

If a preview already exists, the file is **skipped**.

This allows you to run Preview Generator against an existing content library to create missing previews without regenerating previews that are already present.

!!! info "Existing previews are preserved"

	Preview Generator does not replace existing preview images during normal batch processing.

	To regenerate a preview, remove the existing PNG before running Preview Generator again.

---

## Generate the Previews

Preview generation starts automatically after the content folder is selected.

A progress window shows:

* The content currently being processed.
* Overall batch progress.
* Progress for the current item.

Preview Generator processes each supported file in turn.

You can cancel the batch from the progress window if required.

---

## Family Previews

For Revit family files (`.rfa`), Preview Generator opens the family and automatically prepares a standardised 3D preview.

Flow manages the preview configuration, visibility and framing automatically before exporting the image.

No preview settings need to be configured manually.

!!! info "The source family is not saved"

	Preview Generator may temporarily configure the family document to create a consistent preview.

	The family is closed without saving these changes after the preview has been generated.

---

## Drafting View Previews

Extracted drafting-view container files (`.rvt`) are processed differently from families.

Preview Generator locates the drafting view within the container and exports it as the preview image.

If the RVT file does not contain a suitable drafting view, that file cannot produce a drafting-view preview and is reported as failed.

---

## Generated Images

Each generated preview is saved as a PNG in the same folder as its source Revit file.

The preview uses the same base filename as the source content.

For example:

```text
ADa_Window.rfa
ADa_Window.png
```

and:

```text
4202_WBD__Beam Penetration.rvt
4202_WBD__Beam Penetration.png
```

This naming allows other Flow tools, including **Content Browser**, to associate the preview automatically with its Revit content.

---

## Processing Results

Preview Generator continues processing the remaining content if an individual file cannot generate a preview.

When processing finishes, Flow displays a summary showing:

* **Processed**
* **Succeeded**
* **Skipped**
* **Failed**
* **Cancelled**

A failed item therefore does not normally prevent other content in the selected folder from being processed.

!!! tip "Skipped files are usually expected"

	A skipped file normally means that its preview PNG already exists.

	If you expected the preview to be regenerated, remove the existing PNG and run Preview Generator again.

---

## Related Help

* [Preview Generator](index.md)
* [Troubleshooting](troubleshooting.md)
* [Content Browser](../content-browser/index.md)
* [**Drafting View Extractor**](../index.md)
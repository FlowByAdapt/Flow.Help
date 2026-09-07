# Generating Preview Images

Use **Preview Generator** to create consistent preview images for supported Revit content.

Preview Generator searches a selected folder, creates missing previews and saves each generated PNG beside its source Revit file.

---

## Open Preview Generator

On the Revit ribbon:

**Flow → Content → Preview Generator**

A folder selection window opens.

---

## Select a Content Folder

Select the folder containing the Revit content you want to process.

Preview Generator searches:

- The selected folder.
- Every subfolder beneath the selected folder.

Supported files are:

- Revit family files (`.rfa`).
- Revit project files (`.rvt`) containing drafting views.

Other file types are ignored.

Select the required folder and confirm the selection to begin processing.

!!! tip "Process a complete content library"

    You can select a folder containing multiple content categories.

    Preview Generator searches the complete folder structure and automatically
    finds supported Revit files.

---

## Existing Preview Images

Before processing each supported file, Preview Generator checks whether a corresponding PNG already exists.

The expected PNG must:

- Be located beside the source Revit file.
- Use the same base filename as the source file.

For example:

```text
ADa_Window.rfa
ADa_Window.png
```

If the corresponding PNG exists, the Revit file is **skipped** without being opened.

Flow checks only whether the expected PNG filename exists. It does not check the age or contents of the existing image.

!!! info "Existing previews are preserved"

    Preview Generator does not replace existing preview images during normal
    folder processing.

    To regenerate a preview, move, rename or remove the existing PNG before
    running Preview Generator again.

---

## Generate the Previews

Preview generation starts automatically after the content folder is selected.

A progress window shows:

- The file currently being processed.
- Overall batch progress.
- Progress for the current file.
- A control for cancelling the batch.

Preview Generator processes each supported file in turn.

---

## Family Previews

For a Revit family file (`.rfa`), Flow:

1. Opens the family document.
2. Reads the applicable preview profile.
3. Creates or prepares the preview view.
4. Configures preview visibility.
5. Frames the family content.
6. Exports the preview as a PNG.
7. Closes the family without saving it.

No preview settings need to be configured manually.

!!! info "The source family is not saved"

    Flow may temporarily change the family document to prepare a consistent
    preview.

    The family is closed without saving those changes after the image has
    been generated.

If a file with an `.rfa` extension is not a valid Revit family document, the preview is reported as failed.

---

## Drafting View Previews

Revit project files (`.rvt`) are processed as drafting-view content containers.

Flow opens the file and finds its first non-template drafting view in alphabetical order. That view is then exported as the preview image.

If the RVT does not contain a non-template drafting view, it cannot produce a drafting-view preview and is reported as failed.

!!! note "Use one drafting view per content container"

    Extracted drafting-view files are intended to contain one reusable
    drafting view.

    If an RVT contains several drafting views, Preview Generator uses the
    first non-template drafting view in alphabetical order.

Use [Drafting View Extractor](../index.md) to create suitable drafting-view content files.

---

## Generated Images

Each generated preview is saved as a PNG in the same folder as its source Revit file.

The PNG uses the same base filename as the source content.

For example:

```text
ADa_Window.rfa
ADa_Window.png
```

For drafting-view content:

```text
4202_WBD__Beam Penetration.rvt
4202_WBD__Beam Penetration.png
```

This naming convention allows other Flow tools, including **Content Browser**, to associate the preview with its Revit content automatically.

---

## Review the Results

When processing finishes, Flow displays:

- **Processed** — the total number of supported items found in the batch, including skipped items.
- **Succeeded** — previews generated successfully.
- **Skipped** — items for which the expected PNG already existed.
- **Failed** — items that could not generate a preview.
- **Cancelled** — whether the batch was cancelled.

If no supported content is found, the summary displays zero for each count.

Preview Generator records failures separately and continues processing the remaining content wherever possible.

!!! note "The summary displays counts"

    The completion message reports the number of failed items but does not
    list their filenames or individual error messages.

    If a file fails, try processing a smaller folder or opening the source
    file manually to identify the affected content.

---

## Cancel Preview Generation

Select the cancel control in the progress window if you need to stop the batch.

Cancellation is checked before the next file is processed. The current operation may therefore need to finish before the batch stops.

Previews generated before cancellation remain available.

The completion summary displays:

```text
Cancelled: True
```

---

## Expected Result

After a successful run:

- Each newly processed source file has a same-named PNG beside it.
- Existing preview PNGs remain unchanged.
- Source Revit files remain unsaved and unchanged by the preview workflow.
- Failed files do not normally prevent other files from being processed.

---

## Related Help

- [Preview Generator](index.md)
- [Troubleshooting](troubleshooting.md)
- [Content Browser](../content-browser/index.md)
- [Drafting View Extractor](../index.md)

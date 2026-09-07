# Preview Generator

The **Preview Generator** creates consistent preview images for Revit content used by Flow and the Revit content library.

Use it to scan a content folder and create missing preview images for supported Revit family and drafting-view content.

---

## Open Preview Generator

On the Revit ribbon:

**Flow → Content → Preview Generator**

A folder selection window opens.

---

## Supported Content

Preview Generator processes:

- Revit family files (`.rfa`).
- Revit project files (`.rvt`) containing drafting views.

The selected folder and all its subfolders are searched automatically.

!!! note "RVT files must contain a drafting view"

    Preview Generator attempts to process every `.rvt` file found in the
    selected folder structure.

    An RVT file must contain at least one non-template drafting view to
    produce a drafting-view preview.

---

## Existing Preview Images

Before opening each Revit file, Flow checks whether a corresponding PNG already exists beside it.

If the PNG exists, that item is skipped.

This allows Preview Generator to be run against an existing content library without regenerating every preview.

!!! info "Existing previews are preserved"

    Preview Generator does not replace existing PNG files during normal
    folder processing.

    To regenerate a preview, move, rename or remove the existing PNG before
    running Preview Generator again.

---

## What Do You Want to Do?

### Generate Preview Images

Select a content folder, process supported Revit content and create its missing preview images.

➡️ [**Generating Preview Images**](generating-previews.md)

### Having Problems?

Find help if content cannot be processed, a preview is skipped or an expected image is not created.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Related Help

- [Content Browser](../content-browser/index.md)
- [Drafting View Extractor](../index.md)

---

## Getting Help

Hover over **Preview Generator** on the Flow ribbon and press **F1** to return directly to this page.
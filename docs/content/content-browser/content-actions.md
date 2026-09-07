# Content Actions

Right-click an item in Content Browser to access file, preview, type-catalogue and publishing actions.

Some actions are disabled when their required companion file does not exist. Other actions remain visible for content they cannot process, so check the selected content type before running them.

<!-- SCREENSHOT: Content Browser context menu.
Show an RFA with both a preview image and matching type catalogue. -->

---

## Open Family

**Open Family** asks Revit to open and activate the selected source file.

If the source cannot be resolved or found, Content Browser reports **Source file not found.**

!!! note "Check the selected file type"

    This action is currently shown for non-family items as well as `.rfa` files. Use it only when opening the selected Revit source file is appropriate.

---

## Reload Family

**Reload Family** updates a loaded `.rfa` family from the current Flow library. The command is enabled when the selected item is shown as loaded and performs additional family validation when run.

See [**Reload One Family**](project-content.md#reload-one-family).

---

## Open Folder

**Open Folder** opens the folder containing the resolved source file in File Explorer.

---

## Preview Actions

- **Open Preview Image** — opens the existing PNG using its Windows-associated application.
- **Generate Preview** — requests preview generation for an `.rfa` family or `.rvt` drafting-view source.
- **Regenerate Preview** — recreates the preview and refreshes the selected item's preview path when successful.

!!! warning "Templates are not supported"

    Preview generation supports `.rfa` and `.rvt` files. It does not support `.rte` templates, even though the commands may currently remain enabled.

!!! info "Preview files are separate"

    A missing preview does not necessarily mean that the source Revit content is unavailable.

---

## Type Catalogue Actions

### Open Type Catalogue

Opens the matching `.txt` catalogue using the application associated with text files in Windows.

### Edit Type Catalogue

Opens the catalogue in Flow **Type Catalog Manager**.

### Conform Catalogue

Runs the catalogue-conformance process before opening Type Catalog Manager. If no changes are needed, Flow reports **No changes required** without opening the manager.

### Generate Type Catalogue

Opens Type Catalog Manager and starts generation from the selected family.

The open, edit and conform actions require a catalogue beside the selected family. **Generate Type Catalogue** is enabled when the Browser does not find that adjacent `.txt` file.

!!! note "Source and cached paths"

    Catalogue actions currently resolve source and cached paths differently. If an expected action is disabled or reports a missing catalogue, clear the cache and confirm that the `.rfa` and `.txt` files share the same base filename.

---

## Extract + Publish Drafting Views

Starts the Drafting View Extractor for the selected source file.

The workflow validates its library and template, asks for extraction/overwrite confirmation, extracts drafting views, generates previews and reports the result. It can then open the output folder or start another extraction.

The command is currently visible for all items. Use it only with an appropriate drafting-view source file.

---

## Copy Active Path

Copies the resolved source-file path to the Windows clipboard and reports **Source file path copied.**

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)

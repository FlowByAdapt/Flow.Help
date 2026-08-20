# Content Actions

Right-click an item in Content Browser to access actions that apply directly to that content.

The available actions depend on the selected content and its current state.

---

## Open Family

Use **Open Family** to open the selected Revit family file in Revit.

1. Right-click the family.
2. Select **Open Family**.

If the source file cannot be resolved or found, Content Browser reports that the source file is unavailable.

---

## Reload Family

Use **Reload Family** to update an already-loaded family from the current Flow library.

This action is available only when the selected item is a Revit family that is already loaded in the active project.

See [**Project Content**](project-content.md#reload-one-family).

---

## Open Folder

Use **Open Folder** to open the folder containing the selected source content in File Explorer.

1. Right-click the item.
2. Select **Open Folder**.

---

## Preview Actions

Depending on the selected item, the context menu provides:

- **Open Preview Image** — open the existing preview image.
- **Generate Preview** — create a preview where required.
- **Regenerate Preview** — recreate the preview for the selected content.

!!! info "Preview files are separate from the family"

    A missing preview does not necessarily mean that the Revit family itself is missing.

---

## Type Catalogue Actions

For family content, the context menu provides type-catalogue tools.

### Open Type Catalogue

Opens the `.txt` type catalogue associated with the family.

### Edit Type Catalogue

Opens the catalogue in the Flow **Type Catalog Manager**.

### Conform Catalogue

Opens and conforms the existing catalogue using the Flow type-catalogue workflow.

If no catalogue exists, Flow reports that no type catalogue was found.

### Generate Type Catalogue

Requests generation of a type catalogue from the selected family.

---

## Extract + Publish Drafting Views

Use **Extract + Publish Drafting Views** on an appropriate source item to start the drafting-view extraction workflow.

This is separate from loading an already-indexed drafting view into the active project.

---

## Copy Active Path

Use **Copy Active Path** to copy the resolved source-file path to the Windows clipboard.

This is useful when you need to inspect or reference the actual library file outside Content Browser.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Browser Tools**](content-browser-tools.md)
- [**Troubleshooting**](troubleshooting.md)
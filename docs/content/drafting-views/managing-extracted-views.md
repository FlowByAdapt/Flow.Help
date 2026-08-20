# Managing Extracted Drafting Views

Drafting View Extractor converts drafting views held within Revit library files into individually managed Revit files.

The extracted files are stored within the Flow content library so that reusable drafting content can be maintained separately from the source files in which it was created.

---

## How Extracted Views Are Stored

Flow stores extracted drafting views within a `_draftingviews` folder in the corresponding area of the Revit content library.

The source library structure is retained beneath this location so that extracted content remains associated with the area of the library from which it originated.

For example, a source file stored within a library structure such as:

```text
Library
└── Category
    └── Subcategory
        └── Container.rvt
```

will have its extracted drafting-view content organised beneath:

```text
Library
└── Category
    └── _draftingviews
        └── Subcategory
            └── Extracted drafting-view files
```

!!! info "The library structure is maintained automatically"

    You do not need to choose an output folder for each extraction.

    Flow determines the appropriate `_draftingviews` location from the
    location of the selected source file.

---

## Extracted File Names

Each drafting view is saved as an individual `.rvt` file.

The filename is built from:

**Source Container Name + Drafting View Name**

For example:

```text
ContainerName_Drafting View Name.rvt
```

Characters that cannot be used in Windows filenames are replaced automatically.

Associated preview images use the same base filename:

```text
ContainerName_Drafting View Name.rvt
ContainerName_Drafting View Name.png
```

This allows the extracted Revit content and its preview image to remain associated within the library.

---

## Keeping Extracted Views Current

Drafting View Extractor checks whether an extracted file already exists before recreating it.

Existing files are classified according to when they were last updated.

### Missing

If no extracted file exists, Flow creates it.

### Older Than Seven Days

If the existing extracted file is more than seven days old, the normal extraction workflow updates it.

### Seven Days Old or Less

If the existing file was created or updated within the last seven days, the normal extraction workflow skips it.

!!! tip "Use Extract Missing / Old Only for routine maintenance"

    The normal extraction mode avoids unnecessarily rebuilding content that
    has already been extracted recently.

---

## Regenerating Existing Content

If recently extracted content needs to be rebuilt, run the extractor again and select:

**Force Extract All**

This regenerates the extracted drafting-view files regardless of their age.

!!! note "Force extraction replaces existing output"

    **Force Extract All** bypasses the seven-day recent-file check.

    Use it when the source content has changed and the extracted version
    needs to be refreshed immediately.

---

## Source Files and the Content Library

Source RVT files must be located within the configured Revit content library.

Flow uses the source file's position within the library to determine where its extracted drafting views belong.

!!! note "Source files must be inside the library"

    If a source file is outside the configured library root, Flow cannot
    determine the corresponding `_draftingviews` location.

    Use library source files when creating centrally managed drafting content.

---

## Revit Versions

Flow automatically uses the content library associated with the current Revit version.

The drafting-view template used during extraction is also resolved for the current Revit version.

This keeps extracted drafting content associated with the appropriate Revit library.

---

## Preview Images

Preview images are generated automatically after successful drafting-view extraction.

The preview uses the same base filename as its corresponding extracted RVT and is stored alongside the reusable content.

There is normally no need to run Preview Generator separately after extracting drafting views.

---

## Related Help

* [Drafting View Extractor](index.md)
* [Extracting Drafting Views](extracting-drafting-views.md)
* [Troubleshooting](troubleshooting.md)
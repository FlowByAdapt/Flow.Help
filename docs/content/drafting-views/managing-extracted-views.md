# Managing Extracted Drafting Views

Drafting View Extractor stores individually managed RVTs within the version-specific Flow content library.

---

## Output Folder Structure

The source file must be inside the configured library. Flow inserts `_draftingviews` after the source path's first folder beneath the library root and retains the remaining source folders.

For example:

```text
Library
└── Category
    └── Subcategory
        └── Container.rvt
```

produces output beneath:

```text
Library
└── Category
    └── _draftingviews
        └── Subcategory
            └── Extracted drafting-view files
```

The required output folders are created automatically.

!!! note "Sources outside the library"

    Flow cannot calculate the mirrored output location when a source is outside the configured library root.

---

## Extracted File Names

Each output RVT uses:

```text
ContainerName_Drafting View Name.rvt
```

For example:

```text
Typical Details_Foundation Junction.rvt
Typical Details_Foundation Junction.png
```

Invalid Windows filename characters are changed to underscores, repeated underscores are collapsed and spaces are retained.

The matching PNG uses the same base filename and is stored beside the RVT.

---

## Missing, Old and Recent Output

Normal extraction uses the output RVT's last-write time:

- **Missing** — create the RVT.
- **More than seven days old** — replace the RVT.
- **Seven days old or less** — skip the RVT.

Use **Extract Missing / Old Only** for normal maintenance.

---

## Force an Immediate RVT Update

Choose **Force Extract All** to replace extracted RVTs regardless of age.

The existing RVT is deleted before the replacement is saved. If creation or saving fails after deletion, the previous output may no longer be available.

!!! warning "The preview may remain unchanged"

    Forced extraction does not currently overwrite an existing PNG. Delete or regenerate a stale preview separately when the source content has changed.

---

## Purged Content

Before saving, Flow repeatedly asks Revit for unused elements and deletes them until none remain. The completion summary reports the accumulated number of unused element IDs processed.

This produces a reduced reusable-content file rather than a full copy of the original container.

---

## Revit Versions and Template

Flow resolves the library for the running Revit version and uses:

```text
C:\ProgramData\Autodesk\RVT {version}\Templates\English\DefaultMetric.rte
```

The required library and template must both be accessible before extraction can begin.

---

## Verify Published Content

Until the current final-view cleanup behaviour has been corrected and tested, open generated RVTs and confirm that:

- the expected drafting view exists;
- its drawable content is present;
- its name, scale and detail level are correct; and
- the accompanying PNG represents that view.

<!-- SCREENSHOT: Output verification.
Show an extracted RVT open in Revit beside its matching PNG and source drafting view. -->

---

## Getting Help

Hover over **Drafting** on the Flow ribbon and press **F1** to open Drafting View Extractor help.

---

## Related Help

- [**Drafting View Extractor**](index.md)
- [**Extracting Drafting Views**](extracting-drafting-views.md)
- [**Troubleshooting**](troubleshooting.md)

# Content Browser Tools

Use the **Tools** menu for sheet, view, project, family-file and library-maintenance utilities that sit alongside the main browsing and loading workflows.

---

## Open Content Browser Tools

On the Revit ribbon:

**Flow → Content → Browser**

Then open **Tools**.

<!-- SCREENSHOT: Tools menu.
Show the complete menu without clipped items. -->

---

## Sheet & Drafting View Utilities

This window contains six operations:

- **Renumber A-Series** — renumber all non-placeholder A0–A5 sheets within each series.
- **Renumber P-Series** — renumber all non-placeholder sheets beginning with P.
- **Convert P → R** — replace the P prefix on all matching sheets.
- **Convert R → P** — replace the R prefix on all matching sheets.
- **Rename Drafting Views** — apply sheet/detail prefixes to eligible drafting views.
- **Renumber Viewports** — renumber drafting-view viewports by pick order on the active sheet.

### A-Series and P-Series Numbering

Flow uses the existing numeric order, including letter suffixes, to establish the new sequence. Numbers reserved by sheets outside the operation are skipped.

The first sheet whose name contains `!INFO` receives the zero number for its series, such as `A00`, `A10` or `P00`. Remaining sheets begin at `A001`, `A101` or `P001` as applicable.

### Rename Drafting Views

Only drafting views whose drafting-view type name begins with a number are renamed. Placed views receive `{sheet number}-{detail number}-`; unplaced views receive `x-`. Recognised existing prefixes are removed before the new prefix is applied.

### Renumber Viewports

Open the required sheet first, then select **Renumber Viewports**. Pick drafting-view viewports in the desired order, starting at 1, and press **Esc** when finished. Picked viewports are temporarily shown in halftone and their original overrides are restored afterward.

---

## Auto Adjust Crop Regions

Use this tool to resize eligible plans, sections, elevations and detail views around selected model categories.

1. Select **Auto Adjust Crop Regions**.
2. Choose one or more candidate views.
3. Select **Adjust Crops**.
4. Review the per-view result.

Flow uses walls, floors, roofs, stairs, structural framing, generic models, section markers and elevation markers to calculate the extents. It applies a fixed 300 mm margin.

The operation activates and displays the crop region and disables annotation crop. If a custom crop shape prevents the rectangular result, Flow can remove that custom shape and try again.

Views with no target elements or an extent exceeding 47,000 mm are skipped. Candidate views are also restricted by Flow view-naming rules.

!!! warning "Crop settings can change"

    Review selected views before running the tool. Annotation crop and custom crop shapes may be changed as part of the adjustment.

---

## Transfer Project Standards

1. Select **Transfer Project Standards**.
2. Choose one `.rte` source template.
3. Select the standards to transfer.
4. Select **Transfer** and review the result for each standard.

Available standards are Dimension Styles, Fill Patterns, Fill Region Types, Filters, Global Parameters, Line Patterns, Print Settings, Project Parameters, Text Types and View Templates.

Some categories copy only names missing from the project. When duplicate type names occur, Flow retains the destination project's existing type. Each selected standard is attempted independently.

---

## Reload Project Families

Select family categories and reload matching loaded families from the current library.

See [**Reload Project Families**](project-content.md#reload-project-families).

---

## Purge Selected Unused Types

This is a category-based purge, not an individual type picker.

1. Select **Purge Selected Unused Types**.
2. Review the available categories: **Windows**, **Doors** and **Basic Walls**.
3. Clear any category that should not be processed.
4. Select **Purge**.
5. Review the deleted-type and dependent-element totals.

All three categories are selected by default.

!!! warning "Dependent elements can be deleted"

    Flow deletes all elements Revit reports as unused in the selected categories. Revit may also delete dependent elements. Review the categories before continuing.

---

## Sheet Copier

Use **Sheet Copier** to copy selected sheets from another Revit project.

1. Choose a source `.rvt` file and click **Load Sheets**.
2. Search and select the required non-placeholder sheets.
3. Click **Copy Selected**.
4. Review the copied and failed sheet numbers.

The last source path is remembered for the current Windows user. Flow copies the title block, eligible sheet-owned elements, schedules and legends. Existing destination types are retained.

If an incoming sheet number already exists, Flow may move a continuous sequence of existing destination sheet numbers upward to create space. Otherwise, it selects the next available number.

!!! note "Viewport limitation"

    Ordinary model and drafting-view viewports are not copied. Legend viewports are copied or matched and placed on the new sheet.

---

## Family File Cleanup

Use this utility to create audited, compact copies of selected `.rfa` files.

1. Choose a source folder and output folder.
2. Click **Scan Families**.
3. Review the recursively discovered files; all are initially selected.
4. Click **Clean Families**.
5. Review progress and the processed/failed result.

The source files are not changed. Existing files with the same name in the output folder are overwritten.

!!! warning "Folder structure is not currently preserved"

    Cleaned files are written directly into the selected output folder. Families from different source folders that share a filename can overwrite one another.

Cancelling progress stops before the next file; output files already created remain in place.

---

## Clean Revit Backups

1. Choose a folder to scan.
2. Optionally include matching preview PNGs and filenames containing `-adaltpc`.
3. Click **Scan**.
4. Review and select the recursively discovered files.
5. Click **Delete Selected** and confirm the deletion.

Revit backup files are always included. Matching uses a numeric suffix before `.rfa`, `.rvt` or `.rte`; it is not limited to four digits.

Preview matching looks for `.png` filenames containing `3D Vie` or `3D View`. The `-adaltpc` match is case-insensitive.

!!! danger "Deletion is permanent"

    The operation uses direct file deletion rather than moving files to the Recycle Bin. Confirm that the selected files are no longer required.

---

## Copy Folder Structure

Use this tool to reproduce a folder hierarchy without copying files.

1. Choose the source folder.
2. Choose an existing destination folder.
3. Enter the new root-folder name.
4. Click **Copy**.

Invalid filename characters are replaced with underscores. A blank name becomes `Copied_Structure`.

If the named destination already exists, Flow adds any missing subfolders to it. Existing folders and files are left in place.

!!! warning "Keep the destination outside the source"

    Do not select a destination inside the source hierarchy. The current workflow does not block that arrangement.

---

## Rebuild Index

**Rebuild Index** is on the main Browser window. It rescans the current library, writes a new `content_index.json` and reloads the Browser.

Use it after library content or classification changes. Write access to the library location is required.

---

## Clear Cache

**Clear Cache** removes the local version-specific content mirror and recreates its empty folder. Source library files are not deleted.

Use it when a cached family, catalogue or preview is stale. Content is copied into the cache again when subsequently selected.

---

## Getting Help

Hover over **Browser** on the Flow ribbon and press **F1** to open the Content Browser help.

---

## Related Help

- [**Content Browser**](index.md)
- [**Browsing and Searching**](browsing-and-searching.md)
- [**Loading Content**](loading-content.md)
- [**Project Content**](project-content.md)
- [**Content Actions**](content-actions.md)
- [**Troubleshooting**](troubleshooting.md)

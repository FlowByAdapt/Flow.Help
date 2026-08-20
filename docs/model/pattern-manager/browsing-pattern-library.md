# Browsing the Pattern Library

Use the **Pattern Library** tab to find approved PAT content, review its definition and load it into the active Revit project.

---

## Open the Pattern Library

On the Revit ribbon:

**Flow → Model → Patterns**

Open the **Pattern Library** tab.

When Pattern Manager opens, Flow scans the configured hatch-pattern library and all of its subfolders for `.pat` files. The summary cards show the number of PAT files, parsed patterns, pattern folders and reading warnings.

---

## Browse by Folder

Use the folder list to show:

- **All Folders**; or
- patterns in a selected library folder and its subfolders.

The folder path shown on each pattern helps identify where the source PAT definition is stored.

---

## Search for a Pattern

Enter text in the library search box. Search matches:

- pattern names; and
- pattern descriptions.

Search and folder filtering work together. Clear the search or return the folder filter to **All Folders** if an expected pattern is not visible.

!!! tip "Search by a distinctive term"

    You do not need to enter the complete pattern name. A material, bond, size or other distinctive term is usually enough to narrow the results.

---

## Review a Pattern

Select a pattern card to review its available information and preview.

Depending on the PAT definition, Pattern Manager can show:

- name and description;
- model or drafting target;
- millimetre or inch units;
- source folder and PAT file information;
- grid definitions; and
- parsing or validation warnings.

The preview is a graphical aid. Dense dot patterns, very large repeats or unusual dash definitions may be simplified by the preview even when the resulting Revit pattern is valid.

---

## Refresh the Library

Click **Refresh** after PAT files have been added, removed or changed outside Pattern Manager.

Flow rescans the library, rebuilds the folder list and updates the summary metrics and warnings.

---

## Load a Pattern

1. Select the required library pattern.
2. Review its target, units and preview.
3. Click **Load**.

Flow applies the standard project naming format and adds the pattern to the current Revit project.

If a pattern with the same standardised name and target already exists, Flow uses that existing project pattern rather than creating a second duplicate.

!!! note "Model and drafting patterns are separate"

    Revit treats model and drafting patterns as different targets. Always check that the selected library pattern is intended for the required use.

---

## Library Warnings

A warning does not necessarily mean the whole library is unavailable. Flow continues reading other valid files and patterns wherever possible.

Warnings can identify issues such as:

- an unreadable PAT file;
- an unsupported or missing target declaration;
- missing or unknown units;
- malformed numeric grid data; or
- a pattern with no usable grid definitions.

Open or correct the affected PAT file, then click **Refresh**.

---

## Related Help

- [Pattern Manager](index.md)
- [Project Patterns](project-patterns.md)
- [Importing and Exporting Patterns](importing-and-exporting-patterns.md)
- [Troubleshooting](troubleshooting.md)
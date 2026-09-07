# Bulk Parameter Editor

!!! info "Not currently available"

	Bulk Parameter Editor is not exposed as a completed workflow in the current Parameters Manager interface.

There is currently no Parameters Manager button for selecting multiple Revit files, reviewing their parameter data in a grid, or applying general parameter changes across those files.

---

## Current Batch Functionality

The available batch-related maintenance workflow is **Fix Keynotes**.

Fix Keynotes:

- Scans a selected folder recursively
- Finds supported `.rfa`, `.rvt` and `.rte` files
- Excludes numbered Revit backups and existing `NewFiles` content
- Starts a configured keynote-standards batch job
- Directs processed output to a `NewFiles` folder

It is a specialised keynote-standard workflow, not a general Bulk Parameter Editor.

See [Fixing Keynotes](fixing-keynotes.md).

---

## Proposed Direction

Bulk Parameter Editor is intended to support controlled parameter maintenance across multiple Revit files through a reviewable, grid-based workflow.

Potential future stages may include:

1. Selecting Revit files or a source folder
2. Scanning supported parameter data
3. Reviewing the results in a data grid
4. Preparing proposed value changes
5. Applying selected changes in batch
6. Saving processed copies for review

!!! note "Proposed functionality"

	These steps describe the development direction rather than a current production workflow. The supported file types, parameter types, filters, validation and editing controls remain subject to implementation.

---

## What to Use Now

Use the current Parameters Manager workflows for project-side Opening Global Parameters:

- **Opening GP Dashboard** for review and supported value editing
- **Review Associations** for instance and type associations
- **Copy GP Setup** for copying matching associations inside the active project
- **Apply Window Standards** and **Apply Door Standards** for configured opening setup
- **Import Office Standard GPs** for importing missing GPs from one `.rte` or `.rvt`
- **Fix Keynotes** for the current external-file keynote batch process

None of these commands provides arbitrary multi-file parameter editing.

---

## Documentation Status

This page should remain an availability notice until a Bulk Parameter Editor command is present in the production interface and its complete implementation has been reviewed.

Once implemented, this page should be replaced with verified instructions covering:

- Supported source files
- Parameter scope
- Scan and filtering rules
- Editable values
- Validation
- Output and source-file safeguards
- Cancellation and recovery
- Batch results

---

## Related Help

- [Parameters Manager](index.md)
- [Project Parameters](project-parameters.md)
- [Family Parameters](family-parameters.md)
- [Fixing Keynotes](fixing-keynotes.md)

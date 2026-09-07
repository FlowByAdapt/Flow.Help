# Parameters Manager

**Parameters Manager** brings together Flow tools for reviewing Opening Global Parameters, checking and managing their associations, applying window and door standards, and carrying out related maintenance.

The current release is focused primarily on the Global Parameters used by Flow opening workflows. It is not a general editor for every project, family or shared parameter.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Open the Revit project containing the elements and Global Parameters you want to work with.

Most Parameters Manager workflows act on the current project. Selection-based workflows temporarily move Parameters Manager out of the way so you can select elements in Revit.

!!! warning "Work in the correct project"

	Confirm that the intended Revit project is active before running a setup, association-removal or cleanup workflow.

---

## Opening Parameters Manager

On the Revit ribbon, select:

**Flow → Content → Parameters Manager**

Parameters Manager opens as a modeless window, allowing you to continue interacting with Revit. If the window is already open, launching the command again activates the existing window rather than opening another copy.

The **Opening GP Dashboard** scans the current project automatically when the window first opens.

<!-- SCREENSHOT: Complete Parameters Manager window immediately after opening. Show the four left-hand sections, three dashboard cards and dashboard grid. -->

---

## First-Time Workflow

For your first use, follow this sequence:

1. Open **Parameters Manager** in the project you want to inspect.
2. Review the **Total GPs**, **Associated** and **Unused** dashboard cards.
3. Select a card to filter the dashboard grid.
4. Review GP names, current values, association counts and statuses.
5. If you need to inspect an element, use **Review Associations** before changing anything.
6. Run the required setup, audit or maintenance workflow from the left-hand menu.
7. Review the completion message, including any skipped or failed items.
8. Select **Audit → Refresh Dashboard** to rescan the project after most changes.

Unused Opening GP cleanup refreshes the dashboard automatically after confirmed deletion. Other workflows may leave the dashboard showing the results of its previous scan until you refresh it.

---

## Opening GP Dashboard

The dashboard provides a project-level overview of the Global Parameters included in its current scope.

### Summary Cards

| Card | What It Shows |
| --- | --- |
| **Total GPs** | All Global Parameters included in the dashboard. |
| **Associated** | Global Parameters with at least one association detected by the dashboard scan. |
| **Unused** | Global Parameters for which the dashboard scan detected no associations. |

Select a card to filter the grid. Select **Total GPs** to return to the complete dashboard list.

<!-- SCREENSHOT: Dashboard after selecting Associated or Unused. Include the updated subtitle and filtered grid. -->

### Dashboard Grid

| Column | Description |
| --- | --- |
| **GP Name** | Global Parameter name. |
| **Type** | Value type reported by Flow. |
| **Current Value** | Displayed value and, where supported, an editable value. |
| **Associations** | Number of associations detected during the dashboard scan. |
| **Status** | **Associated** or **Unused**, based on the detected count. |

!!! note "Dashboard scope"

	The dashboard intentionally excludes a fixed group of office graphics and project-control Global Parameters. **Total GPs** therefore does not represent every Global Parameter stored in the Revit project.

!!! warning "What Unused means"

	**Unused** means that this dashboard scan did not detect an association. It is not, by itself, confirmation that the Global Parameter is safe to delete.

	The current scan is based on non-type elements and may not detect a Global Parameter used only by a type parameter. Use **Review Associations**, **GP Audit**, or Revit's native Global Parameters tools where additional confirmation is required.

For more detail, see [Reviewing Global Parameters](reviewing-global-parameters.md).

---

## Editing a Global Parameter Value

Editable **Current Value** cells display an edit indicator.

1. Find the required Global Parameter.
2. Double-click its editable **Current Value** cell.
3. Enter the new value.
4. Press **Enter** or leave the cell to commit the edit.
5. Select **Refresh Dashboard** to confirm the stored result.

Direct dashboard editing is currently available for:

- **Text**
- **Length / Number** values represented by a Revit double value

The following are read-only in the dashboard:

- **Integer / Yes-No**
- **Element**
- Unsupported or unknown value types
- **Zero Window Sill Height**

!!! info "Displayed units"

	Global Parameters with **Angle** in their name are displayed and entered in degrees. Other double values are displayed and entered as millimetres.

	This conversion is name-based. Use Revit's native Global Parameters editor when the displayed interpretation does not suit the parameter.

Invalid numeric input is not applied. Formula-controlled or otherwise non-settable values may also be rejected by Revit.

<!-- SCREENSHOT: One editable Current Value cell in edit mode beside a read-only value. -->

See [Editing Global Parameter Values](editing-global-parameter-values.md).

---

## Associations

Expand **Associations** to inspect, copy or remove Global Parameter associations.

### Review Associations

Use **Review Associations** before modifying an unfamiliar element.

1. Select **Review Associations**.
2. Pick one element in Revit.
3. Review the reported parameter, Global Parameter, scope and storage type.
4. Select **Close** when finished.

The review includes supported associations found on both the selected instance and its Revit type. The **Scope** column identifies each association as **Instance** or **Type**. This workflow makes no changes.

### Copy GP Setup

Use **Copy GP Setup** to apply matching associations from a configured source element to one or more targets.

1. Select **Copy GP Setup**.
2. Pick the source element first.
3. Pick one or more target elements.
4. Finish the Revit selection.
5. Review the completion totals.

The copy begins immediately after target selection; there is no separate preview. Flow matches target parameters by name, preserves existing conflicting associations, and skips missing, read-only or incompatible parameters.

Type associations are applied to the target type and can therefore affect other instances of that type.

### Remove Associations

Use **Remove Associations** to disconnect selected element parameters from their Global Parameters.

1. Choose **Pick Elements** or **Current Selection**.
2. Review the discovered associations.
3. Clear any rows you want to retain. All rows are selected initially.
4. Use **Select All** or **Select None** where helpful.
5. Select **Remove Selected**.
6. Review the removed and failed counts.

!!! warning "Type associations"

	Removing a row whose scope is **Type** changes the shared Revit type. Other instances using that type can be affected.

See:

- [Reviewing Associations](reviewing-associations.md)
- [Copying GP Setup](copying-gp-setup.md)
- [Removing Associations](removing-associations.md)

---

## Audit

### GP Audit

Use **GP Audit** to compare association counts for selected elements.

1. Select **GP Audit**.
2. Choose whether to audit multiple elements.
3. Pick the required element or elements.
4. Review the Category, Mark, Family/Type, GP Count and Status columns.
5. Select **Close** when finished.

The current expected-count rules are calibrated for windows. Other categories may be reported as **Not Required**.

Possible window statuses include:

- **Not Configured** — no associations were detected.
- **Missing _n_** — fewer associations were detected than the configured expected count.
- **Complete** — the detected count meets or exceeds the expected count.
- **Not Required** — no expected association count is configured for that category.

!!! note "Count-based audit"

	GP Audit compares association quantities. It does not prove that every parameter is connected to the correct Global Parameter. Use **Review Associations** when the exact mapping matters.

### Refresh Dashboard

Select **Refresh Dashboard** after applying setup, copying or removing associations, importing GPs, or editing values.

See [Auditing Global Parameters](auditing-global-parameters.md).

---

## Setup

### Apply Window Standards

Use **Apply Window Standards** for supported wall-hosted windows created in the Revit phase named **New Construction**.

1. Select **Apply Window Standards**.
2. Choose **Pick Windows** or **All Windows**.
3. If picking, select only the required standard windows and finish the selection.
4. Flow identifies each window's host wall type and resolves the applicable preset.
5. Missing GPs are created where the required family parameter provides a suitable data type.
6. Flow applies supported instance or type associations.
7. Review the completion summary and any skipped items.
8. Refresh the dashboard.

Flow automatically excludes curtain-wall-related elements. An element is skipped when it is not in New Construction, lacks a matching wall-type preset, or lacks required compatible parameters.

Depending on the preset, Flow may create:

- Level-specific names such as `Window Head Height_Level 1`
- Wall-type-specific names using the resolved preset name as a suffix

Where appropriate, the seed GP named `Window Head Height` may be renamed to the required level-specific name.

Existing GP values are retained. Preset values are applied when Flow creates a new GP.

!!! warning "Existing associations"

	Apply Window Standards does not replace a parameter that already has a GP association. Review existing associations if a window does not respond to the expected standard.

<!-- SCREENSHOT: Selected standard wall-hosted windows followed by the Window GP Setup completion summary. -->

See [Applying Window Standards](applying-window-standards.md).

### Apply Door Standards

Use **Apply Door Standards** for supported Doors-category elements created in **New Construction**.

Choose:

- **Pick Doors**
- **All New Construction Doors**
- **Cancel**

Flow creates missing standard GPs where required and applies compatible instance associations. Current creation defaults include:

- **Architrave_Depth:** 20 mm
- **Architrave_Width:** 60 mm
- **Plan % Open:** 40

The result reports newly created associations. A result of zero can mean that qualifying parameters were already associated, as well as that nothing new could be applied.

See [Applying Door Standards](applying-door-standards.md).

### Apply Existing Window Standards

Use **Apply Existing Window Standards** for Windows-category family instances created in the phase named **Existing**.

1. Select the workflow.
2. Pick the required existing windows.
3. Finish the selection.
4. Flow creates missing existing-window GPs where possible and applies supported instance associations.
5. Review the found, created, applied and skipped counts.
6. Refresh the dashboard.

Defaults are applied only to newly created GPs. Existing same-name GP values are retained.

See [Applying Existing Window Standards](applying-existing-window-standards.md).

### Import Office Standard GPs

Use this workflow to import GPs missing from the current project.

1. Select **Import Office Standard GPs**.
2. Choose one Revit project or template file (`.rvt` or `.rte`).
3. Flow compares GP names case-insensitively.
4. All missing GPs are imported automatically.
5. Review the import result.
6. Refresh the dashboard.

Existing same-name GPs are not duplicated, validated or updated. The selected source file is closed without modification.

See [Importing Office Standard Global Parameters](importing-office-standard-global-parameters.md).

---

## Maintenance

### Find Unused Opening GPs

This workflow searches for apparently unused GPs whose names match Flow's opening-related naming patterns.

1. Select **Find Unused Opening GPs**.
2. Review the candidate list. Up to 30 names are shown in the confirmation.
3. Choose **No** to leave everything unchanged.
4. Choose **Yes** to delete all listed candidates.
5. Review the deletion result.

The dashboard refreshes automatically after confirmed cleanup.

!!! danger "Review before deleting"

	The current unused-GP scan may not detect associations used only by type parameters. Confirm unfamiliar candidates before deleting them.

	The protected GPs `Window Head Height`, `X-Window Head Height`, and `Zero Window Sill Height` are not offered for deletion.

See [Finding Unused Opening GPs](finding-unused-opening-gps.md).

### Fix Keynotes

**Fix Keynotes** starts a separate batch process for supported Revit files beneath a selected folder.

The folder scan is recursive and includes `.rfa`, `.rte` and `.rvt` files. Numbered Revit backups and files already inside a `NewFiles` folder are excluded. Processed output is directed to **NewFiles**.

The initial Parameters Manager message confirms that the batch job started; it does not by itself confirm that every file completed successfully. Review the batch results and output copies.

See [Fixing Keynotes](fixing-keynotes.md).

### Open Native GP Editor

Use **Open Native GP Editor** for operations not supported directly by the dashboard.

If Revit cannot expose the command through Flow, use:

- Revit shortcut **GG**, or
- **Manage → Global Parameters**

See [Native Global Parameter Editor](native-global-parameter-editor.md).

---

## Expected Results

After a successful workflow:

- The requested GP values or associations are changed in the current Revit project.
- Setup workflows may create missing Global Parameters.
- Completion messages identify applied, skipped or failed operations.
- The dashboard reflects the new project state after it is refreshed.

Partial success is possible. Always review skipped and failed counts rather than relying only on the fact that the command completed.

---

## Current Limitations

- Parameters Manager requires an active Revit project.
- The dashboard is not a complete list of every project GP.
- Type-only GP associations may not be detected by the dashboard or unused-GP cleanup.
- GP Audit is count-based and currently calibrated primarily for windows.
- Direct dashboard editing does not support Integer/Yes-No or Element values.
- Unit conversion for double values is based partly on the GP name.
- Setup workflows do not overwrite existing conflicting associations.
- Window standards depend on recognised host wall types and available preset files.
- Broader project, family and bulk parameter editing is not yet available from this window.

---

## Related Help

- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Editing Global Parameter Values](editing-global-parameter-values.md)
- [Reviewing Associations](reviewing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Applying Window Standards](applying-window-standards.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

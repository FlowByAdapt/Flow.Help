# Parameters Manager Troubleshooting

Use these checks when the Opening GP Dashboard or a Parameters Manager workflow does not produce the expected result.

---

## Parameters Manager Does Not Open

Check that:

1. A Revit project is open and active.
2. Flow loaded correctly for the current Revit version.
3. Another Parameters Manager window is not already open behind Revit or on another display.

Launching Parameters Manager again should activate its existing window rather than opening a duplicate.

---

## The Dashboard Has Not Updated

The dashboard scans automatically when Parameters Manager first opens, but most workflows do not refresh it automatically.

1. Expand **Audit**.
2. Select **Refresh Dashboard**.
3. Confirm that the intended Revit project is active.

Refresh after editing values, copying or removing associations, applying standards, importing GPs, or changing GPs through Revit's native editor.

Confirmed unused-GP deletion refreshes the dashboard automatically.

---

## A Global Parameter Is Missing from the Dashboard

The Opening GP Dashboard deliberately excludes a fixed group of office graphics and project-control GPs.

Try:

1. Select **Refresh Dashboard**.
2. Open **Maintenance → Open Native GP Editor**.
3. Confirm whether the GP exists in the complete Revit list.

**Total GPs** means all GPs in the dashboard's scope, not every GP in the project.

---

## A Global Parameter Appears Unused but Has an Association

The dashboard scans parameters on non-type elements. A GP used only through a type parameter may not be counted and can appear **Unused**.

1. Do not delete the GP based only on the dashboard status.
2. Run **Review Associations** on a representative instance.
3. Look for a row whose scope is **Type**.
4. Check the GP in Revit's native tools.

This limitation also affects **Find Unused Opening GPs**.

!!! danger "Confirm type associations before cleanup"

	The current cleanup scan may offer a type-associated GP for deletion. Choose **No** if any candidate is uncertain.

---

## I Cannot Edit a Current Value

Direct dashboard editing is limited to:

- Text
- Double values displayed as **Length / Number**

The following are read-only:

- Integer / Yes-No
- Element
- Unsupported or unknown types
- `Zero Window Sill Height`

Use **Open Native GP Editor** for unsupported values.

---

## A Numeric Edit Does Not Persist

1. Enter a plain numeric value without unit text.
2. Press **Enter** or **Tab**, or move away from the cell.
3. Select **Refresh Dashboard**.
4. Confirm that the GP is not formula-controlled or otherwise restricted by Revit.
5. Try the same edit in Revit's native editor.

Invalid numeric input is rolled back and may not produce a dedicated validation message. The typed text can remain visible until the dashboard is refreshed.

---

## An Angle or Number Uses the Wrong Units

The dashboard treats a double GP as degrees only when its name contains **Angle**. Other double GPs are treated as millimetres.

Use Revit's native editor when this name-based interpretation is unsuitable.

---

## Review Associations Finds Nothing

Review Associations checks both the selected element and its Revit type.

If no rows are found:

1. Confirm that you selected the intended element.
2. Confirm in Revit that the parameter is actually GP-associated.
3. Check whether Revit exposes that parameter's association through its API.
4. Try another representative instance.

Review Associations reports current mappings; it does not judge whether they comply with a Flow preset.

---

## Copy GP Setup Skips Some Associations

Check that:

1. The source element has the intended associations.
2. The target has parameters with matching names.
3. The appropriate target instance or type exists.
4. The target parameter is not read-only.
5. The target parameter does not already have a different GP.
6. The GP and target parameter have compatible Revit data types.

The completion message reports **Skipped / Not Applied** as one combined count. It does not display its stored per-target detail records.

If the target is already connected to the required GP, Flow treats that attempt as successful even though no new change was needed.

---

## Remove Associations Finds Nothing

Check that:

1. The intended elements were picked or preselected.
2. The associations exist on either the instances or their types.
3. Revit exposes those associations through its API.

If **Current Selection** is chosen without selected elements, Flow reports that no elements are currently selected.

---

## Remove Selected Reports No Associations Selected

At least one checkbox must be selected in the removal-review window.

Use individual checkboxes or **Select All**, then select **Remove Selected** again.

Remember that every row is selected when the review window first opens.

---

## Removing a Type Association Affected Other Elements

A row whose scope is **Type** belongs to a shared Revit type. Removing that association affects other instances that use the same type.

Use Revit Undo immediately if the removal was unintended, then review the type setup before repeating the workflow.

---

## The GP Audit Summary Shows Zero Categories

The current summary sentence above the audit grid counts older status labels and may show zero for all summary categories.

Use the individual grid rows as the current result:

- **Not Required**
- **Not Configured**
- **Missing _n_**
- **Complete**

---

## GP Audit Reports Not Required

The current expected-count configuration is calibrated for Windows.

Doors, Curtain Walls and other categories currently have an expected count of zero and are reported as **Not Required**.

Use **Review Associations** to inspect their actual mappings.

---

## GP Audit Reports Complete but the Setup Is Wrong

GP Audit compares association counts. It does not verify the identity of each parameter-to-GP mapping.

A window can reach the expected count using an unrelated or incorrect association.

1. Run **Review Associations**.
2. Compare the exact parameter and GP names.
3. Check the window's applicable preset.

The current audit expects 19 associations for Windows, while some presets can define a different number of potential associations.

---

## Apply Window Standards Finds No Valid Windows

For **All Windows**, check that the project contains Windows-category instances created in **New Construction** and not hosted by curtain walls.

For **Pick Windows**, select only standard wall-hosted window instances.

Flow skips elements that:

- Are curtain-wall-related
- Were not created in New Construction
- Have no supported host wall
- Do not resolve to an available preset

---

## Apply Window Standards Reports Missing Presets

Preset resolution depends on the host wall type.

Check that:

1. The window is hosted by a standard wall.
2. The host wall type matches an explicit mapping or configured name pattern.
3. The mapped preset file exists in the active preset folder.
4. The preset name, configured wall-type name or filename matches the resolved name.

The first matching configured name pattern is used.

---

## Apply Window Standards Reports Missing Parameters

The selected family may not contain every instance or type parameter required by the preset.

Check:

1. The exact family parameter name.
2. Whether it exists on the instance or type.
3. Whether its Revit data type is compatible with the required GP.
4. Whether the family variant intentionally omits that parameter.

Some expected optional family omissions are consolidated as **Hidden expected family skips** in the result.

---

## A Window Has the Wrong GP but Reports Already Associated

The current window preview considers a parameter already associated when it finds any GP association. It does not first prove that the association points to the GP required by the preset.

1. Run **Review Associations** on the window.
2. Confirm the exact GP name.
3. Remove or correct a conflicting association deliberately before applying the standard again.

---

## An Existing GP Value Was Not Updated by Window Standards

Window setup workflows retain existing same-name GP values. Preset or creation defaults are applied only when Flow creates a missing GP.

Edit the existing value deliberately through the dashboard or Revit's native editor if the project standard needs to change.

---

## Door Standards Reports Zero Associations Applied

The result counts newly created associations only.

Zero can mean:

- Qualifying parameters were already associated
- Selected elements were not doors
- Doors were not created in New Construction
- Required instance parameters were missing
- Parameters were read-only or incompatible
- Different GPs were already associated

Run **Review Associations** on a representative door to identify the case.

---

## Existing Window Standards Skips Items

Check that:

1. The selected elements are Revit window family instances.
2. Their created phase is named **Existing**.
3. Required parameters exist on the instances.
4. Existing GPs have compatible data types.
5. Parameters do not have conflicting associations.

The completion result combines missing, incompatible and failed items in one **Skipped** count.

---

## Office Standard GP Import Does Not Start

Check that:

1. A destination Revit project is open.
2. The selected source is an accessible `.rte` or `.rvt` file.
3. The source can be opened by the current Revit version.
4. The source contains Global Parameters.

The picker does not accept `.rfa` files.

---

## Office Standard Import Does Not Update an Existing GP

The import compares GP names case-insensitively. An existing same-name destination GP prevents the source GP from being imported.

Flow does not compare or update the existing GP's:

- Value
- Data type
- Formula
- Other settings

Use Revit's native editor when an existing GP must be reviewed or changed.

---

## An Expected GP Appears in Unused Cleanup

Choose **No** and investigate before deleting it.

Check whether:

- It is used only by a type parameter
- Its intended elements are temporarily absent
- It is a level-specific or wall-type-specific GP awaiting use
- Its name matches an opening prefix but it serves another purpose

The cleanup preview is not individually selectable. Confirming **Yes** processes the complete candidate set found when cleanup executes.

---

## Native GP Editor Does Not Open

Flow attempts to post Revit's native Global Parameters command.

If Revit does not expose or permit that command in the current state:

- Use shortcut **GG**, or
- Open **Manage → Global Parameters**

---

## Fix Keynotes Finds the Wrong Number of Files

The scan searches the selected folder recursively.

It includes:

- `.rfa`
- `.rvt`
- `.rte`

It excludes:

- Numbered Revit backups such as `.0001.rvt`
- Files already inside `NewFiles`
- Other file extensions

Check the complete folder tree and the startup message's **Files found** count.

---

## Fix Keynotes Starts but Output Is Missing or Incomplete

The Parameters Manager message confirms that the external BatchRunner was started. It does not confirm final per-file success.

Check:

1. The run folder reported in the startup message.
2. The batch result information.
3. The `NewFiles` output folder.
4. The installed `KeynoteStandards.json` configuration.
5. Whether source files can be opened by the selected Revit version.
6. Whether the BatchRunner executable is present.

Closing Parameters Manager is not a verified cancellation of an already-started batch.

---

## Reporting a Problem

Record:

- Revit version
- Active project
- Parameters Manager workflow used
- Selection mode
- Selected element category, family, type and phase
- Relevant GP and parameter names
- Expected result
- Actual result
- Completion counts or Flow message
- Screenshot of the dashboard, review window or result

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Editing Global Parameter Values](editing-global-parameter-values.md)
- [Reviewing Associations](reviewing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Applying Window Standards](applying-window-standards.md)
- [Finding Unused Opening GPs](finding-unused-opening-gps.md)

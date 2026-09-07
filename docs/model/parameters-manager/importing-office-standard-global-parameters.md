# Importing Office Standard Global Parameters

Use **Import Office Standard GPs** to copy Global Parameters that are missing from the current project from one selected Revit project or template.

Flow compares Global Parameters by name and automatically imports every missing GP found in the selected source.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Confirm that:

- The destination project is the active Revit project
- You know which approved office-standard `.rte` or `.rvt` file should be used as the source
- The source file contains the Global Parameters you intend to make available

!!! warning "All missing GPs are imported"

	After you select the source file, Flow proceeds automatically. There is no second confirmation and no individual GP-selection window.

---

## Import the Missing Global Parameters

1. Open **Parameters Manager** in the destination project.
2. Expand **Setup**.
3. Select **Import Office Standard GPs**.
4. In **Select Office Standard Template**, choose one Revit project or template:
   - `.rte`
   - `.rvt`
5. Select **Open**.
6. Wait while Flow opens and inspects the source file.
7. Review the import result.
8. Select **Audit → Refresh Dashboard**.

The file picker does not include Revit family files (`.rfa`).

<!-- SCREENSHOT: Select Office Standard Template file picker with the Revit Files (*.rte;*.rvt) filter visible. -->

---

## How Flow Determines What Is Missing

Flow builds two name lists:

- Global Parameters in the selected source file
- Global Parameters in the active destination project

The names are compared case-insensitively.

For example, if the source contains `Architrave_Width` and the destination already contains `architrave_width`, Flow treats that name as already present and does not import another GP.

Flow then copies every source GP whose name is missing from the destination.

---

## What Happens to Existing Global Parameters

An existing same-name GP is left unchanged.

The import does not:

- Replace the existing GP
- Update its value
- Validate its Revit data type against the source
- Correct its formula or other settings
- Create a duplicate based only on different capitalisation

!!! note "Name comparison only"

	A matching name prevents import even when the destination GP differs from the source in another respect. Review existing project standards separately where exact equivalence matters.

---

## What Flow Does Automatically

After file selection, Flow:

1. Converts the selected path to a Revit model path.
2. Opens the source file without making it the active project.
3. Collects the source and destination GP names.
4. Calculates the missing names case-insensitively.
5. Resolves the corresponding source GP elements.
6. Copies all resolved missing GPs into the destination in one Revit transaction.
7. Displays the result.
8. Closes the source file without saving it.

The source file is also closed without saving if the import encounters an error after opening it.

---

## Import Results

### No Global Parameters Are Missing

If every source GP name already exists in the destination, Flow reports:

- Source template filename
- Number of source GPs
- Number of destination-project GPs
- Missing GPs: 0
- No office-standard GPs are missing

No project transaction is required in this case.

### Global Parameters Are Imported

When missing GPs are found, Flow reports:

- Source template filename
- Missing GPs before import
- Imported GPs

<!-- SCREENSHOT: Successful Import Office Standard GPs result showing the source filename, missing count and imported count. -->

If missing names are found but their source GP elements cannot be resolved, Flow reports that no matching Global Parameters could be resolved for import.

---

## Expected Result

After a successful import:

- Every resolved source GP whose name was missing exists in the destination project
- Existing same-name destination GPs remain unchanged
- The source file remains unchanged
- The dashboard can be refreshed to show imported GPs within its opening-focused scope

Imported GPs outside the dashboard's scope may be visible only in Revit's native Global Parameters editor.

---

## Cancel the Workflow

Close or cancel the file picker without selecting a file.

No source document is opened and no project changes are made.

Once a source file has been accepted, the import comparison and copy proceed automatically.

---

## If the Import Does Not Start

Check that:

1. A destination Revit project is open and active.
2. The selected source is a valid `.rte` or `.rvt` file.
3. The source can be opened by the current Revit version.
4. The file is accessible and not blocked by permissions or another file operation.
5. The source actually contains Global Parameters.

If Flow reports that nothing is missing, check for same-name GPs in the destination using Revit's native Global Parameters editor.

---

## Current Limitations

- Only `.rte` and `.rvt` source files are available in the picker.
- All missing GPs are imported together.
- Individual missing GPs cannot be selected or excluded.
- The comparison is based only on GP names.
- Existing same-name GPs are not validated or updated.
- The dashboard does not refresh automatically after import.
- Imported GPs excluded from the dashboard scope will not appear there.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Applying Window Standards](applying-window-standards.md)
- [Applying Door Standards](applying-door-standards.md)
- [Native Global Parameter Editor](native-global-parameter-editor.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

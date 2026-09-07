# Applying Window Standards

Use **Apply Window Standards** to create and associate the Global Parameters required by Flow's configured window presets.

The applicable preset is determined from each window's host wall type. This workflow is intended for supported wall-hosted windows created in the Revit phase named **New Construction**.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Check that:

- The intended Revit project is active
- The windows are hosted by standard walls rather than curtain walls
- The windows were created in the **New Construction** phase
- The host wall types follow a configured Flow wall-type mapping or naming pattern
- The window families contain the parameters required by the relevant preset

If a window already has GP associations, consider using **Review Associations** before applying the standard.

---

## Start the Workflow

1. Open **Parameters Manager**.
2. Expand **Setup**.
3. Select **Apply Window Standards**.
4. Choose:
   - **Pick Windows**
   - **All Windows**
   - **Cancel**

<!-- SCREENSHOT: Apply Window Standards chooser showing Pick Windows, All Windows and Cancel. -->

---

## Pick Windows

Use **Pick Windows** when you want to control which windows are processed.

1. Choose **Pick Windows**.
2. Select the required standard wall-hosted windows in Revit.
3. Finish the Revit multi-selection.
4. Wait for Flow to resolve and apply the relevant presets.
5. Review the **Window GP Setup** completion summary.
6. Select **Audit → Refresh Dashboard**.

Parameters Manager temporarily hides while Revit is waiting for the selection, then returns.

!!! tip "Select only windows"

	The current Pick workflow accepts a broad Revit element selection before preset resolution. Select only the intended window instances.

<!-- SCREENSHOT: Several valid wall-hosted windows selected in Revit before finishing Pick Windows. -->

---

## All Windows

Choose **All Windows** to process every qualifying Windows-category instance in the current project that:

- Was created in **New Construction**
- Is not hosted by a curtain wall
- Has a host wall type that resolves to a Flow preset

If no valid windows are found, Flow reports this and applies no setup.

!!! note "Existing windows"

	All Windows does not process windows created in the **Existing** phase. Use [Applying Existing Window Standards](applying-existing-window-standards.md) for those elements.

---

## How Flow Selects a Preset

For each opening, Flow retrieves the host wall type name and resolves a preset in this order:

1. Check for an explicit wall-type mapping.
2. If no explicit mapping exists, test the configured wall-name patterns in order.
3. Use the first pattern that matches.
4. Match the resulting name against the available preset name, configured wall-type name or preset filename.

Pattern matching is case-insensitive. If the window has no standard wall host or no preset can be resolved, Flow skips it as a missing preset.

The preset supplies:

- Common window parameters used across multiple wall types
- Unique parameters whose values or GP names vary by wall construction
- GP names
- Default or typical values used when supported missing GPs are created

<!-- SCREENSHOT: A representative host wall type and the resulting preset-specific GP names in Revit's Global Parameters interface. -->

---

## What Flow Does Automatically

For each qualifying selected element, Flow:

1. Skips curtain-wall-related elements.
2. Skips elements not created in New Construction.
3. Resolves the preset from the host wall type.
4. Combines the preset's common and unique parameter rules.
5. Resolves the required GP name for each rule.
6. Checks for the corresponding parameter on the instance and its type.
7. Finds or creates the required GP.
8. Applies the preset value when a GP is newly created and the value can be resolved.
9. Attempts the instance association first.
10. Falls back to the type parameter when no usable instance parameter is found.
11. Continues to other parameters if an individual row cannot be completed.

The workflow proceeds automatically after selection. It does not show a separate preset preview or confirmation window.

---

## Automatically Generated GP Names

### Window Head Height

When a preset uses the base name `Window Head Height`, Flow generates a level-specific name:

`Window Head Height_[Level name]`

For example:

`Window Head Height_Level 1`

If the level-specific GP does not exist, Flow may rename the seed GP named `Window Head Height` to the required level-specific name.

!!! warning "Seed GP rename"

	Renaming `Window Head Height` changes that GP's name throughout the Revit project. Existing associations to the renamed GP remain connected to the same GP element under its new name.

### Wall-Type-Specific Parameters

When a preset marks a parameter as unique, Flow generates:

`[Base GP name]_[Preset name]`

For example:

`Ext_Sill_Height_ADa_E_Sheet_C`

This allows different host-wall constructions to use different controlling GP values.

---

## Existing Global Parameters and Associations

Flow retains the value of an existing same-name GP. Preset values are applied when Flow creates a new GP, not as a general overwrite of existing project standards.

If the parameter is already associated with a GP, the current preview treats it as **Already Associated** and skips further work on that row.

!!! warning "Check existing associations"

	The current workflow checks whether an association exists but does not verify at the preview stage that it points to the GP required by the preset.

	A parameter connected to a different GP can therefore be counted as **Already Associated** and left unchanged. Use **Review Associations** when the exact mapping matters.

Flow does not deliberately replace an existing conflicting association.

---

## Completion Summary

After processing, Flow reports:

| Result | Meaning |
| --- | --- |
| **Openings processed** | Elements that passed the initial curtain-wall and phase checks. |
| **Global parameters created** | Missing GPs successfully created by this run. |
| **Associations created** | Associations successfully completed during processing. |
| **Already associated** | Parameters for which an existing GP association was detected. |
| **Skipped missing/incompatible parameters** | Required parameters that were missing or could not be associated. |
| **Skipped missing presets** | Elements whose host wall type did not resolve to an available preset. |

The summary can also include selected detail messages. Some known optional family-parameter omissions are consolidated as **Hidden expected family skips** rather than listing every repeated message.

<!-- SCREENSHOT: Window GP Setup completion summary showing all six totals and, if practical, a short Messages section. -->

!!! note "Partial success"

	A completed command does not mean that every requested association was applied. Review the created, associated and skipped counts.

---

## Expected Result

For supported windows:

- Required common and wall-type-specific GPs exist in the project
- Newly created GPs receive supported preset values
- Matching instance or type parameters are associated
- Level-specific and preset-specific GP names are generated where required
- Existing same-name GP values remain unchanged

Refresh the dashboard and inspect representative windows after the workflow completes.

---

## Cancel the Workflow

- Choose **Cancel** in the initial chooser, or
- Press **Esc** while Revit is waiting for Pick Windows selection

Cancellation before the selection is completed submits no setup request.

---

## If a Window Is Skipped

Check whether:

1. The element is a standard window instance.
2. It was created in **New Construction**.
3. It is hosted by a non-curtain wall.
4. Its host wall type matches a configured mapping or naming pattern.
5. The required preset file is available.
6. The family contains the required instance or type parameter.
7. The parameter is compatible with the required GP data type.
8. The parameter already has a different GP association.

Use **Review Associations** to inspect existing mappings and review the completion messages for missing presets or parameters.

---

## Current Limitations

- Pick Windows does not apply a strict Windows-category selection filter before processing.
- Curtain-wall-hosted windows are excluded.
- Only elements created in the phase named **New Construction** are processed.
- Preset resolution depends on the host wall type and available configuration.
- Existing same-name GP values are not updated from the preset.
- Existing associations are not verified against the required preset GP before being treated as already associated.
- Instance parameters are preferred over type parameters.
- Individual rows can fail while the rest of the run succeeds.
- Some family variants do not contain every preset parameter.

---

## Related Help

- [Parameters Manager](index.md)
- [Applying Existing Window Standards](applying-existing-window-standards.md)
- [Applying Door Standards](applying-door-standards.md)
- [Reviewing Associations](reviewing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Importing Office Standard Global Parameters](importing-office-standard-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

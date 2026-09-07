# Applying Existing Window Standards

Use **Apply Existing Window Standards** to create and associate the `X-` Global Parameters used by supported Revit windows created in the phase named **Existing**.

This is a dedicated existing-window workflow. It does not use the host-wall preset system used by **Apply Window Standards** for New Construction windows.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Check that:

- The intended Revit project is active
- The windows were created in the **Existing** phase
- The families contain the required instance parameters
- Existing GP associations have been reviewed where their current setup is uncertain

The workflow processes selected elements only. There is no **All Existing Windows** option in the current interface.

---

## Apply the Setup

1. Open **Parameters Manager**.
2. Expand **Setup**.
3. Select **Apply Existing Window Standards**.
4. Pick one or more existing-window instances in Revit.
5. Finish the Revit multi-selection.
6. Wait for Flow to create and associate the supported GPs.
7. Review the completion summary.
8. Select **Audit → Refresh Dashboard**.

Parameters Manager temporarily hides while Revit is waiting for the selection, then returns.

<!-- SCREENSHOT: Several Existing-phase windows selected in Revit before finishing the selection. -->

If the initial selection contains no Existing-phase family instances, Flow reports:

> No existing-phase windows were selected.

The processing service then retains only elements in the Revit **Windows** category. Other Existing-phase family instances are ignored.

---

## Existing-Window Associations

The current workflow maps these window instance parameters:

| Window Parameter | Global Parameter |
| --- | --- |
| `Ext_Sill_Angle` | `X-Ext_Sill_Angle` |
| `Architrave Show` | `X-Architrave Show` |
| `Architrave_Depth` | `X-Architrave_Depth` |
| `Architrave_Width` | `X-Architrave_Width` |
| `Ext_Trim_Width` | `X-Ext_Trim_Width` |
| `Ext_Sill_Width` | `X-Ext_Sill_Width` |
| `Ext_Sill_Height` | `X-Ext_Sill_Height` |
| `Ext_Trim_Height` | `X-Ext_Trim_Height` |
| `Frame Setback` | `X-Frame Setback` |
| `GlassThickness` | `X-GlassThickness` |
| `Window Head Height` | `X-Window Head Height` |
| `Sill Height` | `Zero Window Sill Height` |
| `Ext Trim Show` | `X-Exterior Trim Show` |
| `Ext Sill Show` | `X-Exterior Sill Show` |
| `Allow Door to Open in 3d` | `3D Doors Show` |

The workflow applies these as instance associations. It does not search the window type for a matching parameter.

---

## Creating Missing Global Parameters

For each required GP, Flow first searches the current project using a case-insensitive name comparison.

When a GP is missing, Flow:

1. Finds a matching parameter on one of the selected windows.
2. Uses that parameter's Revit data type to create the GP.
3. Applies the configured creation default where supported.

If no selected window contains the corresponding parameter, that GP cannot be created and is counted as skipped.

Existing same-name GPs are reused. Their data types and values are not changed by this setup workflow.

---

## Creation Defaults

These values are applied only when Flow creates the corresponding GP:

| Global Parameter | Creation Default |
| --- | ---: |
| `X-Ext_Sill_Angle` | 15° |
| `X-Architrave Show` | Off |
| `X-Architrave_Depth` | 20 mm |
| `X-Architrave_Width` | 60 mm |
| `X-Ext_Trim_Width` | 20 mm |
| `X-Ext_Sill_Width` | 80 mm |
| `X-Ext_Sill_Height` | 60 mm |
| `X-Ext_Trim_Height` | 60 mm |
| `X-Frame Setback` | 0 mm |
| `X-GlassThickness` | 15 mm |
| `X-Window Head Height` | 2000 mm |
| `Zero Window Sill Height` | 0 mm |
| `X-Exterior Trim Show` | Off |
| `X-Exterior Sill Show` | Off |
| `3D Doors Show` | Off |

!!! note "Existing values are retained"

	If one of these GPs already exists, Flow uses its current project value. The table above does not overwrite an existing GP.

---

## What Flow Does Automatically

Flow performs the setup in one Revit transaction:

1. Filters the selection to Windows-category elements.
2. Finds or creates each required GP.
3. Looks up the matching parameter on each window instance.
4. Checks whether Revit permits the association.
5. Applies compatible associations.
6. Skips missing, incompatible or failed items and continues.

The workflow does not remove an existing GP association before trying the standard mapping. A parameter already controlled by a different GP can therefore be skipped.

---

## Completion Summary

Flow reports:

| Result | Meaning |
| --- | --- |
| **Windows processed** | Selected Existing-phase elements retained in the Windows category. |
| **Global parameters found** | Required GPs already present in the project. |
| **Global parameters created** | Missing GPs successfully created. |
| **Associations applied** | Successful parameter-to-GP association operations. |
| **Skipped** | Missing sample parameters, failed GP creation, missing window parameters, incompatibility or association failures. |

<!-- SCREENSHOT: Existing Window GP Setup completion message showing all five result counts. -->

!!! note "Partial success"

	The workflow can complete with skipped items. Review the summary rather than relying only on the completion message.

---

## Expected Result

For supported Existing-phase windows:

- Required `X-` GPs exist in the current project
- Newly created GPs receive the configured defaults
- Supported window instance parameters are associated
- Existing same-name GP values remain unchanged

Refresh the dashboard and review representative windows after processing.

---

## Cancel the Selection

Press **Esc** while Revit is waiting for the window selection.

No setup request is submitted and the project remains unchanged.

---

## If a Window Is Skipped

1. Confirm that the selected element is a Revit window family instance.
2. Confirm that its created phase is named **Existing**.
3. Check whether the required parameter exists on the instance.
4. Check whether the parameter is compatible with the required GP.
5. Use **Review Associations** to identify an existing conflicting association.
6. Review the completion summary's **Skipped** count.
7. Refresh the dashboard after checking the setup.

---

## Current Limitations

- Only manually selected Existing-phase windows are processed.
- The phase must be named **Existing**.
- The workflow processes instance parameters only.
- Existing GP types and values are not validated against the configured standard.
- Existing conflicting associations are not deliberately replaced.
- Missing or incompatible parameters are counted together as skipped.
- Individual problems do not produce a detailed per-window report.
- Partial success is possible.

---

## Related Help

- [Parameters Manager](index.md)
- [Applying Window Standards](applying-window-standards.md)
- [Applying Door Standards](applying-door-standards.md)
- [Reviewing Associations](reviewing-associations.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

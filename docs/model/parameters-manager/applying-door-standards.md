# Applying Door Standards

Use **Apply Door Standards** to create and associate the standard Flow Global Parameters used by supported door-family instance parameters.

The workflow processes Revit Doors-category elements created in the phase named **New Construction**.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Check that:

- The intended Revit project is active
- The doors were created in **New Construction**
- The door families contain the supported instance parameters
- Existing GP associations have been reviewed where their current setup is uncertain

Use **Review Associations** first if you need to confirm which GPs already control a door.

---

## Start the Workflow

1. Open **Parameters Manager**.
2. Expand **Setup**.
3. Select **Apply Door Standards**.
4. Choose:
   - **Pick Doors**
   - **All New Construction Doors**
   - **Cancel**

<!-- SCREENSHOT: Apply Door Standards chooser showing all three choices. -->

---

## Pick Doors

Use **Pick Doors** when you want to control which doors are processed.

1. Choose **Pick Doors**.
2. Select the required door instances in Revit.
3. Finish the Revit multi-selection.
4. Review the result.
5. Select **Audit → Refresh Dashboard** if required.

Parameters Manager temporarily hides while Revit is waiting for the selection, then returns.

The initial Revit selection is broad, but the processing rules retain only:

- Elements in the **Doors** category
- Doors created in **New Construction**

Other selected elements and doors from other phases are ignored.

---

## All New Construction Doors

Choose **All New Construction Doors** to collect door instances throughout the current project.

The processing rules then retain only doors created in the phase named **New Construction**.

This mode is useful when applying or completing the standard setup across the whole project.

---

## Standard Door Associations

The current rules look for these door instance parameters:

| Door Parameter | Global Parameter |
| --- | --- |
| `Allow Door to Open in 3d` | `3D Doors Show` |
| `Open 3d Panels` | `3D Doors Show` |
| `3D Doors Show` | `3D Doors Show` |
| `Show External Trim` | `Interior Door Trim Show` |
| `Show Internal Trim` | `Interior Door Trim Show` |
| `Interior Door Trim Show` | `Interior Door Trim Show` |
| `Architrave_Depth` | `Architrave_Depth` |
| `Architrave_Width` | `Architrave_Width` |
| `Plan % Open` | `Plan % Open` |
| `3d Panel Opening Angle` | `3d Panel Opening Angle` |

A door family does not need to contain every listed parameter. Missing or incompatible parameters are skipped.

---

## Global Parameters and Creation Defaults

Flow uses an existing exact-name GP where available. If the GP does not exist, Flow attempts to create it using the required data type.

Current creation defaults include:

| Global Parameter | Default when newly created |
| --- | ---: |
| `Architrave_Depth` | 20 mm |
| `Architrave_Width` | 60 mm |
| `Plan % Open` | 40 |

Other newly created values use Revit's initial value unless a rule supplies a default.

Existing same-name GP values are retained and are not reset to these defaults.

---

## What Flow Does Automatically

For each standard rule, Flow:

1. Finds the required GP by exact name.
2. Creates it if it is missing.
3. Finds the matching instance parameter on each qualifying door.
4. Skips missing or read-only parameters.
5. Skips parameters that already have any GP association.
6. Checks whether Revit permits the requested association.
7. Applies each compatible association.

The workflow applies instance associations only. It does not associate door type parameters.

Flow does not replace a parameter's existing GP association, even when it points to a different GP.

!!! note "Partial completion"

	GP creation and association are processed rule by rule. Earlier successful changes remain when another rule or parameter cannot be completed.

---

## Completion Result

Flow displays:

> Associations applied: _number_

This number represents GP associations newly created by the current run.

It does not include:

- Parameters already associated with the correct GP
- Parameters associated with a different GP
- Missing parameters
- Read-only parameters
- Incompatible parameters
- Existing-phase doors
- Non-door elements

<!-- SCREENSHOT: Door GP Setup result showing the Associations applied count. -->

!!! tip "A zero result can be valid"

	A result of zero can mean that the qualifying door parameters were already associated. It can also mean that the selected elements were not qualifying New Construction doors or did not contain compatible parameters.

	Use **Review Associations** on a representative door to distinguish these cases.

---

## Expected Result

After a successful run:

- Required door GPs exist in the project
- Supported instance parameters on qualifying New Construction doors are associated
- Existing GP values and existing associations remain unchanged
- The result reports how many new associations were applied

Refresh the dashboard and inspect representative doors after processing.

---

## Cancel the Workflow

- Choose **Cancel** in the initial chooser, or
- Press **Esc** while Revit is waiting for Pick Doors selection

Cancellation before selection is completed submits no setup request.

---

## If a Door Is Not Affected

1. Confirm that the element is in the Revit **Doors** category.
2. Confirm that its created phase is named **New Construction**.
3. Check whether the family contains the expected instance parameter.
4. Check whether the parameter is read-only.
5. Use **Review Associations** to see whether another GP is already associated.
6. Confirm that the required GP has a compatible Revit data type.
7. Refresh the dashboard after checking the result.

---

## Current Limitations

- Door Standards processes instance parameters only.
- Doors not created in New Construction are ignored.
- Missing, read-only and incompatible parameters are silently skipped.
- Existing GP associations are preserved rather than corrected or replaced.
- Existing GP values are not updated to the creation defaults.
- The completion message reports only newly applied associations, not processed doors or skipped attempts.
- The workflow can partially succeed without a detailed per-door report.

---

## Related Help

- [Parameters Manager](index.md)
- [Applying Window Standards](applying-window-standards.md)
- [Applying Existing Window Standards](applying-existing-window-standards.md)
- [Reviewing Associations](reviewing-associations.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

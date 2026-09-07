# Family Parameters

!!! info "Not currently available"

	General family-parameter inspection and editing is not included in the current Parameters Manager interface.

The current tool works primarily with project-side Opening Global Parameters and the parameters exposed by loaded window and door families inside the active Revit project.

---

## What Parameters Manager Can Do

Current workflows can:

- Discover GP associations on a selected family instance
- Discover associations on that instance's Revit type
- Copy supported instance and type associations to matching target parameters
- Remove selected instance or type associations
- Apply configured GP associations to supported window and door parameters
- Use a matching family parameter's data type when creating some missing project GPs

These operations occur in the active Revit project.

---

## What Parameters Manager Does Not Currently Do

The reviewed interface does not provide general tools to:

- Open external Revit family files (`.rfa`) for parameter editing
- Create or delete family-parameter definitions
- Change a family parameter between instance and type
- Add or edit family formulas
- Change parameter groups or other family-definition settings
- Batch-edit arbitrary family-parameter values across external families

!!! note "Association is not family-authoring"

	Associating a loaded family's parameter with a project Global Parameter does not modify the underlying family-parameter definition in the external `.rfa` file.

---

## Missing or Incompatible Family Parameters

Window and door setup workflows depend on the selected family exposing parameters with the expected names and compatible Revit data types.

When a family lacks a required parameter, Parameters Manager can skip that association. It does not add the missing parameter definition to the family.

Use the applicable setup completion summary to identify missing or incompatible parameter attempts, then review the family separately where necessary.

---

## Type Associations

Parameters Manager can discover, copy and remove associations stored on a loaded family type.

A type association is shared by every project instance using that type. Review the **Scope** column before copying or removing it.

This still changes the type as it exists in the current project; it is not a general external family-file editing workflow.

---

## Future Development

Dedicated family-parameter inspection and editing, including workflows for external family files, may be added in a future release.

Until a corresponding workflow appears in Parameters Manager, this page should be treated as an availability notice rather than instructions for an implemented family editor.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Associations](reviewing-associations.md)
- [Copying GP Setup](copying-gp-setup.md)
- [Removing Associations](removing-associations.md)
- [Applying Window Standards](applying-window-standards.md)
- [Project Parameters](project-parameters.md)
- [Bulk Parameter Editor](bulk-parameter-editor.md)

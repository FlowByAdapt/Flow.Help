# Project Patterns

Use the **Project Patterns** tab to review and manage fill patterns already loaded into the active Revit project.

---

## Open Project Patterns

On the Revit ribbon:

**Flow → Model → Patterns**

Open the **Project Patterns** tab.

Flow reads the current project’s model and drafting fill patterns. Revit’s solid fill is deliberately excluded because it is a system pattern rather than a user-managed hatch definition.

---

## Find a Project Pattern

Use the project search box to filter by pattern name.

Use the type filter to show:

- **All Types**;
- **Drafting**; or
- **Model**.

The results are sorted alphabetically by pattern name.

---

## Review a Project Pattern

Select a project pattern to review its definition and graphical preview.

Pattern Manager identifies:

- the pattern name;
- model or drafting target;
- pattern grids and segments;
- its relationship to a pattern in the shared library; and
- its current classification or match status.

The library comparison can distinguish an exact match from a pattern whose name or geometry differs from the managed library definition.

---

## Available Actions

Depending on where the action is presented, select or right-click a project pattern to access:

- **Edit** — open the definition in Pattern Editor and update the existing project pattern;
- **Duplicate** — open a copy in creation mode using the suffix ` - Copy`;
- **Export** — save the selected definition as an individual PAT file;
- **Create Filled Region** — create a filled region using the selected project pattern;
- **Conform Name** — apply the ADa naming format to the selected pattern; and
- **Conform Project Pattern Names** — review and apply naming changes across eligible project patterns.

---

## Edit a Project Pattern

Editing changes the existing pattern definition in the active project.

1. Select the project pattern.
2. Click **Edit**, or use **Edit** from its context menu.
3. Modify the definition in Pattern Editor.
4. Click **Save**.

Flow updates the existing project pattern and refreshes the project-pattern list.

!!! warning "Review project use before editing"

    A project fill pattern can be referenced by materials, filled-region types and other Revit settings. Editing the pattern changes its appearance everywhere that definition is used.

---

## Duplicate a Project Pattern

Duplicate when the existing definition is a useful starting point but the original pattern must remain unchanged.

The duplicate opens in creation mode as:

`Existing Pattern Name - Copy`

Rename and edit the copy before saving. Flow prevents the new definition from being saved with a project pattern name that already exists.

---

## Standardise Names

For individual or bulk project-pattern naming, see [**Standardising Patterns**](standardising-patterns.md).

---

## Related Help

- [Pattern Manager](index.md)
- [Creating and Editing Patterns](creating-and-editing-patterns.md)
- [Standardising Patterns](standardising-patterns.md)
- [Filled Region Tools](filled-region-tools.md)
- [Troubleshooting](troubleshooting.md)
# Opening Marks

Flow uses a consistent marking system for Windows, Doors and Curtain Walls.

Opening marks are used throughout Openings Manager for auditing, standardisation, guided renumbering and opening-view naming. Establishing reliable marks early helps keep the later documentation workflows consistent.

---

## Standard Opening Marks

Flow uses four primary mark sequences:

| Opening | New | Existing |
| --- | --- | --- |
| Window | `W##` | `Wx##` |
| Curtain Wall | `W##` | `Wx##` |
| Door | `D##` | `Dx##` |

Typical marks are:

```text
W01
W02
Wx01
D01
D02
Dx01
```

Windows and Curtain Walls share the **W / Wx** numbering group.

Doors use the separate **D / Dx** numbering group.

---

## New Openings

New Windows and Curtain Walls use:

```text
W##
```

New Doors use:

```text
D##
```

For example:

```text
W01
W02
W03

D01
D02
D03
```

The standard sequence uses two digits, so the initial marks run `W01`, `W02`, `W03` rather than `W1`, `W2`, `W3`.

---

## Existing Openings

Existing Windows and Curtain Walls use:

```text
Wx##
```

Existing Doors use:

```text
Dx##
```

For example:

```text
Wx01
Wx02

Dx01
Dx02
```

The `x` distinguishes the Existing sequence from the New sequence.

---

## Curtain Walls Share the Window Sequence

Curtain Walls do not have a separate mark series.

A project might therefore contain:

```text
W01  Window
W02  Window
W03  Curtain Wall
W04  Window
```

Flow checks Windows and Curtain Walls together when looking for mark conflicts.

This means a Window and a Curtain Wall cannot both use `W03` without creating a duplicate within the shared numbering group.

---

## Duplicate and Conflicting Marks

The Opening Register audits opening marks for conflicts.

Windows and Curtain Walls are checked together because they share the W/Wx group. Doors are checked within the D/Dx group.

When Flow finds a duplicate or otherwise invalid mark, the opening can be reported as requiring attention in the register.

➡️ [**Reviewing Openings**](reviewing-openings.md)

<!-- SCREENSHOT: Opening Register showing a clear duplicate or non-standard mark example. -->

---

## Non-standard Marks

A mark can be non-standard when it does not match the format expected for the opening category and phase, or when it conflicts with another opening in the same numbering group.

For example, a New Window is expected to use the `W##` convention, while an Existing Window is expected to use `Wx##`.

Use **Standardise** when Flow should resolve invalid or conflicting marks automatically.

➡️ [**Standardising Openings**](standardising-openings.md)

---

## Demolished Openings

Demolished openings remain part of the Opening Register, but the marking workflows do not all treat them in the same way.

### Standardise

When **Standardise** processes a Demolished opening, it uses the Existing-style mark series:

- Window / Curtain Wall → `Wx##`
- Door → `Dx##`

### Renumber

The interactive **Renumber** workflow does **not** accept Demolished openings.

!!! important "Choose the workflow deliberately"

    If the project contains Demolished openings, do not assume Standardise and Renumber will treat them identically.

---

## Standardise or Renumber?

The two commands solve different marking problems.

### Use Standardise when

- marks need to comply with the Flow format
- duplicate or conflicting marks need to be resolved
- valid unique marks should be retained where possible
- you do not need to manually control the complete numbering order
- related opening-view names should be synchronised

Standardise does **not** simply renumber every opening from the beginning. Valid unique marks are preserved where possible, while openings requiring correction are assigned an available number.

### Use Renumber when

- the numbering order matters
- you want to select openings directly in the Revit model
- you want to establish a deliberate W/Wx/D/Dx sequence
- you want to work through the project level by level

Renumber is an interactive workflow. The order in which openings are selected determines the proposed numbering sequence.

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## Marks and Opening Views

Opening marks are also used by the opening-view workflows.

For Windows and Curtain Walls, the opening mark provides the basis for the elevation view name.

Door elevation documentation is type-based and uses the Door type's **Type Mark** with the `-D` view suffix.

Because marks and view names are related, opening marks should normally be resolved before generating opening views.

!!! tip "Resolve marks before generating views"

    Standardise or deliberately renumber the openings before starting the view-generation workflow.

    **Generate Views** also checks its selected scope for non-standard openings and will stop to offer Standardise when required.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## Standardise Also Synchronises View Names

Standardising opening marks includes a view-name synchronisation step.

This means Standardise can update existing opening-view names so they remain aligned with the current opening marks.

This is one reason to use Standardise rather than manually editing a collection of marks when opening documentation already exists.

For broader correction of existing opening views, use **Conform Views**.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

---

## Recommended Marking Workflow

For a project being prepared for opening documentation:

1. Review the Opening Register for unexpected or duplicate marks.
2. Decide whether the existing numbering order should be preserved.
3. Use **Standardise** if the main requirement is compliance and conflict resolution.
4. Use **Renumber** if a deliberate model-selection order is required.
5. Review the register again before generating opening views.

This keeps the marking decision separate from the later documentation workflow.

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Generating Opening Views**](generating-opening-views.md)

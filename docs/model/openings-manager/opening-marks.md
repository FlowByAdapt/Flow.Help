# Opening Marks

Flow uses a consistent marking system for windows, doors and curtain walls.

These marks are used throughout the Openings Manager workflows, including opening views, guided renumbering and documentation checks.

---

## Standard Opening Marks

Flow recognises four primary mark sequences:

| Opening | New | Existing |
| --- | --- | --- |
| Window | `W##` | `Wx##` |
| Curtain Wall | `W##` | `Wx##` |
| Door | `D##` | `Dx##` |

Examples include:

```text
W01
W02
Wx01
D01
D02
Dx01
```

Windows and curtain walls share the same `W` / `Wx` numbering sequence.

Doors use their own `D` / `Dx` sequence.

---

## New Openings

New windows and curtain walls use:

```text
W##
```

New doors use:

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

---

## Existing Openings

Existing windows and curtain walls use:

```text
Wx##
```

Existing doors use:

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

The `x` distinguishes Existing openings from the New opening sequence.

---

## Curtain Wall Marks

Curtain walls participate in the Window numbering sequence.

For example, a project could contain:

```text
W01  Window
W02  Window
W03  Curtain Wall
W04  Window
```

Flow does not maintain a separate curtain wall numbering sequence.

---

## Duplicate Marks

The Openings Manager audit checks for duplicate marks.

Windows and curtain walls are checked together because they share the same mark sequence.

Doors are checked within the Door sequence.

Duplicate or inconsistent marks can be identified through the Openings Manager register.

➡️ [**Reviewing Openings**](reviewing-openings.md)

---

## Non-standard Marks

An opening may be identified as non-standard when its mark does not follow the expected Flow format for its category and phase.

Use **Standardise** when you want Flow to correct non-standard marks automatically.

➡️ [**Standardising Openings**](standardising-openings.md)

---

## Renumber Openings in a Specific Order

Use **Guided Renumber** when the required numbering order matters.

Rather than automatically correcting the existing marks, Guided Renumber lets you select openings from the Revit model in the order in which they should be numbered.

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## Marks and Opening Views

Opening marks are also used by the opening-view workflows.

Window and curtain wall elevation names are based on their opening marks.

Door documentation uses a separate type-based view naming system.

Because of this, opening marks should normally be resolved before generating opening views.

!!! tip "Resolve marks before documentation"

    Standardise or renumber the project openings before generating opening views.

    This reduces the need to rename or reconform views later.

---

## Which Tool Should I Use?

Use **Standardise** when:

- marks need to be brought into the standard Flow format
- you do not need to manually control the complete numbering sequence
- opening view names also need to be synchronised

Use **Guided Renumber** when:

- the numbering order matters
- you want to select openings directly from the model
- you are working through the project level by level
- you want to establish a deliberate W/Wx/D/Dx sequence

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Opening Views**](opening-views.md)
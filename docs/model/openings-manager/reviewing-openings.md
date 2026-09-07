# Reviewing Openings

The **Opening Register** gives you a project-wide overview of Windows, Doors and Curtain Walls discovered by Openings Manager.

Use it to review opening marks, phases, Global Parameter status and other opening issues before running the marking, parameter or documentation workflows.

---

## Open the Opening Register

On the Revit ribbon:

**ADAPT → Model → Openings**

When Openings Manager first opens, Flow scans the current Revit project and discovers:

- Windows
- Doors
- Curtain Walls

The results are displayed in the **Opening Register**.

The counters at the top of the Manager show the number of **Windows**, **Doors**, **Curtain Walls** and **Total** openings found.

<!-- SCREENSHOT: Full Opening Register showing the four counters, filters and a useful mixture of Windows, Doors and Curtain Walls. -->

---

## Review Opening Information

Each row represents an opening discovered in the project.

The visible register columns include:

- **Category**
- **Mark**
- **Type**
- **Level**
- **Phase**
- **GP**
- **Head Height GP**
- **Status**

The checkbox at the left of each row is used to build a working selection for commands that support register scope.

Clicking the row itself selects that opening in Revit.

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

---

## Understand Opening Status

The **Status** column summarises issues found during the opening audit.

Flow checks more than whether an opening exists. Depending on the opening and its current project state, the audit can consider:

- mark format
- duplicate or conflicting marks
- expected Global Parameter associations
- opening-view naming consistency
- Window head-height override status

An opening can therefore require attention even when its mark appears correct.

For example, a Window whose opening view no longer matches its mark can be reported as non-standard until the opening and view are brought back into alignment.

!!! tip "Use the register as a QA check"

    Review unexpected statuses before generating or updating opening documentation. This helps distinguish a marking issue from a parameter or view-related issue.

---

## Search the Register

Use **Search** to narrow the register using opening information.

Searching is particularly useful when you know the mark, type or other identifying information for the opening you want to review.

The register updates as the search changes.

!!! tip "Search by mark"

    If you already know the opening mark, entering it in **Search** is usually the quickest way to isolate the record.

---

## Filter by Category

Use **Category** to review:

- Windows
- Doors
- Curtain Walls

Category filtering is useful before building a working selection or running a category-specific workflow such as tagging.

---

## Filter by Level

Use **Level** to isolate openings associated with a particular project level.

This is useful when reviewing or documenting the project one storey at a time.

---

## Filter by Phase

Use **Phase** to isolate openings by their project phase.

The register distinguishes opening phase states including:

- New
- Existing
- Demolished

Phase affects several downstream workflows and marking conventions.

For standard opening marks:

| Phase | Window / Curtain Wall | Door |
| --- | --- | --- |
| New | `W##` | `D##` |
| Existing | `Wx##` | `Dx##` |

!!! note "Demolished openings"

    Demolished openings remain visible for review.

    Some modifying workflows treat or exclude Demolished openings differently. For example, Guided Renumber does not accept Demolished openings.

➡️ [**Opening Marks**](opening-marks.md)

➡️ [**Guided Renumbering**](guided-renumbering.md)

---

## Filter by Global Parameter Status

Use **GP Status** to review the state of opening-related Global Parameter associations.

The available filter choices include:

- **Complete**
- **Missing**
- **Not Configured**
- **Not Required**

The register can also display an **Override** state for applicable Window Global Parameter conditions, although Override is not currently a separate GP Status filter choice.

Use the GP information together with **Head Height GP** when investigating Window parameter setup.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

➡️ [**Head Height Overrides**](head-height-overrides.md)

---

## Tag Type

The **Tag Type** control is used by the opening-tagging workflow.

Available tag types depend on the opening category being worked with:

- Window Tags for Windows
- Door Tags for Doors
- Wall Tags for Curtain Walls

A tagging scope must contain only one opening category.

➡️ [**Tagging Openings**](tagging-openings.md)

---

## Combine Search and Filters

Search and filters can be combined to work through a large register in smaller groups.

For example, you might review:

**Windows → Ground Floor → New → Missing GP**

and then use Search to isolate a particular opening or type.

Once the required records are visible, use **Select Filtered** if you want all of those filtered records to become the checked working selection.

!!! important "Changing filters clears checked selections"

    Changing **Category**, **Level**, **Phase** or **GP Status** clears the current checked selection.

    Set the required filters first, then check individual rows or use **Select Filtered**.

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

---

## Refresh the Register

Use **Refresh** when the project has changed and you want Openings Manager to rebuild its current audit.

This is useful after:

- editing openings directly in Revit
- changing opening types or parameters
- changing Global Parameter associations
- creating or updating opening views
- completing another opening workflow

If changes are made directly in Revit while Openings Manager remains open, the register does not automatically represent every external change until it is refreshed.

!!! warning "Refresh is not read-only"

    **Refresh can modify the Revit model.**

    Before Flow reruns opening discovery and rebuilds the register, it applies the **Zero Window Sill Height** rule.

    This ensures Window **Sill Height** is associated with the **Zero Window Sill Height** Global Parameter where required.

Use Refresh as an opening maintenance operation rather than treating it as a purely visual reload.

---

## What the Initial Scan Does

Opening Openings Manager performs discovery and audit so that the current project state can be displayed.

The initial scan itself should be distinguished from **Refresh**:

- **Opening the Manager** discovers and audits the openings.
- **Refresh** applies the Zero Window Sill Height rule and then reruns the discovery/audit.

This distinction is important when reviewing a project for the first time.

---

## What to Review First

For a project that has not previously been processed through Openings Manager, start by checking:

1. **Counts** — do the Window, Door and Curtain Wall totals look reasonable?
2. **Category and Level** — are openings being classified where you expect?
3. **Phase** — are New, Existing and Demolished openings correctly phased?
4. **Mark** — look for unexpected, duplicate or non-standard marks.
5. **GP / Head Height GP** — identify parameter setup requiring attention.
6. **Status** — investigate records Flow has identified as inconsistent.

Once the register looks understood, move on to standardisation or the relevant opening workflow rather than correcting everything blindly.

<!-- SCREENSHOT: Register filtered to a useful QA example, such as New Windows with a mixture of clean and attention-required statuses. -->

---

## Next Steps

- [**Openings Manager**](index.md)
- [**Selecting and Locating Openings**](selecting-and-locating-openings.md)
- [**Opening Marks**](opening-marks.md)
- [**Standardising Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Opening Global Parameters**](opening-global-parameters.md)
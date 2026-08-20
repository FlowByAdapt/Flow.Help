# Openings Manager

The **Openings Manager** provides a central workspace for reviewing,
standardising and documenting project openings.

It brings together windows, doors and curtain walls in a searchable
register and provides tools for managing marks, opening views, tags,
dimensions, door heights and opening-related Global Parameters.

------------------------------------------------------------------------

## Open Openings Manager

On the Revit ribbon:

**Flow → Openings → Manager**

The Openings Manager scans the current project and displays the
discovered openings in the register.

------------------------------------------------------------------------

## Review Openings

Use the register to review windows, doors and curtain walls together
with their current project and documentation status.

You can search and filter the register to isolate the openings that need
attention.

➡️ [**Reviewing Openings**](reviewing-openings.md)

------------------------------------------------------------------------

## Select and Locate Openings

Use the register and Revit model together to build working selections
and locate individual openings.

➡️ [**Selecting and Locating
Openings**](selecting-and-locating-openings.md)

------------------------------------------------------------------------

## Opening Marks

Flow uses standard mark sequences for New and Existing openings:

  Opening        New     Existing
  -------------- ------- ----------
  Window         `W##`   `Wx##`
  Curtain Wall   `W##`   `Wx##`
  Door           `D##`   `Dx##`

Windows and curtain walls share the same numbering sequence.

➡️ [**Opening Marks**](opening-marks.md)

### Standardise Openings

Use **Standardise** to correct non-standard opening marks and
synchronise associated opening view names.

➡️ [**Standardising Openings**](standardising-openings.md)

### Guided Renumber

Use **Guided Renumber** when you want to control the numbering sequence
by selecting openings directly from the Revit model.

➡️ [**Guided Renumbering**](guided-renumbering.md)

------------------------------------------------------------------------

## Tag Openings

Use the tagging workflow to add the appropriate Window, Door or Curtain
Wall tags in a Floor Plan.

➡️ [**Tagging Openings**](tagging-openings.md)

------------------------------------------------------------------------

## Opening Views

Openings Manager includes a complete workflow for producing and
maintaining opening elevations.

➡️ [**Opening Views**](opening-views.md)

### Generate Opening Views

Create standard elevations for New windows and New door types.

➡️ [**Generating Opening Views**](generating-opening-views.md)

### Curtain Wall Views

Create curtain wall elevations using the dedicated interactive placement
workflow.

➡️ [**Generating Opening Views**](generating-opening-views.md)

### Conform Opening Views

Repair existing opening elevations and restore the expected Flow view
standards.

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

### Dimension Window Views

Create or regenerate the standard dimensions on component Window
elevations.

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

### Place Views on Sheets

Arrange Window and Door elevations on the appropriate opening schedule
sheets.

➡️ [**Placing Opening Views on Sheets**](placing-views-on-sheets.md)

------------------------------------------------------------------------

## Door Heights

Use **Door Heights** to review door heights by project level and update
applicable New doors.

Flow creates or reuses appropriately sized door types rather than
modifying shared types indiscriminately.

➡️ [**Door Heights**](door-heights.md)

------------------------------------------------------------------------

## Opening Global Parameters

Flow uses Global Parameters to maintain several opening standards,
including:

-   Window sill height
-   Window head height
-   Door display controls
-   Door trim controls
-   Architrave dimensions
-   Door opening settings

Openings Manager audits these associations and identifies openings that
require attention.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

### Window Head Height Overrides

Use controlled Global Parameter overrides when individual windows or
groups of windows need a head height that differs from the project
standard.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

------------------------------------------------------------------------

## Recommended Workflow

A typical opening-documentation workflow is:

1.  Open **Openings Manager**.
2.  Review the register.
3.  Resolve non-standard or incorrect opening marks.
4.  Use Guided Renumber where the numbering order needs to be
    controlled.
5.  Review opening Global Parameter status.
6.  Adjust Door Heights where required.
7.  Generate Window and Door views.
8.  Generate Curtain Wall views where required.
9.  Conform existing opening views.
10. Tag openings.
11. Dimension Window views.
12. Place opening views on sheets.
13. Refresh the register and review the completed status.

!!! tip "Use the register as your starting point"

    Openings Manager is designed to show the current state of the project before you run the individual opening workflows.

    Refresh the register after significant changes so that the displayed status reflects the current Revit model.

------------------------------------------------------------------------

## Troubleshooting

If an opening cannot be found, a mark cannot be standardised, a view
cannot be generated, or another Openings Manager workflow is not
behaving as expected:

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)
# Reviewing Openings

The Openings Manager register provides an overview of windows, doors and curtain walls in the current Revit project.

Use the register to identify openings that require attention before running the marking, Global Parameter or documentation workflows.

---

## Open the Register

Open:

**Flow → Openings → Manager**

Flow scans the current project and displays the discovered openings.

The register includes:

- windows
- doors
- curtain walls

---

## Review Opening Information

Each row represents an opening discovered in the project.

Depending on the opening type and current project state, the register can show information including:

- opening mark
- category
- family and type
- level
- phase
- Global Parameter status
- opening view
- sheet placement
- issue or status information

Use this information to identify openings that are incomplete or inconsistent with the Flow opening standards.

---

## Search the Register

Use the **Search** box to find openings using information already displayed or associated with the opening.

Search can match information including:

- mark
- family
- type
- level
- category
- opening view
- sheet
- issue information

The register updates as the search changes.

!!! tip "Search by mark"

    If you already know the opening you want to review, searching for its mark is usually the quickest way to isolate it.

---

## Filter by Category

Use the **Category** filter to narrow the register to a particular type of opening.

This is useful when you want to work only with:

- Windows
- Doors
- Curtain Walls

---

## Filter by Level

Use the **Level** filter to review openings associated with a particular project level.

This can be useful when checking or documenting one storey at a time.

---

## Filter by Phase

Use the **Phase** filter to review openings according to their project status.

Flow distinguishes:

- New
- Existing
- Demolished

Phase is important because several opening workflows behave differently for New and Existing openings.

For example, standard marks use different prefixes:

| Phase | Window / Curtain Wall | Door |
| --- | --- | --- |
| New | `W##` | `D##` |
| Existing | `Wx##` | `Dx##` |

---

## Filter by Global Parameter Status

Use the **GP Status** filter to review the state of opening-related Global Parameter associations.

The register can distinguish statuses such as:

- Complete
- Missing
- Not Configured
- Not Required

Use this filter to isolate openings that may require Global Parameter setup or review.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

---

## Show Non-standard Openings

Use the **Non-standard only** option to reduce the register to openings that Flow has identified as requiring attention.

This is particularly useful before:

- standardising marks
- generating opening views
- completing opening documentation

➡️ [**Standardising Openings**](standardising-openings.md)

---

## Combine Search and Filters

Search and filters can be used together.

For example, you can narrow the register to:

**Windows → Ground Floor → New → Missing GP**

and then search for a particular mark or family.

This makes it easier to work through a large project in smaller groups.

---

## Select Filtered Openings

Use **Select Filtered** when you want the currently filtered register results to become the working selection.

This is useful before running a tool against a particular group of openings.

The available scope options depend on the command being run, but many Openings Manager tools can work with the checked or filtered register results.

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

---

## Refresh the Register

Use **Refresh** after making changes to the project.

Refresh performs a new opening discovery and audit so that the register reflects the current state of the Revit model.

This is useful after operations such as:

- standardising marks
- changing opening parameters
- creating or conforming views
- modifying Global Parameter associations
- changing opening types

!!! info "Refresh after external changes"

    If you change openings directly in Revit while Openings Manager remains open, the register may still show the previous audited state.

    Use **Refresh** to run the audit again.

---

## What Flow Checks

The Openings Manager audit checks more than whether an element exists.

Depending on the opening, Flow can evaluate:

- mark format
- duplicate marks
- expected Global Parameter associations
- opening view availability
- consistency between the opening mark and its view name
- window head-height override status

These checks provide the status information shown in the register. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

---

## Next Steps

After reviewing the register:

- [**Select and Locate Openings**](selecting-and-locating-openings.md)
- [**Standardise Openings**](standardising-openings.md)
- [**Guided Renumbering**](guided-renumbering.md)
- [**Opening Global Parameters**](opening-global-parameters.md)
- [**Opening Views**](opening-views.md)
# Opening Global Parameters

Openings Manager audits the Revit Global Parameter associations used by the Flow opening standards.

Some opening workflows also create or apply required associations automatically. For broader Global Parameter management, Openings Manager launches the dedicated **Parameters Manager**.

---

## Global Parameter Status

The Opening Register includes a **GP** status for each opening.

The register can report states including:

- **Complete**
- **Missing**
- **Not Configured**
- **Not Required**
- **Override**

The **GP Status** filter provides:

- All
- Complete
- Missing
- Not Configured
- Not Required

!!! note "Override is visible but not a dedicated filter"

    A Window can display **Override** in the GP column, but the current GP Status filter does not provide a separate Override option.

➡️ [**Reviewing Openings**](reviewing-openings.md)

---

## Windows

The current Openings Manager implementation includes a standard zero-sill rule for Windows.

Flow associates the Window instance parameter:

```text
Sill Height
```

with the project Global Parameter:

```text
Zero Window Sill Height
```

The Global Parameter is a Length parameter.

---

## Zero Window Sill Height

The zero-sill association is applied automatically by specific Openings Manager workflows.

### Refresh

Clicking **Refresh** does more than rebuild the Opening Register.

Before discovery is rerun, Flow applies the **Zero Window Sill Height** rule to project Windows.

!!! important "Refresh modifies the model"

    **Refresh is not a read-only register refresh.**

    It ensures the Window `Sill Height` → `Zero Window Sill Height` association before rebuilding the opening audit.

This is different from initially opening Openings Manager, where the register is audited without first running the Refresh operation.

### Generate Views

**Generate Views** also ensures the zero-sill Global Parameter setup before creating Window and Door elevations.

➡️ [**Generating Opening Views**](generating-opening-views.md)

---

## Window Head Height

Window head-height associations are also audited by Openings Manager.

The register includes a separate **Head Height GP** column so the head-height state can be reviewed independently from the general GP status.

Project-standard head-height associations and exceptions are managed through the Flow Global Parameter workflows rather than by manually breaking associations in the Opening Register.

For controlled exceptions:

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

---

## New Door Global Parameter Rules

The opening documentation workflow also applies the configured standard Global Parameter rules used by applicable **New Doors**.

These rules are applied as part of **Generate Views** before Door elevations are created.

Existing and Demolished Doors are not treated as New-Door standardisation targets by that workflow.

The exact supported Door associations are defined by the current Flow parameter configuration and the parameters available in the Door family.

!!! note

    Do not assume that every Door family exposes every Flow-controlled parameter.

    The available family parameters determine which configured associations can actually be applied.

---

## Existing Associations

Opening Global Parameter workflows are intended to establish and audit controlled project associations.

Where an opening already has an association, its current state can affect how Flow reports or processes that opening.

This is particularly important for Window head-height overrides, where an alternative association can be intentional rather than simply missing.

Use the Opening Register to review the resulting status rather than assuming that every non-default association should be replaced.

---

## Parameters Manager

Click **Parameters Manager** in Openings Manager when you need broader control of project Global Parameters and associations.

The current workflow:

1. minimises Openings Manager
2. opens the dedicated Parameters Manager
3. restores Openings Manager when Parameters Manager closes

Parameters Manager is the appropriate place for wider Global Parameter management beyond the opening-specific automatic rules.

<!-- SCREENSHOT: Parameters Manager opened from Openings Manager, showing the project Global Parameter management interface. -->

---

## Head Height Overrides

A Window may need a controlled head-height exception without abandoning the Global Parameter system.

Use the dedicated head-height override workflow for these cases.

This allows Flow to distinguish an intentional override from an incomplete standard setup.

➡️ [**Window Head Height Overrides**](head-height-overrides.md)

---

## Recommended Workflow

When reviewing opening Global Parameters:

1. Check the **GP** and **Head Height GP** columns in the Opening Register.
2. Use the **GP Status** filter to isolate Complete, Missing, Not Configured or Not Required records.
3. Use **Refresh** when the project Window zero-sill rule needs to be reapplied and the register rebuilt.
4. Use **Parameters Manager** for wider project Global Parameter management.
5. Use the dedicated head-height override tools for intentional Window exceptions.
6. Review the Opening Register again after changes.

!!! warning "Be aware of automatic model changes"

    **Refresh** applies the zero-sill Window association.

    **Generate Views** also performs supporting Global Parameter setup before creating opening elevations.

---

## Related Help

- [**Reviewing Openings**](reviewing-openings.md)
- [**Generating Opening Views**](generating-opening-views.md)
- [**Door Heights**](door-heights.md)
- [**Window Head Height Overrides**](head-height-overrides.md)
- [**Openings Manager Troubleshooting**](troubleshooting.md)

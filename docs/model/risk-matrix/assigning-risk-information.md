# Assigning Risk Information

Use **Project Risk Values** and the **Cladding** tab to define the
information written to walls when Risk Faces are processed.

The current tool assigns this information during **Pick Walls**. It does
not yet provide the planned per-face scoring and confirmation grid.

------------------------------------------------------------------------

## Project Risk Values

Risk Matrix uses six E2 Risk Matrix factors:

-   **Wind Zone**
-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

Wind Zone is project-wide and read from Revit Project Information. The
remaining five values are selected in Risk Matrix for the walls being
processed.

------------------------------------------------------------------------

## Wind Zone

Wind Zone is read from:

**Revit Project Information → Wind Zone**

It is not independently editable in Risk Matrix.

Recognised standard values are:

-   **Low**
-   **Medium**
-   **High**
-   **Very High**
-   **Extra High**

Use **Refresh** beside Wind Zone if Project Information has changed
while Risk Matrix is already open.

!!! info "One project source of truth"

    Risk Matrix consumes the persistent Project Information value rather than maintaining a separate Wind Zone selection.

### Wind Zone Is Not Set

If the project Wind Zone cannot be resolved, Risk Matrix shows an
unresolved state and **Pick Walls** is blocked.

Set the required value in Revit Project Information, return to Risk
Matrix, and click **Refresh**.

### SED

If Wind Zone is **SED**, Risk Matrix identifies the project as requiring
**Specific Engineering Design** and blocks the standard E2 Risk Matrix
processing workflow.

!!! warning "SED is not another standard Risk Matrix value"

    SED indicates that the project is outside the standard Wind Zone route used by this workflow.

------------------------------------------------------------------------

## Other Project Risk Values

Before each **Pick Walls** operation, select the values applicable to
the walls you are about to process.

### Number of Storeys

Choose the applicable storey option from the Risk Matrix key schedule.

### Roof / Wall

Choose the applicable roof-to-wall relationship.

### Eave Width

Choose the applicable eave-width category.

### Envelope

Choose the applicable envelope-complexity category.

### Deck

Choose the applicable deck category.

Use the guidance button beside a value when you need to review its Risk
Matrix guidance.

!!! note "Review before processing"

    The current selections are applied during wall processing. Check them before selecting each set of walls that requires a different assessment condition.

------------------------------------------------------------------------

## When Values Are Applied

When you click **Pick Walls**, Risk Matrix takes a snapshot of the
current settings.

Those values are written to newly processed walls when the selection is
completed and the wall groups are processed.

Already processed walls are protected from having their existing risk
values silently replaced if they are selected again.

------------------------------------------------------------------------

## Cladding Information

Cladding information is managed on the **Cladding** tab and is
project-wide.

Risk Matrix discovers applicable exterior wall types and uses the
configured cladding rules to suggest a cladding description. Review this
setup when first preparing the project and whenever the exterior
wall-type strategy changes.

<!-- SCREENSHOT: Complete Cladding tab with realistic wall types and several cladding groups. -->

### Project Cladding Legend

The project legend contains up to four coordinated cladding groups:

-   **Cladding 1**
-   **Cladding 2**
-   **Cladding 3**
-   **Cladding 4**

Unused slots are shown as **N/A**.

### Wall Types to Include

Use **Wall Types to Include** to review the discovered exterior wall
types.

For each wall type you can:

-   include or exclude it from the project cladding configuration;
-   review or edit its cladding description; and
-   review or change its **Cladding 1--4** group.

An excluded wall type is omitted from the cladding assignment passed
into Risk Face processing.

### Automatic and Manual Grouping

Wall types with the same cladding description are coordinated into the
same project cladding group.

If a description is changed to match an existing description, the wall
type can use that existing group. New unique descriptions use an
available group where possible.

Groups can also be adjusted manually. The setup prevents one group from
representing conflicting cladding descriptions.

!!! warning "Maximum four cladding groups"

    The current workflow supports a maximum of four coordinated project cladding descriptions.

### Wall Type Cladding Mapping

Use **Wall Type Cladding Mapping** to review the resulting relationship
between Revit wall types and project cladding descriptions.

The mapping is used automatically during **Pick Walls**. You do not
select a cladding value separately for each Risk Face.

### Project Cladding Health

Use **Project Cladding Health** to identify configuration that still
requires attention before relying on the coordinated cladding
information.

### Saving the Project Cladding Setup

Changes to included wall types, descriptions and cladding groups are
stored in the Revit project and restored when Risk Matrix is reopened.

!!! info "Project-wide configuration"

    Cladding setup belongs to the project rather than to an individual Risk View or Risk Face.

A full **Reset Risk Matrix** clears this saved cladding configuration. A
selected-face reset does not.

------------------------------------------------------------------------

## Automated Risk Scoring

The current version does **not** calculate and present a completed E2
score for each Risk Face.

Automated face-specific suggestion, confirmation and scoring is planned
as a later development stage.

------------------------------------------------------------------------

## Related Help

-   [**Risk Matrix**](index.md)
-   [**Identifying Risk Faces**](identifying-risk-faces.md)
-   [**Reviewing Risk Results**](reviewing-risk-results.md)
-   [**Risk Documentation**](risk-documentation.md)
-   [**Troubleshooting**](troubleshooting.md)

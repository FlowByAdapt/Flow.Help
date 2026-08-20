# Assigning Risk Information

Use **Project Risk Values** in Risk Matrix to define the information
written to walls when Risk Faces are processed.

The current tool assigns these values during **Pick Walls**. It does not
yet provide the planned per-face scoring and confirmation grid.

------------------------------------------------------------------------

## Project Risk Values

The Risk Matrix tab currently provides:

-   **Wind Zone**
-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

Review these values before clicking **Pick Walls**.

The selected values are applied to the walls processed in that
operation.

------------------------------------------------------------------------

## Wind Zone

**Wind Zone** is different from the other Project Risk Values.

It is read from:

**Revit Project Information → Wind Zone**

Risk Matrix does not provide a separate editable Wind Zone selector.

For a standard E2 Risk Matrix workflow, the recognised values are:

-   **Low**
-   **Medium**
-   **High**
-   **Very High**
-   **Extra High**

A valid value is shown as the current project Wind Zone.

Use **Refresh** beside the Wind Zone if Project Information has been
changed while Risk Matrix is already open.

!!! info "One project source of truth"

    Wind Zone is maintained as project information and consumed by Risk Matrix.

    This avoids maintaining a separate Wind Zone value inside each workflow.

------------------------------------------------------------------------

## Wind Zone Is Not Set

If Project Information does not contain a Wind Zone, Risk Matrix
displays:

**Not Set**

and warns that the project Wind Zone has not been set.

Risk Face processing is blocked until a recognised Wind Zone is
available.

Set the value in Revit Project Information, then use **Refresh** in Risk
Matrix.

------------------------------------------------------------------------

## SED

If the project Wind Zone is:

**SED**

Risk Matrix identifies the project as requiring **Specific Engineering
Design**.

The standard E2 Risk Matrix workflow is treated as not applicable and
Risk Face processing is blocked.

!!! warning "SED is not another E2 Risk Matrix score"

    SED indicates that the project is outside the standard Wind Zone route used by this Risk Matrix workflow.

------------------------------------------------------------------------

## Other Project Risk Values

Select the required values for:

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

Use the guidance button beside a value when you need to review the
corresponding Risk Matrix guidance.

------------------------------------------------------------------------

## When Values Are Applied

The values currently shown in **Project Risk Values** are used when you
click:

**Pick Walls**

Risk Matrix writes the corresponding Risk Matrix parameters to the
processed walls while assigning their Risk Face information.

This means you can change the applicable selections before processing
another group of walls.

!!! note "Review the selections before processing"

    The current Risk Matrix values are applied during wall processing.

    Check the values before selecting each set of walls that requires a different assessment condition.

------------------------------------------------------------------------

## Cladding Information

Cladding information is managed separately on the **Cladding** tab.

Processed walls are normalised into up to four project cladding slots:

-   **Cladding 1**
-   **Cladding 2**
-   **Cladding 3**
-   **Cladding 4**

Unused project slots are shown as **N/A**.

The **Wall Type Cladding Mapping** and **Project Cladding Legend** help
keep the cladding descriptions coordinated across processed Risk Faces.

------------------------------------------------------------------------

## Automated Risk Scoring

The current version does **not** calculate and present the completed E2
risk score for each Risk Face.

Automated face-specific suggestion, confirmation and scoring is planned
as a later Risk Matrix development stage.

The current workflow focuses on creating the coordinated Risk Faces and
storing the information required to support that future assessment
workflow.

------------------------------------------------------------------------

## Related Help

-   [Risk Matrix](index.md)
-   [Identifying Risk Faces](identifying-risk-faces.md)
-   [Reviewing Risk Results](reviewing-risk-results.md)
-   [Risk Documentation](risk-documentation.md)
-   [Troubleshooting](troubleshooting.md)
# Risk Matrix

The **Risk Matrix** supports the preparation of external moisture risk
assessment information in Revit.

Use it to identify and number exterior Risk Faces, apply coordinated
colours and tags, manage project cladding information, and assign the
current Risk Matrix values to processed walls.

!!! info "Current assessment scope"

    Risk Matrix currently prepares and coordinates the model information used by the risk assessment workflow.

    It does **not** currently calculate a completed E2 risk score for each Risk Face or provide the planned face-by-face assessment/results grid.

------------------------------------------------------------------------

## Open Risk Matrix

On the Revit ribbon:

**Flow → Model → Risk**

Risk Matrix opens as a modeless window so you can continue working in
Revit while the tool remains open.

When opened, Flow attempts to activate the default Risk View:

**RISK-01-Elevation**

If Risk Matrix is already open, launching it again activates the
existing window rather than opening another copy.

<!-- SCREENSHOT: Risk Matrix immediately after opening beside RISK-01-Elevation.
Show the complete Risk Matrix tab, Current Risk View, Project Risk Values and main actions. -->

------------------------------------------------------------------------

## Before You Start

Risk Matrix is designed to work with:

-   Risk Views whose names begin with **RISK-**;
-   exterior wall types beginning with **ADa_E\_**;
-   the Risk Matrix parameters and key schedules configured in the
    project; and
-   the project's cladding setup.

The project **Wind Zone** is read from **Revit Project Information →
Wind Zone**. It is not independently selected in Risk Matrix.

For the standard workflow, Wind Zone must resolve to:

-   **Low**
-   **Medium**
-   **High**
-   **Very High**
-   **Extra High**

If Wind Zone is missing or unrecognised, **Pick Walls** is blocked. If
it is **SED**, the standard E2 Risk Matrix workflow is treated as not
applicable.

------------------------------------------------------------------------

## First-Time Workflow

### 1. Open Risk Matrix

Open **Flow → Model → Risk**.

Flow attempts to activate **RISK-01-Elevation** automatically. Use
**Previous View** and **Next View** to move through the available Risk
Views.

### 2. Confirm the Project Wind Zone

Check the Wind Zone displayed in **Project Risk Values**.

If Project Information has been changed while Risk Matrix is open, use
**Refresh** to read the current project value again.

➡️ See [**Assigning Risk Information**](assigning-risk-information.md)

### 3. Review the Other Risk Values

Before processing walls, confirm:

-   **Number of Storeys**
-   **Roof / Wall**
-   **Eave Width**
-   **Envelope**
-   **Deck**

These are the values that will be written to newly processed walls
during the next **Pick Walls** operation.

Use the guidance button beside a value when you need to review the
corresponding Risk Matrix guidance.

!!! note "Check before each selection"

    Different building faces may require different values. Review the current selections before each Pick Walls operation.

### 4. Review the Cladding Setup

Open the **Cladding** tab, particularly when setting up the project for
the first time.

Risk Matrix discovers applicable exterior wall types and provides a
project-wide cladding setup. Review:

-   **Project Cladding Legend**
-   **Wall Types to Include**
-   **Wall Type Cladding Mapping**
-   **Project Cladding Health**

For each discovered wall type, the setup can control whether it is
included, its cladding description, and its **Cladding 1--4** group.

The setup is stored in the Revit project and restored when Risk Matrix
is reopened.

!!! warning "Maximum four cladding groups"

    The current workflow supports a maximum of four coordinated project cladding descriptions.

<!-- SCREENSHOT: Cladding tab showing the Project Cladding Legend, Wall Types to Include,
Wall Type Cladding Mapping and Project Cladding Health. -->

### 5. Click Pick Walls

Return to the required Risk View and click:

**Pick Walls**

Select the required **ADa_E\_** exterior walls **one at a time**.

Each selected wall receives a temporary pale-blue highlight so you can
see what has already been selected. The Revit selection prompt also
reports the current selection count.

Press **Esc** when the selection is complete.

In this workflow, Esc finishes wall selection and allows Risk Matrix to
process the walls already selected.

<!-- SCREENSHOT: Pick Walls in progress with several temporarily highlighted walls and
the Revit prompt showing the selection count and Press ESC when finished. -->

### 6. Let Risk Matrix Group the Walls

Flow analyses the selected walls in the current Risk View.

Walls can form one Risk Face where they are sufficiently coplanar and
spatially continuous. A Risk Face can therefore contain more than one
Revit wall, including vertically related wall segments.

A genuine break or change of plane normally creates a separate Risk
Face.

Newly discovered groups are processed in the order established by your
wall selection. Where practical, select walls in the Risk Face numbering
order you want.

➡️ See [**Identifying Risk Faces**](identifying-risk-faces.md)

### 7. Review the Automatic Result

For newly processed Risk Faces, Flow coordinates:

-   a Risk Face number such as **Face 1**, **Face 2** or **Face 3**;
-   the current Risk Matrix values;
-   the applicable cladding information;
-   Risk Face colour and projection graphics in the current view; and
-   a **Risk Face label** tag where possible.

The colour identifies the **Risk Face number**. It does **not**
represent the final E2 risk score.

<!-- SCREENSHOT: Completed Risk View showing several coloured Risk Faces and Face labels.
Ideally include one Risk Face formed from multiple Revit walls. -->

### 8. Continue Around the Building

Use **Next View** and **Previous View** to work through the remaining
Risk Views.

Before each new **Pick Walls** operation, review whether the five
editable Risk Matrix values need to change.

Already processed walls keep their existing risk values if selected
again. They can participate in the selection so their presentation can
be updated in the active view without silently replacing their stored
assessment information.

------------------------------------------------------------------------

## Face Numbering

New Risk Faces normally continue the project sequence:

**Face 1 → Face 2 → Face 3 → ...**

Selection order influences the order in which newly discovered groups
receive their numbers.

### Reprocessing a Reset Face

If all newly selected walls belong to one previously reset Risk Face,
Flow may recognise the previous face number and display **Risk Face
Number** options:

**Next Available**\
Treat the walls as a new Risk Face and use the next available number.

**Restore Original**\
Restore the previous number and shift later Risk Faces where required.

**Choose Number...**\
Insert the face at a selected position in the current sequence.

<!-- SCREENSHOT: Risk Face Number dialog showing Next Available, Restore Original and Choose Number. -->

------------------------------------------------------------------------

## Correcting Risk Faces

### Copy Face

Use **Copy Face** when another wall genuinely belongs to an existing
Risk Face.

Select a processed source wall, then select the target walls one at a
time. Press **Esc** when finished.

Copy Face changes model information: the target walls inherit the source
Risk Face assignment and associated Risk Matrix/cladding information.

### Match Wall End

Use **Match Wall End** when only the visible wall-end presentation needs
to match an existing Risk Face.

Select a processed source wall, then select the exposed **wall face** to
match.

This is a graphics-only operation. It does not assign the target wall to
the source Risk Face or copy its Risk Matrix values.

### Reset Risk Matrix

Use the reset workflow to choose between correcting one face and
clearing the complete project setup.

**Selected Risk Face** clears the selected face's Risk Matrix
information, graphics and associated tags while preserving the
project-wide cladding setup.

**Entire Project** performs a broad Risk Matrix reset and also clears
the saved project cladding configuration.

!!! warning "Use project-wide reset carefully"

    Use the selected-face reset for local corrections wherever possible.

------------------------------------------------------------------------

## Expected Results

After completing the Risk Face mapping workflow, the relevant building
faces should have:

-   coordinated Risk Face numbers;
-   consistent Risk Face colours in the required Risk Views;
-   Risk Face labels where Revit can place them;
-   the intended Risk Matrix parameter values on processed walls; and
-   coordinated cladding information for included wall types.

Review every relevant Risk View before relying on the information for
documentation.

➡️ See [**Reviewing Risk Results**](reviewing-risk-results.md)

------------------------------------------------------------------------

## Current Limitations

Risk Matrix currently does **not**:

-   calculate a completed E2 score for each Risk Face;
-   automatically assess the five geometry/judgement-based risk factors;
-   provide the planned face-by-face assessment DataGrid; or
-   generate the proposed 3D Risk Matrix review model.

The current workflow is therefore focused on **Risk Face mapping,
parameter assignment, cladding coordination and documentation**.

------------------------------------------------------------------------

## Related Help

-   [**Identifying Risk Faces**](identifying-risk-faces.md)
-   [**Assigning Risk Information**](assigning-risk-information.md)
-   [**Reviewing Risk Results**](reviewing-risk-results.md)
-   [**Risk Documentation**](risk-documentation.md)
-   [**Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Getting Help

Hover over **Risk** on the Flow ribbon and press **F1** to return
directly to this page.

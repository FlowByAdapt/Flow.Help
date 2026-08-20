# Risk Matrix

The **Risk Matrix** supports the preparation of external moisture risk
assessment information in Revit.

Use it to identify and number exterior Risk Faces, apply coordinated
face colours and tags, manage project cladding information, and assign
the current project risk values to processed walls.

!!! info "Current assessment scope"

    Risk Matrix currently prepares and coordinates the model information used by the risk assessment workflow.

    Automated per-face E2 risk scoring and a completed-results review grid are planned for future development and are not part of the current tool.

------------------------------------------------------------------------

## Open Risk Matrix

On the Revit ribbon:

**Flow → Model → Risk**

Risk Matrix opens as a modeless window so you can continue working in
Revit while the tool remains open.

------------------------------------------------------------------------

## Before You Start

Risk Matrix works with the project's Risk Views and exterior wall types.

The default Risk View is:

**RISK-01-Elevation**

Other Risk Views use the **RISK-** prefix and can be opened using
**Previous View** and **Next View**.

Exterior walls processed by the tool are based on wall types beginning
with:

**ADa_E\_**

The project **Wind Zone** is read from Revit **Project Information**
rather than selected independently in Risk Matrix.

------------------------------------------------------------------------

## What do you want to do?

### Identify Risk Faces

Select exterior walls, create coordinated Risk Face numbers, and apply
the associated colours and tags.

➡️ [**Identifying Risk Faces**](identifying-risk-faces.md)

### Assign Risk Information

Review the project Wind Zone and select the current Risk Matrix values
that will be written to processed walls.

➡️ [**Assigning Risk Information**](assigning-risk-information.md)

### Review Risk Faces

Check the completed Risk Face numbering, colours, tags and assigned
model information.

➡️ [**Reviewing Risk Results**](reviewing-risk-results.md)

### Work with Risk Documentation

Understand how Risk Face parameters, tags, view graphics and cladding
information support Revit documentation.

➡️ [**Risk Documentation**](risk-documentation.md)

### Having Problems?

Find help for Risk Views, Wind Zone values, wall selection, numbering,
graphics, tags and cladding information.

➡️ [**Troubleshooting**](troubleshooting.md)

------------------------------------------------------------------------

## Main Risk Matrix Controls

**Pick Walls**\
Select exterior walls in Revit and process them using the current Risk
Matrix values.

**Copy Face**\
Copy an existing Risk Face assignment and its Risk Matrix/cladding
information to other walls.

**Match Wall End**\
Apply the colour of an existing Risk Face to another wall in the current
view for graphical continuity. This is a graphics-only operation.

**Reset Risk Matrix**\
Clear Risk Matrix data, Risk Face graphics and Risk Matrix tags from the
project.

------------------------------------------------------------------------

## Getting Help

Hover over **Risk** on the Flow ribbon and press **F1** to return
directly to this page.
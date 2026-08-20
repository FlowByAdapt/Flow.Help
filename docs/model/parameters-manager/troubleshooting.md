# Parameters Manager Troubleshooting

Use these checks if the Opening GP Dashboard or a Parameters Manager
workflow does not behave as expected.

------------------------------------------------------------------------

## The Dashboard Does Not Show a Global Parameter

The dashboard is intentionally focused on the Flow opening workflow and
excludes some office graphics and project-control Global Parameters.

If a Global Parameter is expected in the opening workflow:

1.  Confirm you are in the correct Revit project.
2.  Select **Audit → Refresh Dashboard**.
3.  Check the parameter in Revit's native Global Parameters editor if
    required.

➡️ [**Native Global Parameter
Editor**](native-global-parameter-editor.md)

------------------------------------------------------------------------

## The Dashboard Has Not Updated

The dashboard scans automatically when Parameters Manager opens.

After making changes, select:

**Audit → Refresh Dashboard**

to rescan the current model.

------------------------------------------------------------------------

## I Cannot Edit a Current Value

Direct dashboard editing is currently limited to supported **Text** and
**Length / Number** values.

**Integer / Yes-No**, **Element**, unsupported value types, and the
protected **Zero Window Sill Height** parameter are not directly
editable from the dashboard.

Use the native Revit Global Parameters editor where appropriate.

------------------------------------------------------------------------

## Review Associations Finds Nothing

**Review Associations** reports only Global Parameter associations found
on the selected element.

If none are found, Flow displays a message and makes no changes.

Try **GP Audit** if you need to inspect a different element or multiple
elements.

------------------------------------------------------------------------

## Remove Associations Finds Nothing

Check that:

1.  the intended elements are selected or picked;
2.  those elements actually have Global Parameter associations; and
3.  the associations are removable by the workflow.

If **Current Selection** is chosen with no elements selected, Flow
reports this.

------------------------------------------------------------------------

## Copy GP Setup Does Not Apply the Expected Setup

Check that:

1.  the source element has the required GP associations;
2.  the target elements support matching parameters; and
3.  the correct source and targets were picked.

**Copy GP Setup** copies matching Global Parameter associations; it is
not a general copy-properties command.

------------------------------------------------------------------------

## Window Standards Find No Valid Windows

For **Apply Window Standards**:

-   curtain-wall-hosted windows are excluded;
-   **All Windows** processes qualifying windows created in **New
    Construction**.

For **Apply Existing Window Standards**, selected windows must be
created in the **Existing** phase.

------------------------------------------------------------------------

## Door Standards Do Not Affect a Door

The door standards workflow applies its standard rules to qualifying
doors created in the **New Construction** phase.

Check the door's phase and that the selected element is a door.

------------------------------------------------------------------------

## Office Standard GP Import Does Not Start

Check that:

1.  the current Revit document is open;
2.  a valid source template is selected; and
3.  the source template contains the required office-standard Global
    Parameters.

------------------------------------------------------------------------

## Native GP Editor Does Not Open

Flow first attempts to launch Revit's native Global Parameters command.

If Revit does not expose that command through the API in the current
version:

-   use **GG**, or
-   open **Global Parameters** from the Revit **Manage** tab.

------------------------------------------------------------------------

## Fix Keynotes Does Not Complete as Expected

Check the batch output and result information generated for the run.

The current workflow writes processed copies to **NewFiles** rather than
silently replacing the original source files.

------------------------------------------------------------------------

## Reporting a Problem

If the issue continues, record:

-   Revit version
-   current project
-   Parameters Manager command used
-   selected element or workflow scope
-   expected result
-   actual result
-   any Flow message
-   a screenshot where useful

------------------------------------------------------------------------

## Related Help

-   [Parameters Manager](index.md)
-   [Reviewing Global Parameters](reviewing-global-parameters.md)
-   [Reviewing Associations](reviewing-associations.md)
-   [Auditing Global Parameters](auditing-global-parameters.md)
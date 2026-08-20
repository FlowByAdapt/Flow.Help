# Removing Associations

Use **Remove Associations** to review and remove supported Global
Parameter associations from selected elements.

------------------------------------------------------------------------

## Choose the Elements

1.  Open **Parameters Manager**.
2.  Expand **Associations**.
3.  Select **Remove Associations**.
4.  Choose one of the available scopes:
    -   **Pick Elements**
    -   **Current Selection**
    -   **Cancel**

### Pick Elements

Select the elements in Revit after starting the command.

### Current Selection

Uses the elements already selected in Revit.

If nothing is selected, Flow reports that no elements are currently
selected.

------------------------------------------------------------------------

## Review and Remove

Flow starts the association-removal workflow for the selected elements.

If no removable Global Parameter associations are found, Flow reports
this and no changes are made.

!!! warning "Removing an association"

    Removing an association disconnects the affected element parameter from its Global Parameter.

    Review the associations carefully before confirming removal.

------------------------------------------------------------------------

## Related Help

-   [Parameters Manager](index.md)
-   [Reviewing Associations](reviewing-associations.md)
-   [Copying GP Setup](copying-gp-setup.md)
-   [Troubleshooting](troubleshooting.md)
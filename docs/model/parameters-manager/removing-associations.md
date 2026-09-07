# Removing Associations

Use **Remove Associations** to disconnect selected Revit parameters from their Global Parameters. Flow provides a review window so you can choose the individual associations to remove before the project is changed.

**Ribbon:** Flow → Content → Parameters Manager

---

## Before You Start

Removing an association does not delete the Global Parameter or the selected model element. It disconnects the parameter from the GP that currently controls it.

After an association is removed, the parameter will no longer follow future changes to that GP. Review its resulting Revit value where that matters to the model.

If you are unsure about an element's setup, use **Review Associations** first.

!!! warning "Type associations affect more than one element"

	A **Type** association belongs to the shared Revit type. Removing it can affect every instance using that type, not only the element you selected.

---

## Start the Workflow

1. Open **Parameters Manager**.
2. Expand **Associations**.
3. Select **Remove Associations**.
4. Choose an element scope:
   - **Pick Elements**
   - **Current Selection**
   - **Cancel**

<!-- SCREENSHOT: Remove Associations scope chooser showing Pick Elements, Current Selection and Cancel. -->

### Pick Elements

1. Choose **Pick Elements**.
2. Select one or more elements in Revit.
3. Finish the Revit multi-selection.

Parameters Manager temporarily hides while Revit is waiting for the selection, then returns.

### Current Selection

Choose **Current Selection** to use the elements already selected in Revit.

If nothing is selected, Flow reports that no elements are currently selected and makes no changes.

### Cancel

Choose **Cancel** to close the chooser without inspecting or changing anything.

---

## Review the Associations

Flow discovers supported GP associations on both:

- The selected element instances
- Their Revit types

If associations are found, the **Remove Global Parameter Associations** window opens.

The grid shows:

| Column | Description |
| --- | --- |
| Selection box | Whether the association will be removed. |
| **Parameter** | Associated Revit parameter name. |
| **Global Parameter** | GP currently controlling that parameter. |
| **Scope** | **Instance** or **Type**. |
| **Type** | Revit storage type reported for the parameter. |

All discovered rows are selected initially.

<!-- SCREENSHOT: Remove Global Parameter Associations window with a mixture of Instance and Type rows. Show the selected checkboxes and all four footer buttons. -->

!!! warning "Clear associations you want to keep"

	Because every row is selected by default, review the complete list and clear anything that should remain associated before selecting **Remove Selected**.

---

## Select What to Remove

Use the row checkboxes or the footer controls:

- **Select All** — checks every row
- **Select None** — clears every row
- **Cancel** — closes the review without changing the project
- **Remove Selected** — submits only the checked rows for removal

The summary above the grid updates to show:

- Total associations found
- Number currently selected

If no rows are selected when you choose **Remove Selected**, Flow reports **No associations selected** and keeps the review window open.

---

## Remove the Selected Associations

1. Confirm that only the intended rows are checked.
2. Pay particular attention to rows whose scope is **Type**.
3. Select **Remove Selected**.
4. Review the completion result.
5. Select **Audit → Refresh Dashboard** if you want to update dashboard counts.

Flow processes the selected rows inside one Revit transaction. An individual failure does not prevent other valid associations from being removed.

---

## Completion Result

Flow reports:

| Result | Meaning |
| --- | --- |
| **Associations Found** | Number of checked association records submitted for removal. |
| **Associations Removed** | Associations successfully disconnected. |
| **Failed** | Associations that could not be read, resolved or removed. |

When failures occur, the message can also include parameter-specific details.

<!-- SCREENSHOT: Remove Associations completion message showing found, removed and failed counts. -->

Partial success is possible. Successfully removed associations are committed even when another selected row fails.

---

## Expected Result

After successful removal:

- The selected Revit parameter is no longer associated with its previous GP.
- The GP itself remains in the project.
- Unselected associations remain unchanged.
- A removed type association is removed from the shared type.
- Dashboard counts update after the dashboard is refreshed.

---

## Cancel the Workflow

You can cancel at several points:

- Choose **Cancel** in the scope chooser
- Press **Esc** during Pick Elements selection
- Select **Cancel** in the association review window
- Close the review window without confirming

Cancellation before **Remove Selected** submits no removal request.

---

## If No Associations Are Found

Flow reports that no removable Global Parameter associations were found when none are discovered on the selected instances or their types.

Check that:

1. You selected the intended elements.
2. The parameters are actually associated with Global Parameters.
3. The association exists on either the instance or type.
4. Revit exposes the association through its API.

Use **Review Associations** to inspect one representative element.

---

## Current Limitations

- All associations are selected initially rather than starting with an empty selection.
- Type-association removal can affect every element using the type.
- Removal does not delete the GP.
- Flow continues after individual failures, so a result can be partially successful.
- The workflow removes current associations; it does not validate whether removing them conforms to a Flow preset.
- Some Revit parameters cannot report or remove GP associations through the API.

---

## Related Help

- [Parameters Manager](index.md)
- [Reviewing Associations](reviewing-associations.md)
- [Copying GP Setup](copying-gp-setup.md)
- [Auditing Global Parameters](auditing-global-parameters.md)
- [Reviewing Global Parameters](reviewing-global-parameters.md)
- [Parameters Manager Troubleshooting](troubleshooting.md)

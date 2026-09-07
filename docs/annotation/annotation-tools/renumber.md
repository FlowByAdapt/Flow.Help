# Renumber

**Renumber** renumbers supported Revit elements sequentially in the order they are selected.

Available targets depend on the active Revit view. The tool supports numeric, alphabetic and prefixed numbering sequences, handles existing value conflicts through Flow's shared numbering system, and includes a dedicated **Doors by Room** workflow.

**Ribbon:** **Flow → Annotation → Renumber**

---

## When to Use Renumber

Use **Renumber** when element numbering or naming needs to be reorganised without manually editing values one by one.

Renumber is particularly useful when:

* elements need to be numbered in a specific selection order
* a sequence needs to start from a particular number or letter
* existing values need to be reorganised
* zero-padded or prefixed numbering is required
* Door Marks need to be based on Room Numbers
* Viewport Detail Numbers need to be reorganised on a Sheet

---

## Choosing What to Renumber

Start:

**Flow → Annotation → Renumber**

Flow opens the **Choose element type** window.

The available choices depend on the active Revit view.

Supported Renumber targets include:

| Target    | Value changed |
| --------- | ------------- |
| Rooms     | Room Number   |
| Areas     | Area Number   |
| Doors     | Mark          |
| Walls     | Mark          |
| Windows   | Mark          |
| Levels    | Level Name    |
| Grids     | Grid Name     |
| Viewports | Detail Number |

Not every target is available in every view.

For example:

* model annotation targets are presented where appropriate to the active model view
* Levels and Grids are available in suitable plan, section and elevation views
* Viewports are available when working on a Sheet

<!-- Screenshot recommended:
Show the Renumber "Choose element type" window with several target cards visible.
-->

---

## Sequential Renumber

Most Renumber targets use the same sequential workflow.

### 1. Choose the Element Type

Select the type of element to renumber.

Flow closes the chooser and starts the interactive Renumber workflow.

### 2. Enter the Starting Value

Enter the first value for the new sequence.

The default starting value is:

`1`

Flow checks that the entered value forms a supported numbering sequence before selection begins.

If the value cannot be incremented, Flow displays an **Invalid Starting Value** message.

### 3. Select Elements in Order

Select elements **one at a time in the exact order you want them numbered**.

Flow assigns the current value and then advances to the next value.

!!! tip "Selection order controls the sequence"

	The order in which you select elements determines the order in which their new values are assigned.

The Revit selection prompt shows the value that will be assigned to the next element.

An element that has already been successfully processed during the current Renumber session is not processed again.

### 4. Press Esc to Finish

Press **Esc** when the required elements have been renumbered.

If one or more changes have been completed, the Renumber session is retained.

If no elements were successfully changed, no Renumber operation is retained.

---

## Numbering Sequences

Renumber automatically determines the sequence from the starting value.

### Numeric Sequences

Standard numbers increment normally:

```text
1 → 2 → 3 → 4
```

Leading zeros are retained:

```text
01 → 02 → 03 → 04
```

### Alphabetic Sequences

Letters increment alphabetically:

```text
A → B → C → D
```

Alphabetic sequences continue beyond `Z`:

```text
Y → Z → AA → AB
```

Lowercase sequences remain lowercase:

```text
a → b → c → d
```

### Prefixed Sequences

A trailing number can be incremented while retaining its prefix:

```text
D01 → D02 → D03
```

```text
W10 → W11 → W12
```

Trailing alphabetic sequences are also supported where the entered value forms a valid sequence.

!!! tip "Starting format controls the result"

	Start with `01` if you want leading zeros retained.

	Start with an alphabetic value if you want an alphabetic sequence.

---

## Renumbering Doors

Selecting **Doors** opens an additional **Choose numbering method** window.

Two methods are available:

### Sequential

Renumbers Doors in the order they are selected.

This uses the same sequential Renumber workflow described above.

### By Room

Numbers Doors from their associated Room Numbers.

Choose **By Room** when Door Marks should follow the numbering of the Rooms they serve.

<!-- Screenshot recommended:
Show the "Renumber Doors" chooser with Sequential and By Room visible.
-->

---

## Doors by Room

**Doors by Room** is an interactive plan-view workflow.

### 1. Select a Door

Select a Door in the active plan view.

Only Doors can be selected during this step.

### 2. Flow Determines the Associated Room

Flow checks the Door's **From Room** and **To Room** using the phase assigned to the active view.

If exactly one associated Room is found, Flow uses that Room automatically.

### 3. Select the Room if Required

If Flow cannot identify one unambiguous associated Room, you are prompted to select the intended Room manually.

Only Rooms can be selected during this step.

### 4. Flow Prepares the Door Mark

Flow uses the selected Room Number to prepare an available room-based Door Mark.

If the Door already has a valid, unique room-based Mark, that existing Mark can be retained.

If another Mark is required, Flow determines an available room-based value using the shared Door numbering system.

### 5. Continue Selecting Doors

Continue selecting Doors as required.

Successfully processed Doors receive temporary visual feedback while the workflow remains active.

Press **Esc** when finished.

<!-- Screenshot recommended:
Show a Door and its associated Room in plan with the resulting Door Mark visible.
-->

---

## Doors by Room Requirements

Doors by Room requires:

* an active **plan view**
* a valid phase assigned to the active view
* the selected Door to be **New** in that phase
* the selected Room to have a **Room Number**
* the Door to be associated with the selected Room

If one of these requirements is not met, Flow displays a message explaining why the Door could not be renumbered.

!!! note "Door phase"

	Doors by Room is intended for Doors that are **New** in the phase assigned to the active view.

---

## Existing Value Conflicts

Revit numbering and naming parameters may require unique values.

If a requested value is already being used by another relevant element, Flow handles the conflict through its shared numbering system rather than requiring you to manually clear existing values first.

This applies to sequential Renumber and to Door Marks created through **Doors by Room**.

!!! note "Review large renumbering operations"

	After reorganising a dense existing sequence, review the completed result to confirm that the final numbering arrangement matches the intended documentation strategy.

---

## Visual Feedback

Successfully processed elements receive temporary visual feedback in the active Revit view while Renumber is running.

This makes it easier to see which elements have already been processed.

The temporary overrides are restored when the interactive session is finished with **Esc**.

The completed numbering changes remain.

<!-- Screenshot recommended:
Show a sequential Renumber session in progress with several processed elements visibly identified.
-->

---

## Finishing with Escape

Press **Esc** when the required selection sequence is complete.

If elements have already been successfully renumbered:

* the completed changes are retained
* temporary visual feedback is removed
* the interactive Renumber session finishes

If the workflow is cancelled before any successful changes are made, the session is rolled back.

---

## Undo

A completed interactive Renumber session is grouped as a single Revit operation.

This allows the completed session to be reversed together using Revit Undo.

---

## Related Help

* [Renumber Troubleshooting](troubleshooting.md)
* [Grid Renumber](grid-renumber.md)
* [Grid Dimensions](grid-dimensions.md)
* [Annotation](index.md)
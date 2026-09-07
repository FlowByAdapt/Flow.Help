# Grid Renumber

**Grid Renumber** renumbers Revit grids sequentially in the order they are selected.

It supports numeric, alphabetic and prefixed numbering sequences, handles existing Grid Name conflicts automatically and provides temporary visual feedback as grids are processed.

**Ribbon:** **Flow → Annotation → Grid Renumber**

---

## When to Use Grid Renumber

Use **Grid Renumber** when an existing grid sequence needs to be reorganised without manually editing each Grid Name.

Grid Renumber is particularly useful when:

* grids need to be renumbered in a specific order
* a sequence needs to start from a particular number or letter
* grid numbering needs to be reorganised around existing Grid Names
* a consistent numeric or alphabetic sequence is required

---

## Supported Views

Grid Renumber is available in:

* **Floor Plans**
* **Reflected Ceiling Plans**
* **Engineering Plans**
* **Area Plans**
* **Sections**
* **Elevations**

---

## Renumbering Grids

### 1. Enter the Starting Value

Start:

**Flow → Annotation → Grid Renumber**

The **Renumber Grids** window opens.

Enter the first Grid number or letter for the new sequence.

The default starting value is:

`1`

Flow checks the value before starting the renumbering workflow.

If the value cannot form a supported numbering sequence, Flow reports that the starting value is invalid.

<!-- Screenshot recommended:
Show the Renumber Grids input window.
Use a starting value such as A or 01 to demonstrate that the tool supports more than basic numeric numbering.
-->

### 2. Select Grids in Order

After entering the starting value, select the first Grid.

Flow assigns the current value and then advances the sequence ready for the next Grid.

Continue selecting Grids **one at a time in the exact order you want them numbered**.

!!! tip "Selection order controls numbering"

	Grid Renumber does not determine the required Grid order automatically.

	The order in which you select the grids determines the order in which the new values are assigned.

The Revit selection prompt shows the value that will be assigned to the next Grid.

For example:

```text
Select the next grids element for '4'. Press Escape to finish.
```

This allows you to keep track of the sequence while working through a larger grid arrangement.

### 3. Continue the Sequence

Each successful selection advances the sequence automatically.

For example, starting at `1` produces:

```text
1 → 2 → 3 → 4 → 5
```

Starting at `A` produces:

```text
A → B → C → D → E
```

A Grid that has already been successfully processed during the current run is not processed again if it is selected a second time.

<!-- Screenshot recommended:
Show the Revit view during renumbering with several grids already processed.
Where practical, include the Revit selection prompt showing the value that will be assigned next.
-->

### 4. Press Esc to Finish

When the required grids have been renumbered, press **Esc**.

If at least one Grid has been successfully renumbered, the completed changes are retained.

Flow restores the normal visual appearance of the processed grids and finishes the workflow.

---

## Numbering Sequences

Grid Renumber automatically determines the sequence from the starting value.

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

Grid Renumber can also increment a trailing number while retaining its prefix.

For example:

```text
G01 → G02 → G03 → G04
```

Trailing alphabetic sequences are also supported where the starting value forms a valid sequence.

!!! tip "Choose the starting format carefully"

	The format of the starting value controls the sequence Flow creates.

	For example, start with `01` if you want leading zeros to be retained rather than starting with `1`.

---

## Existing Number Conflicts

Grid Names must remain unique in Revit.

If a requested value is already being used by another Grid, Flow's numbering system handles the conflict automatically so the new sequence can continue.

Conflict checking considers **all grids in the Revit project**, not only grids visible in the active view.

This means you do not need to manually clear existing Grid Names before starting a renumbering sequence.

!!! note "Existing Grid Names"

	Grid Renumber is designed to reorganise an existing numbering sequence while maintaining unique Grid Names.

	Existing conflicts are resolved as part of the renumbering operation.

---

## Selection Behaviour

Grid Renumber accepts **Grids only** during the interactive selection workflow.

Other Revit element types cannot be selected for renumbering.

Grids are selected one at a time so that the selection order directly controls the numbering order.

During a single Grid Renumber run:

* each successful selection receives the current sequence value
* the sequence then advances
* the next value is shown in the Revit selection prompt
* an already-processed Grid is not processed a second time

---

## Visual Feedback

Successfully processed grids receive temporary visual feedback in the active view while Grid Renumber is running.

This makes it easier to see which grids have already been processed when working through a larger grid arrangement.

The temporary overrides are removed when you press **Esc** to finish.

The completed Grid Name changes remain.

<!-- Screenshot recommended:
Show the completed Grid sequence after pressing Esc.
Use the same view as the in-progress screenshot so that the finished numbering and restored Grid appearance are clear.
-->

---

## Invalid Starting Values

The starting value must form a numbering sequence that Flow can increment.

If the entered value is not supported, Flow displays an **Invalid Starting Value** message and does not begin the Grid selection workflow.

Enter a valid numeric, alphabetic or supported prefixed sequence and start Grid Renumber again.

---

## Finishing the Workflow

Press **Esc** when the required grids have been renumbered.

If one or more grids have been successfully changed:

* the numbering changes are retained
* temporary visual feedback is removed
* the Grid Renumber session finishes

If no grids have been successfully renumbered, no numbering changes are retained.

---

## Related Help

* [Grid Renumber Troubleshooting](troubleshooting.md)
* [Renumber](renumber.md)
* [Grid Dimensions](grid-dimensions.md)
* [Annotation](index.md)
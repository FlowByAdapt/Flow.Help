# Join Dimensions

**Join Dimensions** combines two or more compatible dimension strings into one continuous dimension.

You first select a **primary dimension**, followed by the other dimensions you want to join. Flow collects their references, removes duplicates, orders the references along the primary dimension direction and recreates them as a single dimension string.

The primary dimension determines the position and dimension type used for the replacement dimension.

Where possible, **Below** text applied to the original dimensions is preserved and transferred to the recreated dimension.

**Ribbon:** **Flow → Annotation → Join Dimensions**

---

## When to Use Join Dimensions

Use **Join Dimensions** when separate dimension strings would be clearer or easier to manage as one continuous dimension.

This can be useful when:

* dimensions have been created separately during documentation
* adjacent dimension strings need to be combined
* dimension strings are staggered or separated but describe the same direction
* dimension strings containing **Below** labels created through **Dimension Labels** need to be combined

The dimensions do not need to sit on exactly the same dimension line, but they must be compatible and run in the same direction.

---

## Before You Start

**Join Dimensions** can be used in:

* **Floor Plans**
* **Reflected Ceiling Plans**

The dimensions being joined must:

* be linear dimensions
* belong to the active view
* run parallel to the primary dimension
* contain valid references that can be used to recreate the dimension

!!! tip "Choose the primary dimension carefully"

	The primary dimension controls the position and dimension type of the joined dimension.

	Choose the dimension whose location and dimension type you want the completed dimension string to follow.

---

## Opening the Tool

Open:

**Flow → Annotation → Join Dimensions**

Flow begins the interactive selection workflow.

---

## Joining Dimensions

### 1. Select the Primary Dimension

Flow first prompts you to select the **primary dimension**.

Select the dimension whose position and dimension type you want the completed dimension to use.

If the selected element is not a dimension, Flow displays a message and asks you to select the primary dimension again.

<!-- Screenshot recommended:
Show several compatible parallel or staggered dimension strings immediately before selecting the primary dimension.
The image should make it clear which dimension will control the final position.
-->

### 2. Select the Other Dimensions

Flow then prompts you to select the other dimensions to join.

Select one or more additional compatible dimensions and complete the Revit selection.

The dimensions can be separated or staggered, but they must run parallel to the primary dimension.

### 3. Flow Creates the Joined Dimension

Flow validates the selected dimensions and collects the references required to recreate them.

Flow then:

1. Orders the references along the direction of the primary dimension.
2. Removes duplicate or unusable references.
3. Creates a new continuous dimension on the primary dimension line.
4. Uses the dimension type of the primary dimension.
5. Reapplies supported **Below** text where possible.
6. Deletes the original dimensions only after the replacement dimension has been created successfully.

After a successful join, Flow immediately returns to the selection workflow so you can join another group of dimensions.

---

## Choosing the Primary Dimension

The primary dimension provides the basis for the new dimension string.

Its dimension line determines where the replacement dimension is created, and its dimension type is applied to the result.

This means the order in which the dimensions are selected matters.

!!! example "Choosing a primary dimension"

	If two compatible dimensions use different dimension types, select the dimension with the type you want to retain as the **primary dimension**.

	The other dimension contributes its references, but the resulting dimension uses the primary dimension's type.

---

## Expected Result

The original compatible dimension strings are replaced by one continuous dimension positioned on the primary dimension line.

References from the selected dimensions are combined and ordered to create the new dimension string.

Supported **Below** text is reapplied where possible.

<!-- Screenshot recommended:
Show the same area after joining, with the original separate dimensions replaced by one continuous dimension.
Where practical, include a Below label so its preservation can also be seen.
-->

---

## What Flow Preserves

Flow preserves the valid dimension references needed to recreate the combined string.

**Below** text associated with the original dimension or its segments is recorded before the dimensions are recreated. Flow then reapplies those labels to the resulting dimension or segments where possible.

This is particularly useful with labels created through **Dimension Labels**.

!!! info "Below text"

	Join Dimensions specifically preserves supported **Below** text.

	Other custom dimension text or overrides should not be assumed to transfer to the replacement dimension.

---

## Staggered or Separated Dimension Strings

The dimensions being joined do not need to be positioned on exactly the same dimension line.

As long as they are compatible and run parallel to the primary dimension, Flow can collect their references and order them along the primary dimension direction.

The resulting continuous dimension is placed on the dimension line of the **primary dimension**.

!!! tip "Use the primary dimension to control placement"

	When joining staggered dimensions, select the dimension that is already in the preferred final position as the primary dimension.

---

## Duplicate and Zero-Length Segments

Joining separate dimensions can sometimes introduce duplicate or redundant references.

Flow removes duplicate references before creating the replacement dimension.

If the recreated dimension still contains a zero-length segment, Flow removes the redundant reference responsible for that segment and retries the dimension creation. This process continues until a valid dimension can be created or there are not enough usable references remaining.

!!! info "Source dimensions are protected"

	Flow does not delete the original dimensions until a valid replacement dimension has been created successfully and supported Below labels have been reapplied.

---

## If the Dimensions Cannot Be Joined

Flow validates the selected dimensions before replacing them.

A join may be rejected if:

* fewer than two different dimensions are selected
* a dimension does not belong to the active view
* a selected dimension is not linear
* the dimensions do not run parallel to the primary dimension
* a dimension does not contain enough valid references
* the active view is not a Floor Plan or Reflected Ceiling Plan
* the collected references cannot produce a valid replacement dimension

If Flow cannot complete the join, it displays a message explaining the problem and leaves the existing dimensions in place.

Correct the issue and select the dimensions again.

---

## Repeating and Finishing

After successfully joining a group of dimensions, Flow is ready for another group.

Select another primary dimension and repeat the process as required.

Press **Esc** during the selection workflow when you have finished.

Cancelling the selection ends **Join Dimensions** cleanly without being treated as an error.

---

## Related Help

* [Annotation](index.md)
* [Dimension Labels](dimension-labels.md)
* [Wall Dimensions](wall-dimensions.md)
* [Grid Dimensions](grid-dimensions.md)
* [Annotation Troubleshooting](troubleshooting.md)
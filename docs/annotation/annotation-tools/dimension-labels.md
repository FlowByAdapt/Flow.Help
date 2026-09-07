# Dimension Labels

**Dimension Labels** applies the name of a Room to an individual dimension segment.

You select a dimension chain, identify the segment you want to label, then select a **Room Tag**. Flow reads the Name of the associated Room and places it below the selected dimension segment.

**Ribbon:** **Flow → Annotation → Dimension Labels**

---

## When to Use Dimension Labels

Use **Dimension Labels** when dimension strings would benefit from additional room information.

This is particularly useful for continuous dimensions where individual segments relate to different rooms or spaces and the Room Name provides useful context alongside the dimension value.

Labels created through Dimension Labels are also designed to work with **Join Dimensions**.

---

## Before You Start

Open a:

* **Floor Plan**, or
* **Reflected Ceiling Plan**

containing:

* a continuous dimension chain; and
* the Room Tag for the room name you want to apply.

!!! note "Continuous dimension required"

	The selected dimension must contain individual dimension segments.

	A simple unsegmented dimension cannot receive a segment label through this workflow.

---

## Applying a Room Name

### 1. Select the Dimension

Start **Dimension Labels**.

Flow prompts:

**Select a dimension. Press Esc to finish.**

Select the continuous dimension containing the segment you want to label.

If you select something other than a dimension, Flow displays a message and allows you to try again.

### 2. Choose the Dimension Segment

Flow prompts:

**Click the dimension segment to label.**

Click close to the dimension segment that you want to label.

Flow identifies the dimension segment nearest to the point you click.

!!! tip "Click close to the intended segment"

	When dimension segments are close together, click near the centre of the segment you want to label.

	This helps Flow identify the intended segment correctly.

<!-- Screenshot recommended:
Show a Floor Plan after the dimension chain has been selected and while the user is being prompted to click the dimension segment.
Include several dimension segments and nearby Room Tags so the selection sequence is clear.
-->

### 3. Select the Room Tag

Flow then prompts:

**Select a Room Tag.**

Select the Room Tag containing the Room Name you want to apply.

Flow identifies the Room associated with the selected tag and reads its **Name**.

If you select something other than a Room Tag, Flow displays a message and returns to the workflow.

If the selected Room Tag cannot be associated with a valid Room, no label is applied.

### 4. Flow Applies the Room Name

Flow writes the Room Name below the selected dimension segment.

After applying the label, Flow is immediately ready for another dimension.

Repeat the process for additional dimension segments as required.

---

## Expected Result

The selected Room's Name appears below the chosen dimension segment.

The dimension value itself is unchanged.

The Room Tag is only used to identify the Room and obtain its Name; the Room Tag itself is not modified.

<!-- Screenshot recommended:
Show the completed dimension with the Room Name clearly displayed below the selected segment.
Keep the source Room Tag visible so the relationship between the Room Name and resulting dimension label is easy to understand.
-->

---

## Choosing the Correct Segment

Dimension Labels works with individual segments within a continuous dimension chain.

After selecting the dimension, you identify the required segment by clicking near it.

Flow compares the clicked position with the available dimension segments and uses the nearest segment.

For dimension strings containing several short segments, zoom in if necessary before choosing the segment.

---

## Existing Below Text

Dimension Labels writes the Room Name to the dimension segment's **Below** text.

If the selected segment already contains Below text, the existing text is **replaced** by the Room Name.

!!! warning "Existing Below text is replaced"

	Check the selected segment before applying a Room Name if it already contains manually entered Below text.

	Dimension Labels does not append the Room Name to existing Below text.

---

## Room Information

The text applied to the dimension comes from the **Name** of the Room associated with the selected Room Tag.

Flow resolves the Room from the selected tag and then reads its Name.

If Flow cannot find a valid Room associated with the selected Room Tag, it displays a message and leaves the dimension unchanged.

!!! info "The Room is the source"

	Dimension Labels uses the selected Room Tag to identify its associated Room.

	The resulting dimension text comes from the Room Name rather than from manually entered text in the Room Tag.

---

## Working with Join Dimensions

Room Names applied by Dimension Labels are stored as **Below** text on the dimension segments.

**Join Dimensions** preserves supported Below labels when compatible dimensions are recreated as a continuous dimension string.

This allows Room Names added through Dimension Labels to remain associated with the resulting dimension segments where they can be matched during the join.

!!! tip "Dimension Labels + Join Dimensions"

	You can apply Room Names before joining compatible dimension strings.

	Join Dimensions will attempt to carry those Below labels across to the recreated dimension.

---

## If a Label Cannot Be Applied

Dimension Labels may display a message if:

* there is no active Revit document
* the active view is not a Floor Plan or Reflected Ceiling Plan
* the selected element is not a dimension
* the selected element is not a Room Tag
* the selected Room Tag cannot be associated with a valid Room
* the dimension is no longer valid
* Revit cannot apply the Room Name to the dimension

If an invalid dimension or Room Tag is selected, correct the selection and continue the workflow.

A failed label operation does not end the entire Dimension Labels session.

---

## Repeating and Finishing

After successfully applying a Room Name, Flow returns to dimension selection.

You can continue labelling additional dimension segments without restarting the tool.

The sequence for each label is:

**Select Dimension → Choose Segment → Select Room Tag**

Press **Esc** during the interactive workflow when you have finished.

Dimension Labels exits cleanly and returns you to the Annotation window when launched from there.

---

## Related Help

* [Annotation](index.md)
* [Join Dimensions](join-dimensions.md)
* [Annotation Troubleshooting](troubleshooting.md)
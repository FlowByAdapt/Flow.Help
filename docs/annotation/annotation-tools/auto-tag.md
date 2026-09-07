# Auto Tag

**Auto Tag** automatically places configured tags on supported elements in the active Revit view.

Auto Tag contains individual tagging workflows for different element types. The current workflow automatically finds and tags **Downpipes**, while leaving downpipes that are already tagged unchanged.

**Ribbon:** **Flow → Annotation → Auto Tag**

---

## When to Use Auto Tag

Use **Auto Tag** when you need to quickly apply standard tags to supported elements across the active view.

Rather than selecting elements and placing tags individually, Flow:

1. finds the supported elements in the active view
2. identifies elements that are already tagged
3. selects the appropriate standard tag type
4. automatically places tags on the remaining elements

This is particularly useful when preparing or updating documentation views containing multiple downpipes.

---

## Opening Auto Tag

Start **Auto Tag** from:

**Flow → Annotation → Auto Tag**

Flow opens the **Choose tagging workflow** window.

Select the type of element you want Flow to tag.

Currently available:

**Downpipes** — Automatically tag untagged downpipes in the active view.

<!-- Screenshot recommended:
Show the Auto Tag "Choose tagging workflow" window with the Downpipes card visible.
This demonstrates that Auto Tag contains individual automatic tagging workflows.
-->

---

## Downpipes

The **Downpipes** workflow automatically finds supported downpipe families in the active view and places the appropriate standard Flow tag.

There is no need to:

* select the downpipes
* choose a tag type
* position individual tags

Flow performs these steps automatically.

---

## Before You Start

Open the Revit view containing the downpipes you want to tag.

Auto Tag supports:

* **Floor Plans**
* **Reflected Ceiling Plans**
* **Engineering Plans**
* **Sections**
* **Elevations**

View Templates and unsupported view types cannot be used.

The required standard tag families must also be loaded into the project.

!!! note "Active view only"

	Auto Tag processes downpipes visible to Revit's element collector in the active view.

	It does not automatically tag downpipes throughout the entire project.

---

## Automatically Tagging Downpipes

### 1. Open Auto Tag

Start:

**Flow → Annotation → Auto Tag**

The **Choose tagging workflow** window opens.

### 2. Choose Downpipes

Select:

**Downpipes**

Flow begins processing the active view.

No further element selection is required.

### 3. Flow Finds the Downpipes

Flow searches the active view for supported downpipe family instances.

A supported downpipe must:

* have a Family Name containing `ADa_PLM_Downpipe`; and
* be categorised as either **Plumbing Fixtures** or **Generic Models**.

Flow also checks the tags already placed in the active view.

If a downpipe is already tagged, it is skipped.

<!-- Screenshot recommended:
Show a supported Revit view before running Auto Tag.
Include several untagged downpipes and, if practical, one downpipe that is already tagged.
-->

### 4. Flow Places the Tags

For each untagged downpipe, Flow determines which standard tag is required and places it automatically.

Tags are created:

* horizontally
* without leaders
* at an automatically determined position

If Revit cannot tag an individual downpipe, Flow skips that instance and continues processing the remaining downpipes.

---

## Supported Downpipes

Auto Tag currently recognises two types of downpipe family instance.

### Plumbing Fixture Downpipes

The family must:

* be in the **Plumbing Fixtures** category; and
* have a Family Name containing `ADa_PLM_Downpipe`.

### Generic Model Downpipes

The family must:

* be in the **Generic Models** category; and
* have a Family Name containing `ADa_PLM_Downpipe`.

This allows the same Auto Tag workflow to support downpipes modelled using either of the standard categories.

---

## Standard Tag Types

Flow automatically chooses the required tag.

You do not need to select a tag family or tag type.

### Plumbing Fixtures

Plumbing Fixture downpipes use:

**Family:** `ADa_TAG_plum`
**Type:** `Tag_plum`

### Generic Models

Generic Model downpipes use:

**Family:** `ADa_TAG_Multi-Cat-Mark`

Generic Model downpipes are tagged using Revit's multi-category tagging behaviour.

!!! warning "Required tags"

	The appropriate standard tag must be loaded into the project.

	If qualifying downpipes are present but the required tag cannot be found, Flow reports which standard tag is missing and does not continue with the tagging operation.

---

## Existing Tags

Auto Tag is designed to avoid duplicating tags.

Before creating new tags, Flow checks which elements are already referenced by tags in the active view.

If a downpipe already has a tag, Flow leaves it unchanged.

This applies even if the existing tag is different from the standard tag that Auto Tag would normally use.

!!! info "Existing tags are left alone"

	Auto Tag does not replace, reposition or change an existing tag simply because it uses a different tag type.

	To replace an existing tag, remove or change that tag separately before running Auto Tag again.

---

## Tag Placement

Tag positions are determined automatically.

Where possible, Flow places the tag at the downpipe family's location point.

If a location point is not available, Flow uses the centre of the downpipe's bounding box.

If Flow cannot determine a usable tag position, that downpipe is skipped.

Tags are created horizontally and without leaders.

You can reposition the resulting tags using standard Revit controls if further documentation adjustment is required.

---

## Expected Result

After running Auto Tag:

* previously untagged supported downpipes have the appropriate standard tag
* downpipes that were already tagged remain unchanged
* the appropriate tag type is selected automatically
* tags are placed horizontally without leaders

<!-- Screenshot recommended:
Show the same view used for the "before" screenshot after Auto Tag has run.
Previously untagged downpipes should now be tagged, while the downpipe that already had a tag should retain its original tag.
-->

---

## If Downpipes Cannot Be Tagged

### No downpipes found

If Flow cannot find any supported downpipes in the active view, it reports:

**No downpipes were found in the active view.**

Check that the downpipe families:

* are present in the active view
* use the expected `ADa_PLM_Downpipe` Family Name
* are categorised as Plumbing Fixtures or Generic Models

### Required tag not found

If a Plumbing Fixture downpipe is present but its standard tag cannot be found, Flow expects:

`ADa_TAG_plum : Tag_plum`

For Generic Model downpipes, Flow expects:

`ADa_TAG_Multi-Cat-Mark`

Load the required tag into the project and run Auto Tag again.

### All downpipes are already tagged

If supported downpipes are present but none require a new tag, Flow reports:

**No untagged downpipes were found in the active view.**

No existing tags are changed.

### Unsupported view

If the active view does not support Auto Tag, Flow reports:

**Auto Tag is not available in the active view.**

Switch to a supported Floor Plan, Reflected Ceiling Plan, Engineering Plan, Section or Elevation and run the tool again.

### Individual downpipe cannot be tagged

Some individual instances may not be taggable by Revit in the active view.

Flow skips these instances and continues processing the remaining downpipes rather than cancelling the entire operation.

---

## Related Help

* [Annotation](index.md)
* [Annotation Troubleshooting](troubleshooting.md)
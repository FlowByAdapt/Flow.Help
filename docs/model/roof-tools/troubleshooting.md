# Roof Tools Troubleshooting

Use this page when Roof Tools cannot process the selected geometry or
the result is not what you expected.

---

## Roof Outline Cannot Be Run

**Roof Outline** must be started from a plan view.

If the command reports that it can only run from a plan view, open the
required Revit plan and run the tool again.

---

## No Roofs Were Selected

Roof Outline requires one or more Revit roof elements.

Run the command again and select the roof elements that should
contribute to the final perimeter.

---

## No Roof Footprint Was Found

The current Roof Outline workflow reads the profiles of Revit **Roof by
Footprint** elements.

If the selected roof was created using another method, Flow may not be
able to generate an outline from it.

Use a supported footprint roof or create/review the required
documentation manually.

---

## The Roof Outline Is Not What I Expected

Check that all roof elements forming the intended overall roof were
included in the selection.

Roof Outline treats the selected roof profiles as one boundary network.
Missing or unintended roof elements can therefore change the resulting
outside perimeter.

For complex roof arrangements, visually compare the generated detail
lines with the roof geometry before using the result for documentation.

---

## An Existing Roof Outline Disappeared

When deletion of an existing outline is enabled, Flow removes existing
detail curves in the active view that use the Roof Outline line style
before creating the replacement outline.

This is intentional and allows an existing outline to be regenerated
after the roof design changes.

---

## Gutter Caps Does Not Accept the Selected Element

Gutter Caps is intended to work with Revit **Gutter** elements.

If another element is selected, select the gutter itself. Use **Tab**
where necessary to cycle through overlapping Revit elements.

---

## A Gutter End Cannot Be Found

Pick close to the physical end of the gutter.

The established Gutter Cap workflow identifies the end face nearest the
picked point. A point too far from the intended end may make the
required face difficult to identify.

If the gutter geometry is unusual, cancel the workflow and inspect the
gutter profile before trying again.

---

## A Gutter Cap Was Not Created

A cap may be skipped when a previously generated Gutter Cap already
exists near that gutter end.

Check the end in a suitable 3D or plan view before attempting to create
another cap.

---

## The Gutter Cap Shape Is Not What I Expected

The cap is derived from the gutter's end geometry.

Unusual or complex profiles may not produce the expected envelope.
Review the generated solid and remove it if the result is unsuitable.

The original Revit gutter remains separate from the generated cap.

---

## Related Help

- [Roof Tools](index.md)
- [Roof Outline](roof-outline.md)
- [Gutter Caps](gutter-caps.md)
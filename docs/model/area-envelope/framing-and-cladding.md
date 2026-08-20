# Framing and Cladding

Area Envelope provides two workflows for positioning Area Boundary Lines relative to the exterior wall construction.

---

## Cladding Area

Use **Cladding Area** when the measured area needs to follow the exterior cladding face of the selected perimeter walls.

Flow derives an exterior cladding-face boundary from each selected wall, trims the resulting lines into a continuous perimeter, and creates the boundary in an Area Plan using the **Area to Cladding** Area Scheme.

---

## Framing Area

Use **Framing Area** when the measured area needs to follow the exterior framing boundary of the selected perimeter walls.

Flow derives the exterior framing position from the selected wall construction, trims the resulting lines into a continuous perimeter, and creates the boundary in an Area Plan using the **Area to Framing** Area Scheme.

---

## Choosing the Correct Mode

| Mode | Boundary position | Required Area Scheme |
| --- | --- | --- |
| **Cladding Area** | Exterior cladding face | **Area to Cladding** |
| **Framing Area** | Exterior framing boundary | **Area to Framing** |

!!! tip "Choose the measurement line"

    Use **Cladding Area** for an envelope measured to the outside cladding surface. Use **Framing Area** when the required measurement relates to the external framing line.

---

## Wall Construction Requirements

The selected walls must provide geometry that Flow can use for the chosen mode. The result depends on the wall orientation, compound structure, layer functions, joins, and the continuity of the selected perimeter.

Review the generated boundary whenever the model contains unusual wall types, edited profiles, curved walls, complex joins, or discontinuous perimeter conditions.

---

## Area Plan Selection

Flow reuses a matching existing Area Plan. It does not create a new Area Scheme or Area Plan.

When the active view is not suitable, Flow searches for another Area Plan using the required scheme and activates an appropriate view. The active matching Area Plan is preferred, followed by an open matching plan, a named ground-floor plan, or the lowest-level matching plan.

---

## Related Help

* [Area Envelope](index.md)
* [Creating Area Envelopes](creating-area-envelopes.md)
* [Troubleshooting](troubleshooting.md)

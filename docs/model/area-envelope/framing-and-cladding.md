# Framing and Cladding

Area Envelope provides two workflows for positioning Area Boundary Lines relative to the exterior wall construction.

The important difference is where Flow derives the boundary from each selected wall.

---

## Cladding Area

Use **Cladding Area** when the measured envelope needs to follow the outside surface of the wall.

Flow finds a usable planar exterior face for each selected Basic Wall and derives the Area Boundary Line from that exterior face.

The result is created in an existing Area Plan using a matching cladding Area Scheme. The standard scheme name is **Area to Cladding**.

---

## Framing Area

Use **Framing Area** when the measured envelope needs to follow the exterior boundary of the Revit wall core.

Flow starts from the wall's exterior face and reads the wall's compound structure. It sums the widths of all layers outside the first core layer and offsets the exterior face inward by that distance.

For a correctly configured framed wall, where the Revit core begins at the framing layer, this normally corresponds to the outside face of the framing.

The result is created in an existing Area Plan using a matching framing Area Scheme. The standard scheme name is **Area to Framing**.

!!! important "Framing uses the Revit core boundary"

    Flow does not search for a layer whose material or function is named "framing". The Framing Area position is determined by the wall's compound structure and the location of its first core layer.

---

## Choosing the Correct Mode

| Mode | Boundary position | Standard Area Scheme |
| --- | --- | --- |
| **Cladding Area** | Exterior planar wall face | **Area to Cladding** |
| **Framing Area** | Exterior boundary of the wall core | **Area to Framing** |

!!! tip "Choose the measurement line"

    Use **Cladding Area** when the required measurement is to the outside wall surface. Use **Framing Area** when the required measurement is to the outside of the wall core or framing line.

<!-- SCREENSHOT: Plan detail of the same exterior wall/corner showing the Cladding Area boundary at the outside face and the Framing Area boundary at the exterior core boundary. -->

---

## Wall Compound Structure Matters

The Framing Area result depends on the wall type's compound structure and core boundaries.

For example, if a wall contains exterior cladding, cavity and other non-core layers outside a framed core, Flow offsets inward across those exterior layers to reach the first core layer.

If Flow cannot obtain a usable core definition, the calculated framing inset is zero. In that situation, the Framing Area boundary can coincide with the Cladding Area boundary.

If the two modes produce an unexpected result, check the wall type's compound structure and core boundaries in Revit.

---

## Wall Geometry Requirements

Both modes require supported wall geometry.

Area Envelope currently supports:

* **Basic Walls**;
* straight wall location lines;
* usable planar exterior wall faces;
* one continuous closed perimeter.

Curved walls are not currently supported.

The wall's exterior/interior orientation also matters because the boundary is derived from the exterior side of the wall.

---

## Area Plan Selection

Flow reuses a matching existing Area Plan. It does not create a new Area Scheme or Area Plan.

The standard scheme names are **Area to Cladding** and **Area to Framing**, but Flow also recognises names that clearly identify the corresponding Area and Cladding or Framing purpose, including common **A2C** and **A2F** variants.

When the active view is not already suitable, Flow prefers:

1. a matching Area Plan on the same level as the current plan view;
2. an already open matching Area Plan;
3. a matching ground-floor Area Plan;
4. the lowest-level matching Area Plan.

---

## Related Help

* [Area Envelope](index.md)
* [Creating Area Envelopes](creating-area-envelopes.md)
* [Troubleshooting](troubleshooting.md)

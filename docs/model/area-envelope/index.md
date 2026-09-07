# Area Envelope

The **Area Envelope** tool creates Revit Area Boundary Lines from selected perimeter walls at either the exterior cladding face or the exterior boundary of the wall core.

After the boundary is created, Flow can also place an Area and leaderless Area Tag automatically, place them at a point you select, or leave the result as boundary lines only.

---

## Open Area Envelope

On the Revit ribbon:

**Flow → Model → Areas**

Choose:

* **Cladding Area**
* **Framing Area**

You can also run **Cladding Area** or **Framing Area** directly from Flow Hub.

---

## How It Works

1. Choose **Cladding Area** or **Framing Area**.
2. Select the exterior walls that form one continuous closed perimeter.
3. Click **Finish** in Revit's native wall-selection mode.
4. Flow activates a suitable existing Area Plan and creates the Area Boundary Lines.
5. Choose **Auto Area + Tag**, **Manual Area + Tag**, or **Boundary Only**.
6. Review the completed boundary in the activated Area Plan.

!!! note "Existing Area Plan required"

    Flow reuses an existing Area Plan with a matching Area Scheme. It does not create the Area Scheme or Area Plan.

<!-- SCREENSHOT: Finished Area Envelope in an Area Plan, showing boundary lines, Area and leaderless Area Tag. -->

---

## What Do You Want to Do?

### Create an Area Envelope

Follow the complete workflow, including wall selection, Area Plan activation, boundary creation and Area placement.

➡️ [**Creating Area Envelopes**](creating-area-envelopes.md)

### Choose Framing or Cladding

Understand exactly where each boundary is taken from and how the wall compound structure affects the result.

➡️ [**Framing and Cladding**](framing-and-cladding.md)

### Having Problems?

Find help for wall selection, Area Plans, unsupported walls, invalid loops, boundary position and Area or tag placement.

➡️ [**Troubleshooting**](troubleshooting.md)

---

## Getting Help

Hover over **Areas** on the Flow ribbon and press **F1** to return directly to this page.

# Geometry and Output Options

Use **Geometry** to inspect family complexity and choose optional connector, unit-display and preview settings.

---

## Inspect Elements

Select the required **Values / inspection type** and review **Elements**. The list includes element IDs, kinds, ratings, triangle and face counts, location, coverage and cleanup information.

Use the element ID to locate content for further inspection in the Family Editor. Review **Nested Families** for nested content recorded by the audit.

!!! note "Ratings are inspection guides"

    Ratings use measured geometry counts. Partial counts are lower bounds, and triangle share uses measured triangles only. Ratings do not prove safe removal or measure project performance.

---

## Compare Types

1. Choose **Compare All Types**.
2. Review **Type Comparison** for differences in ratings, triangles and faces.
3. Select a type to inspect its preview.
4. Return to **Elements** for its geometry details.

!!! tip "Inspect the more complex types"

    A family can vary substantially between types. Use the comparison to identify types that need closer review before approving library content.

<!-- SCREENSHOT: Geometry Type Comparison showing several types with different counts and a selected type preview. -->

---

## Remove MEP Connectors

Under **Options & Details**, review the connector information and select **Remove MEP connectors (disconnects services)** only when the cleaned copy should lose those connections.

The action targets supported host-family connectors. Nested content and associated parameters are retained. Unexpected dependent deletions block output publication.

!!! warning "Connector removal changes function"

    The output loses the removed MEP connection capabilities. Confirm that the family will not be required to connect to services before selecting this option.

---

## Use Metric Display

Select **Metric display · nearest 5 mm (size unchanged)** to use millimetre length display rounded to the nearest 5 mm, with area in square metres and volume in cubic metres.

Actual dimensions are unchanged. Custom dimension/label overrides and nested-family units remain unchanged, and the destination project can control display after loading.

---

## Save a Preview PNG

Select **Save preview PNG beside cleaned family**. Choose the required inspection type before reviewing the final plan.

The PNG is generated from the reopened cleaned family using the selected type and its final approved name. Temporary preview changes are rolled back.

If the requested preview cannot be generated, publication is blocked. Resolve the failure or remove the PNG option, review the revised plan and save again.

---

## Related Help

- [**Selecting and Auditing Families**](selecting-and-auditing.md)
- [**Reviewing and Saving**](reviewing-and-saving.md)
- [**Preview Generator**](https://help.flowbyadapt.com/content/preview-generator/)
- [**Troubleshooting**](troubleshooting.md)

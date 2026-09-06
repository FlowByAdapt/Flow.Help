# Auto Tag

**Auto Tag** automatically places configured tags on supported elements in the active view.

The verified source workflow uses this capability to place downpipe tags while avoiding elements that are already tagged.

------------------------------------------------------------------------

## Opening the Tool

On the **Flow** ribbon:

1.  Open **Annotation**.
2.  Choose **Auto Tag**.

------------------------------------------------------------------------

## Tagging Supported Elements

For the verified downpipe workflow:

1.  Open the view containing the elements to tag.
2.  Start **Auto Tag**.
3.  Choose the required downpipe tag type.
4.  Flow finds supported downpipe instances in the active view.
5.  Existing tags are checked.
6.  Flow places the selected tag type on untagged downpipes.
7.  Review the resulting tag positions.

------------------------------------------------------------------------

## Choosing a Tag Type

The source workflow finds tag family types whose family name begins with the configured downpipe tag prefix.

User-facing labels are shortened so office naming prefixes do not dominate the tag chooser.

If no supported tag types are loaded, the workflow cannot continue.

------------------------------------------------------------------------

## Already-Tagged Elements

Auto Tag checks existing Independent Tags in the active view and skips elements that are already tagged.

!!! info "Existing tags are retained"

    Auto Tag is intended to add missing tags rather than duplicate tags that already reference the same element.

------------------------------------------------------------------------

## Tag Placement

For supported family instances, Flow places the tag at the element location.

Where a direct location point is not available, the source workflow falls back to the centre of the element bounding box.

Tags are created with horizontal orientation.

------------------------------------------------------------------------

## View Templates

The verified source workflow temporarily detaches a view template where necessary for tag creation, restores the template afterwards, and ensures the created tag category remains visible.

------------------------------------------------------------------------

## Related Help

-   [Auto Tag Troubleshooting](troubleshooting.md)
-   [Annotation](index.md)
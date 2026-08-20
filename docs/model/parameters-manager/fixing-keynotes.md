# Fixing Keynotes

Use **Fix Keynotes** to batch-apply configured keynote standards to
external Revit files.

This is a maintenance workflow and is separate from editing values in
the Opening GP Dashboard.

------------------------------------------------------------------------

## Start Fix Keynotes

Open:

**Parameters Manager → Maintenance → Fix Keynotes**

Follow the folder/file selection workflow presented by Flow.

The batch process reviews supported Revit files and applies the
configured keynote-standard rules.

------------------------------------------------------------------------

## Output

The current batch workflow preserves the source files and writes
processed copies to a **NewFiles** output location.

The batch system processes Revit files in groups and produces result
information for the run.

!!! warning "Check the output"

    Review the processed copies before replacing or distributing source content.

    The maintenance workflow is designed to avoid silently overwriting the original files.

------------------------------------------------------------------------

## Related Help

-   [Parameters Manager](index.md)
-   [Troubleshooting](troubleshooting.md)
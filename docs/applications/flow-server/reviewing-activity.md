# Reviewing Server Activity

The **Activity** tab scans the connected Revit Server and groups recent model activity by project.

Use it to understand which models have been active, who made the latest change and when that activity occurred.

---

## Before You Start

Connect to the required Revit Server address and version first.

Activity information is collected when you deliberately start a scan. Opening the tab does not automatically scan every model.

---

## Scanning Activity

1. Open the **Activity** tab.
2. Select **Scan Activity**.
3. Allow Flow to inspect the available models.
4. Review the project list when the scan completes.

During the scan, the status area reports the number of models completed and identifies the model currently being checked.

The project list reports:

- project name
- number of models
- latest activity
- total model size
- whether locked models are present

!!! info "A partial scan can still return results"

    If some models cannot be inspected, Flow reports the number of successful and failed checks when the scan finishes.

---

## Searching Project Activity

Enter part of a project name in the Activity search field.

Flow filters the scanned project list without running another server scan.

---

## Reviewing Models in a Project

Select a project to show its models.

The model list includes:

- model name
- latest activity
- user
- revision
- size
- lock state

Select a model and choose **View History** to open its complete revision history.

<!-- Screenshot recommended:
Show the Activity tab after a completed scan.
Include the project summary list and the models for one selected example project.
Use fictional project and user names.
-->

---

## Related Help

- [Flow Server](index.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Troubleshooting](troubleshooting.md)
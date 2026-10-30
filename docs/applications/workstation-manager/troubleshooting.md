# Workstation Manager Troubleshooting

This page covers common connection, inventory, installation and notification issues in **Flow Workstation Manager**.

For the normal workflow, start with [Flow Workstation Manager](index.md).

---

## The Office Folder Cannot Be Reached

Check:

- that the computer is connected to the office network or approved remote connection
- that **NAS folder** matches the location supplied by your office administrator
- that the folder can be opened in File Explorer
- that your Windows account can read releases and save inventory reports

After reconnecting, select **Scan and check in** or **Check updates** as required.

Local reports are retained when delivery fails.

---

## A Computer Shows an Old Application Version

Check **Last checked** on **Office computers**.

Open Workstation Manager on the affected computer while connected to the office network. It automatically scans and attempts to check in. If needed, select **Scan and check in** and review the delivery message.

Then select **Refresh office reports** on the reviewing computer.

Updating one computer does not update the other computers or their reports.

---

## Flow Tools Show Installed—Release Not Recorded

Flow add-ins were detected, but their installed release could not be verified.

1. Review **Add-in details**.
2. Close all Revit sessions.
3. Select **Check updates** and the affected Revit year.
4. Use **Install / update tools** and review the result.
5. If installation fails, expand **Report details** and report the exact error.

Ask your office administrator to investigate conflicting or malformed Flow registrations. Avoid deleting add-in files based only on this status.

---

## Installation Says Revit Is Still Open

Close all Revit sessions, including other Revit years and any separate worker sessions. Wait for them to finish closing before trying again.

Save any work before closing Revit. If no Revit window is visible and the message remains, ask your office administrator to check for a remaining process.

---

## Tools Fail to Load After Installation

Record:

- the Revit year
- the Flow tools release shown by Workstation Manager
- the tool you tried to open
- the complete error message

Close Revit before retrying installation. If a compatible previous installation is available, review [Restoring Previous Tools](restoring-previous-tools.md).

---

## No Restore Backup Is Available

A compatible previous installation has not been retained for the selected year.

Restore cannot reconstruct a missing backup. If the current tools need repair, review the approved installation with your office administrator.

---

## No Update Is Offered

Check that:

- the office folder is reachable
- the relevant update check has completed
- the correct Revit year or application is selected
- an approved release has been set
- the installed version is older than the approved version, or the product is missing

An installation newer than the approved release is not automatically downgraded. A missing optional product may offer installation without producing a reminder or red update count.

---

## Flow Server Is Installed but Not Detected

On that computer, open Workstation Manager and select **Scan and check in**. Then check **Flow apps** and the report details.

If detection still fails, report the Server installation location and the error or status shown. The office view may simply be displaying an older report.

---

## The Red Number Does Not Clear

Run **Check updates** on **This computer** and **Check app updates** on **Flow apps** while connected to the office folder.

Dismissing an update notice does not clear an available update. An offline indicator retains the last known count until successful checks refresh it.

If the number is a preview **3**, allow approximately twelve seconds for the preview to finish.

---

## No Indicator or Notice Appears

Check the Windows hidden-icons area beside the clock and review **Background checks**.

A notice may already have been shown for the same update that day. Missing optional installations are not counted as updates. If the indicator was exited, opening Workstation Manager or the next scheduled check can start it again.

---

## Revit Differs from Standard

This compares the installed Autodesk Revit version with the exact office standard. It is separate from the Flow tools release check.

Ask your office administrator whether a Revit update is required. Workstation Manager does not install Autodesk Revit updates.

---

## Reporting a Problem

Include:

- Workstation Manager version shown in the window header
- affected computer and Revit year or Flow application
- command used
- status message and expanded **Report details**
- whether the office folder was available
- a screenshot with confidential names and network paths obscured

---

## Related Help

- [Getting Started](getting-started.md)
- [Installing and Updating Revit Tools](installing-and-updating-tools.md)
- [Restoring Previous Tools](restoring-previous-tools.md)
- [Installing and Updating Flow Apps](installing-and-updating-apps.md)
- [Background Checks and Update Notices](background-checks-and-notices.md)

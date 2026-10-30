# Background Checks and Update Notices

Workstation Manager can check inventory and approved updates without requiring the main window to stay open.

---

## Automatic Checks

When the installed background task is enabled, checks run at login and every two hours while you are signed in. They do not wake the computer.

The checks save a local report, attempt delivery to the office folder and check for approved Flow updates.

Opening Workstation Manager also scans and attempts to check in.

!!! note "Checks do not install software"

    Background checks can report available updates and show a notice. Installation still requires a deliberate action.

---

## Reviewing Background Status

1. Open **Background checks**.
2. Select **Refresh check status**.
3. Review whether automatic checks are enabled, the last launch and the next scheduled check.
4. Review the latest background-check details and report delivery message.

Select **Run scheduled check now** to request a check without waiting for the next scheduled time. Refresh the status after the check has finished.

!!! info "A completed check and a delivered report are different"

    A scheduled process can finish successfully while the office folder is unavailable. Review the report delivery message as well as the process result.

---

## Update Notices

A Flow notice can appear when an approved newer release is available and the office folder can be reached.

The same update is normally limited to one reminder per day. Use **Review updates** to open Workstation Manager or **Remind me tomorrow** to defer the notice.

Custom release notes appear in Revit tools update notices where a note has been saved for that year and release.

**Preview update notice** on **This computer** lets you inspect the selected year's notice and saved note. **Preview app notice** on **Flow apps** shows an example Workstation Manager notice. Neither installs anything or consumes the normal reminder.

---

## The Red Update Number

The Flow icon beside the Windows clock shows a red number when known updates are available. Windows may place the icon under the hidden-icons arrow.

The number counts:

- each Revit year with an available Flow tools update
- each Flow application with an available update

For example, tools updates for two Revit years and one application update give a count of **3**.

Double-click the icon to open Workstation Manager. Right-click it to open the application or exit the update indicator.

!!! note "Where the number appears"

    The number appears on the notification-area icon beside the clock and on the taskbar button while the main Workstation Manager window is open or minimised. Desktop and Start menu shortcuts remain unchanged.

Closing the main window leaves the notification-area indicator running. If you exit the indicator, it can return at the next Workstation launch or scheduled check.

---

## Previewing the Indicator

1. Open **Background checks**.
2. Select **Preview update indicator**.
3. Look for a sample red **3** on the Flow icon beside the clock.
4. Allow approximately twelve seconds for the real count to return.

The preview does not create updates, change approved releases or alter reminder history.

<!-- Screenshot recommended:
Show the notification-area Flow icon with the sample 3 and its preview tooltip.
Crop out unrelated applications and identifying desktop information.
-->

---

## Working Offline

Workstation Manager keeps local inventory when the office folder is unavailable. Successful later checks refresh the report and update information.

The indicator retains its last known count while offline. Treat it as the last successful result rather than a fresh update check.

---

## Related Help

- [Installing and Updating Revit Tools](installing-and-updating-tools.md)
- [Installing and Updating Flow Apps](installing-and-updating-apps.md)
- [Troubleshooting](troubleshooting.md)

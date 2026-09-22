# Getting Started with Flow Server

Flow Server is installed as a standalone Windows desktop application. The installer also adds the Revit worker components required for supported archive and upgrade operations.

---

## Before You Start

You need:

- a 64-bit Windows workstation
- network access to the required Revit Server host
- the server address or IP address
- the relevant supported Revit installation for worker-based operations
- permission to install the application as an administrator
- suitable access to the local or network location used for archives

Flow Server can browse Revit Server 2025, 2026 and 2027. Archive workers are installed only where a compatible Revit installation is detected.

For Revit 2026 archiving, the installer requires Revit 2026.5 or later.

The current managed upgrade workflow targets Revit 2027 and requires Revit 2027 to be installed.

!!! note "Revit is used for archive and upgrade processing"

    Flow Server is a standalone application, but archive and upgrade jobs launch the appropriate installed Revit version in a separate worker session.

---

## Installing Flow Server

1. Close Flow Server and any worker sessions that are already running.
2. Run the supplied **Flow Server** setup file.
3. Approve the administrator prompt.
4. Complete the installation wizard.
5. Leave **Launch Flow Server** selected if you want to open the application immediately.

The installer creates:

- a **Flow Server** desktop shortcut
- a **Flow Server** entry under **Flow by Adapt** in the Start menu
- the main Flow Server application
- archive worker components for detected compatible Revit versions
- the Revit 2027 upgrade worker when Revit 2027 is installed

---

## Opening Flow Server

Open **Flow Server** from the desktop shortcut or Start menu.

The application opens with connection controls at the top and four main tabs:

- **Browse**
- **Activity**
- **Archive Queue**
- **Upgrade Workflow**

<!-- Screenshot recommended:
Show the complete Flow Server window immediately after opening.
Include the Server and Version controls, connection status and all four tabs.
Use a fictional or obscured server address.
-->

---

## Making the First Connection

1. Enter the Revit Server host address in **Server**.
2. Select the required Revit Server **Version**.
3. Select **Refresh**.
4. Wait for the connection indicator to show **Connected**.
5. Open the **Browse** tab and expand the required folder.

Flow remembers the last successfully used server address and Revit Server version.

See [Connecting and Browsing](connecting-and-browsing.md).

---

## About Flow Server

Select **About** to view the installed Flow Server version, application information and support details.

---

## Related Help

- [Flow Server](index.md)
- [Connecting and Browsing](connecting-and-browsing.md)
- [Archiving Projects](archiving-projects.md)
- [Upgrading Projects](upgrading-projects.md)
- [Troubleshooting](troubleshooting.md)
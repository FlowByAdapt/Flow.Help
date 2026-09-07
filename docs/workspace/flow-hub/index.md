# Flow Hub

The **Flow Hub** is Flow's persistent dockable workspace for finding and running Flow tools, native Revit commands and indexed library content.

It also provides quick access to pinned and recent commands, saved workspace layouts, window recovery and up to three preferred Visibility Manager controls.

---

## Open Flow Hub

On the Revit ribbon:

**Flow → Workspace → Hub**

Flow Hub opens as a dockable Revit panel.

You can keep it docked alongside panels such as **Properties** or the **Project Browser**, or leave it floating.

<!-- SCREENSHOT: Flow Hub immediately after opening.
Show the complete docked Hub with Search, Quick Actions, Pinned, Recent, Browse and the Workspace area visible. -->

---

## What You See When It Opens

When the Search box is clear, Flow Hub organises available commands into:

- **⚡ Quick Actions**
- **📌 Pinned**
- **🕘 Recent**
- **≡ Browse**

The first available result is selected automatically.

Flow Hub also provides a **Workspace** area for restoring layouts, recovering windows and using selected Visibility Manager shortcuts.

---

## First-Time Workflow

A typical Flow Hub workflow is:

1. Open **Flow → Workspace → Hub**.
2. Browse **Quick Actions**, **Pinned**, **Recent** or **Browse**, or start typing in **Search**.
3. Review the matching command and content results.
4. Select the required result.
5. Press **Enter**, double-click the result or select **Run Selected**.
6. Complete any additional Flow, Revit or content workflow that appears.

Search results update automatically as you type.

!!! tip "You do not need the exact name"

    Flow searches command names and additional searchable information such as aliases, keywords, descriptions and categories.

    Start with the word or phrase you associate with the task and refine the search if required.

---

## Quick Actions

Flow Hub includes a small set of predefined **Quick Actions** for common workflows.

The current Quick Actions include:

- **Open Command Palette**
- **Zero Window Sill**
- **Copy GP Setup**
- **Generate Views**
- **Recover Windows**

These appear when no search is active, provided the corresponding action is available in the current Revit context.

---

## Find and Run Tools

Flow Hub can search registered **Flow tools** and supported **native Revit commands**.

➡️ [**Finding and Running Tools**](finding-and-running-tools.md)

---

## Find and Load Content

When a search is active, Flow Hub can also search the indexed Revit content library.

Depending on the result, content can be opened in Content Browser, loaded into the project, revealed in Explorer or opened from its source file.

➡️ [**Finding and Loading Content**](finding-and-loading-content.md)

---

## Pinned and Recent Items

Pin commands you use regularly and return quickly to commands you have recently run.

Command pin and recent state is shared with **Command Palette**.

➡️ [**Pinned and Recent Items**](pinned-and-recent.md)

---

## Workspace Controls

The Hub Workspace area provides quick access to:

- saved workspace layouts;
- **Restore**;
- **Manage**;
- **Recover**;
- up to three preferred Visibility Manager shortcuts; and
- shortcut configuration.

➡️ [**Workspace Controls**](workspace-controls.md)

---

## What Flow Does Automatically

While you use Flow Hub, Flow automatically:

- updates search results as you type;
- removes actions that are not available in the current Flow context;
- selects the first available result;
- ranks commands using match quality and command usage;
- records commands that you run;
- shares command pin and usage state with Command Palette;
- uses Content Browser favourite and recent information when ranking library content;
- refreshes Workspace and visibility state when shared command state changes; and
- suggests a saved workspace that best matches the current monitor arrangement.

---

## Flow Hub or Command Palette?

Both interfaces use Flow's shared command infrastructure.

!!! tip "Which should I use?"

    Use **Flow Hub** when you want a persistent docked interface with search, commands, content and workspace controls available throughout the Revit session.

    Use **Command Palette** when you want a compact floating launcher that can be opened only when required.

See [**Command Palette**](../command-palette/index.md).

---

## Docking Flow Hub

Flow Hub is a Revit dockable panel and can be positioned to suit your normal working environment.

Its position can also be included in saved Flow workspace layouts.

See [**Workspace**](../index.md).

---

## Getting Help

Hover over **Hub** on the Flow ribbon and press **F1** to return directly to this page.

---

## Related Help

- [**Finding and Running Tools**](finding-and-running-tools.md)
- [**Finding and Loading Content**](finding-and-loading-content.md)
- [**Pinned and Recent Items**](pinned-and-recent.md)
- [**Workspace Controls**](workspace-controls.md)
- [**Troubleshooting**](troubleshooting.md)
- [**Command Palette**](../command-palette/index.md)

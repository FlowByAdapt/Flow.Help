# Pinned and Recent Commands

Command Palette keeps commonly used commands easier to access through **Pinned** and **Recent** command state.

Command pin and usage information is shared with **Flow Hub**, while library content uses its related **Content Browser** favourite and recent state.

---

## Pinned and Recent When Command Palette Opens

You do not need to search to access commands you use regularly.

When the Search box is empty, Command Palette can organise commands into:

* **Quick Actions**
* **Pinned**
* **Recent**
* **Browse**

This provides immediate access to useful commands before you start a search.

---

## Pinned Commands

Pin commands that you use frequently so they remain readily available through Flow's command interfaces.

### Pin a Command

1. Find the required command.
2. Select the **pin** control beside the command.

The command is added to your pinned commands.

### Unpin a Command

Select the pin control again to remove it.

!!! info "Pinning does not change the command"

	Pinning only changes how the command is presented in Flow's command interfaces.

	It does not enable, disable or otherwise modify the underlying Flow or Revit command.

---

## Recent Commands

Flow automatically records commands that you successfully run through its command interface.

Recently used commands can then be presented in the **Recent** section when Command Palette is opened without a search.

You can also use the **Recent** filter to focus the current results on recently used commands.

Select **Recent** again to turn the filter off.

!!! note "Recent is automatic"

	You do not need to manually add a command to Recent.

	Running commands through Flow builds the usage history automatically.

---

## Pinned or Recent?

Use **Pinned** for commands that form part of your regular workflow.

Use **Recent** when you want to return to commands you have been using lately.

!!! tip "A simple way to think about it"

```
**Pinned** = commands you regularly want close at hand.

**Recent** = commands you have been using lately.
```

---

## Shared with Flow Hub

Pinned command state and command usage are shared with **Flow Hub**.

For example:

1. Pin a command in Command Palette.
2. Open or return to Flow Hub.
3. The shared command state is refreshed automatically.

Likewise, running a command through Command Palette contributes to the command usage information available to Flow Hub.

You should not normally need to close and reopen either interface to synchronise this state.

See [**Pinned and Recent Items in Flow Hub**](../flow-hub/pinned-and-recent.md).

---

## Content Favourites and Recent Content

Library content is handled differently from Flow and Revit commands.

Content favourites and recent content are maintained through **Content Browser** state rather than the normal command pin and usage system.

Flow can use this information when ranking matching content in Command Palette searches.

This means content you regularly use or have marked as a favourite can receive greater priority when it matches your search.

!!! info "Commands and content use different state"

	**Flow and Revit commands** use Command Palette / Flow Hub pin and usage state.

	**Library content** uses Content Browser favourite and recent content state.

---

## Using the Recent Filter

The **Recent** filter applies to command usage.

It should not be treated as a replacement for the recent-content functionality available through Content Browser.

If a command you expect to see disappears:

1. Check whether **Recent** is active.
2. Turn the filter off.
3. Search again.

The **Flow** and **Recent** filters can also be combined when you specifically want recently used Flow commands.

---

## Search for Other Commands

Pinned and recent commands do not limit what is available through Command Palette.

Turn off **Recent** and use Search whenever you need to find another Flow or Revit command.

See [**Finding and Running Commands**](finding-and-running-commands.md).

---

## Related Help

* [**Command Palette**](index.md)
* [**Finding and Running Commands**](finding-and-running-commands.md)
* [**Flow Hub**](../flow-hub/index.md)
* [**Pinned and Recent Items in Flow Hub**](../flow-hub/pinned-and-recent.md)

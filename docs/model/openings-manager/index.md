# Openings Manager

The **Openings Manager** brings the main window, door and curtain-wall workflows into one place.

Use it to review opening standards, locate openings in the model, standardise marks, manage opening parameters, create and maintain opening views, tag openings, dimension window views and place opening views on sheets.

---

## Open Openings Manager

On the Revit ribbon:

**ADAPT → Model → Openings**

Openings Manager is a modeless window, so you can continue working in Revit while it remains open. If the Manager is already open, running **Openings** again returns you to the existing window rather than opening a second copy.

When the Manager first opens, Flow scans the current project for:

- Windows
- Doors
- Curtain walls

It then audits the discovered openings and displays the results in the **Opening Register**.

<!-- SCREENSHOT: Full Openings Manager window immediately after opening. Show the opening counts, filters, action buttons and Opening Register. Include one highlighted row and one checked row if possible. -->

---

## Understanding the Opening Register

The Opening Register is the starting point for most Openings Manager workflows.

Each row represents an opening discovered in the project. The register shows information including:

- **Category**
- **Mark**
- **Type**
- **Level**
- **Phase**
- **GP**
- **Head Height GP**
- **Status**

The counters at the top of the Manager show the number of **Windows**, **Doors**, **Curtain Walls** and **Total** openings currently discovered.

Use **Search**, **Category**, **Level**, **Phase**, **Tag Type** and **GP Status** to narrow down what you are reviewing.

!!! important "Row selection and checkboxes are different"

    Clicking a row selects that opening in Revit.

    The checkbox at the left of a row adds the opening to the working selection used by commands such as **Standardise**, **Generate Views** and **Tag**.

Changing the **Category**, **Level**, **Phase** or **GP Status** filter clears the current checked selection. Set your filters first, then check the openings you want to work with.

---

## Selecting and Locating Openings

The **Selection** tools help connect the register with the Revit model.

### Select Filtered

**Select Filtered** checks all openings currently visible through the register filters.

This is useful when you want to apply an operation to a particular category, level, phase or status.

### Select from Model

**Select from Model** switches Revit to the project view **3D-01-Work Main** and lets you pick elements directly in the model.

Openings that match your picks are checked in the register and briefly highlighted.

!!! note

    **3D-01-Work Main** must exist for this workflow. Flow does not automatically return to the view that was active before model selection.

### Focus

**Focus** locates one opening in Revit.

Flow uses the currently highlighted register row, or the first checked opening if no row is highlighted.

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

<!-- SCREENSHOT: Openings Manager beside the 3D-01-Work Main view after Select from Model, with the corresponding opening identified in Revit and checked in the register. -->

---

## Recommended First-Time Workflow

Openings Manager contains several related workflows. For a project that has not previously been processed through the Manager, the following sequence provides a useful starting point.

### 1. Review the Opening Register

Open **Openings Manager** and review:

- the Window, Door and Curtain Wall counts
- opening marks
- phases
- GP status
- Head Height GP status
- warnings or non-standard statuses

Use the filters and selection tools to investigate anything unexpected before making project-wide changes.

### 2. Resolve Opening Marks

Use **Standardise** when you want Flow to correct invalid or conflicting opening marks automatically.

When Standardise is run, choose whether to process the checked openings, the filtered openings or all openings, depending on the available scope.

Flow preserves valid unique marks where possible and assigns available numbers to openings that require correction.

Standardising also synchronises opening view names with their openings.

For deliberate sequential renumbering, use **Renumber** instead. This opens the guided renumbering workflow and lets you select openings in the model in the order you want them numbered.

➡️ [**Opening Marks**](opening-marks.md)

➡️ [**Guided Renumbering**](guided-renumbering.md)

<!-- SCREENSHOT: Register filtered to show an opening with a duplicate or non-standard mark, ideally paired with the corrected register after Standardise. -->

### 3. Review Opening Parameters

Use the **GP** and **Head Height GP** columns to identify openings whose Global Parameter setup requires attention.

Choose **Parameters Manager** to open the wider Flow parameter-management tools.

Openings Manager minimises while Parameters Manager is open and returns when Parameters Manager is closed.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

➡️ [**Head Height Overrides**](head-height-overrides.md)

### 4. Adjust Door Heights if Required

Use **Door Heights** to apply the standard door-height workflow.

This is a separate project-door workflow and does **not** use the checked rows in the Opening Register as its dashboard scope.

Flow works with applicable **New** doors, reuses a matching family type where one already exists, or creates the required type where necessary.

➡️ [**Door Heights**](door-heights.md)

### 5. Generate Window and Door Views

Choose **Generate Views**.

Select the required scope when prompted. Depending on the current register selection, this can be based on checked, filtered or all openings.

If the selected scope contains non-standard openings, Flow offers **Standardise Now**.

!!! important "Run Generate Views again after standardising"

    **Standardise Now** completes the standardisation workflow only.

    After it finishes, choose **Generate Views** again to create the opening views.

During view generation, Flow also performs supporting opening setup automatically, including the required Global Parameter setup and Window Size O/A updates used by the opening workflow.

Generated component views are for **New** openings. Window views are instance-based, while door elevations are based on door types.

Where the required project resources are available, Flow applies the opening-view standards and tags the generated elevations automatically.

➡️ [**Generating Opening Views**](generating-opening-views.md)

<!-- SCREENSHOT: A completed generated Window elevation showing the standard crop, opening tag and W## view name. -->

### 6. Generate Curtain Wall Views

Curtain wall elevations use the separate **Curtain Wall Views** command.

This is an interactive model-picking workflow rather than a checked-register workflow.

Flow attempts to begin from **X-01-GF_Win**. Pick a valid New curtain wall, then indicate the side from which its elevation marker should be created.

Valid curtain walls must use a Revit Curtain Wall type whose name begins with **CW_** and must be in the **New Construction** phase.

Flow standardises the selected curtain wall mark before the marker-side step, then creates and configures the elevation using the curtain-wall opening standards.

➡️ [**Generating Opening Views**](generating-opening-views.md)

### 7. Conform Existing Opening Views

Use **Conform Views** to bring existing opening elevations back into line with the current opening standards.

Choose either the active opening view or all opening views.

Depending on the resolved opening, Flow can:

- apply the standard view template and scale
- activate and adjust the crop
- clean up level datum extents
- rename the view from its opening
- add a missing opening tag
- update Window Size O/A information
- update curtain-wall metadata

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

### 8. Tag Openings in Plan

Use **Tag** from an active **Floor Plan**.

Choose a single opening category and the required tag type before running the command. A mixed Window/Door/Curtain Wall scope cannot be tagged in one operation.

Flow skips openings that are already tagged in the active view.

➡️ [**Tagging Openings**](tagging-openings.md)

### 9. Dimension Window Views

Choose **Dimension Window Views**, then select:

- **Active Window View**
- **All Window Views**

The batch workflow processes standard New Window views named **W##**. Existing **Wx##** views are not included in the all-window batch.

Curtain-wall views can use W## naming but are not dimensioned as Window family instances.

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

### 10. Place Opening Views on Sheets

Choose **Place on Sheet**, then choose the Window or Door placement workflow.

Window placement is a managed multi-sheet workflow. It begins from **A401**, finds unplaced New Window views, remembers placement progress and can continue across A4-series sheets.

If a previous Window placement session exists, Flow can resume it or reset it and start again.

➡️ [**Placing Views on Sheets**](placing-views-on-sheets.md)

### 11. Refresh and Review

Use **Refresh** after making changes to rebuild the Opening Register and review the resulting statuses.

!!! warning "Refresh can change the Revit model"

    Refresh is not a read-only rescan.

    Before rebuilding the register, Flow applies the **Zero Window Sill Height** Global Parameter rule to Windows. This ensures Window **Sill Height** is associated with the **Zero Window Sill Height** Global Parameter where required.

Review the register again after Refresh to confirm that marks, Global Parameters and statuses are as expected.

<!-- SCREENSHOT: Completed Opening Register after the main workflow, showing clean marks, GP information and opening statuses. -->

---

## What Flow Does Automatically

Some Openings Manager commands perform supporting work in addition to the action named on the button.

Depending on the workflow, Flow can automatically:

- audit opening marks and Global Parameter associations
- preserve valid unique marks while resolving invalid or conflicting marks
- synchronise opening view names during Standardise
- apply opening Global Parameter setup during view generation
- update **Window Size O/A**
- apply opening view templates, scale, crop settings and datum cleanup
- add elevation tags when the required tag families are available
- reuse or create suitable door types during Door Heights
- remember Window view-placement progress and placement areas
- toggle **Sheet Outline Show** during sheet placement when that Global Parameter exists
- enforce the **Zero Window Sill Height** rule when Refresh is run

Because several of these operations modify the Revit model, review the selected scope and any action prompts before continuing.

---

## Which Commands Use the Register Selection?

Not every Openings Manager command uses the checked rows.

| Command | Uses register selection? | How scope is determined |
| --- | --- | --- |
| **Standardise** | Yes | Checked, filtered or all openings |
| **Generate Views** | Yes | Checked, filtered or all openings |
| **Tag** | Yes | Selected scope must contain one opening category |
| **Renumber** | No | Openings are picked interactively in the model |
| **Door Heights** | No | Uses its own project-door workflow |
| **Curtain Wall Views** | No | Curtain walls are picked interactively in the model |
| **Conform Views** | No | Active opening view or all opening views |
| **Dimension Window Views** | No | Active Window view or all standard Window views |
| **Place on Sheet** | No | Uses the Window or Door placement workflow |

---

## Opening Standards and Project Requirements

Openings Manager is designed around the Flow opening standards and expects supporting Revit resources to be present in the project.

Important dependencies include:

- **3D-01-Work Main** for **Select from Model**
- opening documentation plans using the `_Win` convention, including workflows that look for **X-01-GF_Win**
- section type **5.6_WINDOW ELEVATIONS**
- view template **bc_SEC_WDW-SCHED**
- Flow/ADa opening tag families
- curtain-wall types beginning **CW_** for the curtain-wall elevation workflow
- appropriate opening Global Parameters
- **A401** for the Window sheet-placement workflow
- suitable family references for automatic Window dimensioning

Some workflows can continue when an optional resource is unavailable, while others cannot complete without their required project resource.

See the relevant workflow page or Troubleshooting for the specific requirement.

---

## Opening Workflows

### Review and Selection

Understand register statuses, filters and how to locate openings in Revit.

➡️ [**Reviewing Openings**](reviewing-openings.md)

➡️ [**Selecting and Locating Openings**](selecting-and-locating-openings.md)

### Marks and Standardisation

Review the opening mark conventions, automatically resolve non-standard marks, or deliberately renumber openings in model order.

➡️ [**Opening Marks**](opening-marks.md)

➡️ [**Standardising Openings**](standardising-openings.md)

➡️ [**Guided Renumbering**](guided-renumbering.md)

### Parameters and Door Heights

Review the opening Global Parameter setup, manage head-height overrides and standardise door heights.

➡️ [**Opening Global Parameters**](opening-global-parameters.md)

➡️ [**Head Height Overrides**](head-height-overrides.md)

➡️ [**Door Heights**](door-heights.md)

### Opening Views

Create, conform, dimension and place opening documentation views.

➡️ [**Generating Opening Views**](generating-opening-views.md)

➡️ [**Conforming Opening Views**](conforming-opening-views.md)

➡️ [**Dimensioning Window Views**](dimensioning-window-views.md)

➡️ [**Placing Views on Sheets**](placing-views-on-sheets.md)

### Tags

Apply opening tags to Windows, Doors or Curtain Walls in plan.

➡️ [**Tagging Openings**](tagging-openings.md)

---

## Troubleshooting

If a workflow does not behave as expected, check:

- that the required project view, sheet, tag family or Global Parameter exists
- that the opening category and phase are supported by the selected workflow
- that your checked selection still exists after changing filters
- that you are in a Floor Plan before using **Tag**
- that opening marks are standard before generating views
- that you rerun **Generate Views** after choosing **Standardise Now**
- that Window views use the expected W## naming for batch dimensioning

➡️ [**Openings Manager Troubleshooting**](troubleshooting.md)

---

## Getting Help

Hover over **Openings** on the ADAPT ribbon and press **F1** to return directly to this page.

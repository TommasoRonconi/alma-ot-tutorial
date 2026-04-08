---
layout: default
title: Tips and known issues
nav_order: 9
---

# Tips and known issues

This page collects practical tips, known issues, and workarounds for the web-based OT. Some of these are specific to the current implementation and may be resolved in future updates.

---

## General tips

### Use Tab, not Enter

{: .warning }
The **Enter** key does not work reliably in all input fields. Use the **Tab** key to move away from a field and trigger the save. This applies throughout the OT.

### Autosave is immediate and irreversible

The OT saves automatically — either when you leave a field (click away or press Tab) or after you stop typing for 500 ms in text fields (project name, abstract, duplicate observations). There is no undo and no version history.

{: .tip }
If you are about to make significant changes, make a copy of the proposal first using "Open project as new proposal". This gives you a safe fallback.

### Coordinate with your collaborators

All investigators (PI, CoPI, CoI) can edit the same proposal simultaneously. There is no locking mechanism and no conflict resolution — the last save wins.

{: .tip }
Establish a clear agreement within your team about who edits the proposal and when. Avoid having two people working on the same proposal at the same time.

### Clean up your staging area

Draft proposals accumulate in the staging area over time. Unlike submitted proposals, drafts can be deleted. Periodically review your drafts and delete those you no longer need — it makes it easier to find the proposals you are actively working on.

### Generate PDFs regularly

Use the **Generate PDF** button in the header bar to produce a PDF preview of your proposal as you work. This is useful for:

- Sharing the current state with collaborators who are not editing the OT directly.
- Proofreading — some formatting issues are easier to spot in a PDF than in the OT interface.
- Keeping a local record of your proposal at various stages (since the OT does not maintain version history).

---

## Known issues

### Band 2 Single Continuum wide setup

{: .warning }
> For Band 2, the **Single Continuum** spectral type only takes advantage of the broader IF range when using the **default sky frequency**. If you need a continuum observation at a non-default frequency with wider spectral window separation, set the spectral type to **Spectral Line** instead and configure the basebands manually as continuum windows with the desired frequency separation.
>
> This issue affects both the web-based and the desktop OT. It is documented in the [OT FAQ and known issues](https://almascience.eso.org/proposing/observing-tool/faq-and-known-issues) page.

### Spectral line picker: click away to search

When using the **Transition Filter** field in the spectral line picker, typing a molecule name and pressing Enter does not always trigger the search. You need to **click outside the filter field** (or press Tab) for the search to start.

### Spatial visualiser: pointings cannot be moved or removed

In the Aladin-based spatial visualiser, individual pointings can be **added** by clicking on the sky, but they currently **cannot be moved or removed** through the visualiser interface.

{: .tip }
> If you need fine control over pointing positions, define them in **CARTA** and import them into the OT via the import button. The file format must match the OT specification — see the [OT documentation](https://almascience.eso.org/proposing/observing-tool) for details.

### Spatial visualiser: Reset FOV resets overlays

The **"Reset FOV"** button resets not only the field of view but also any overlays that have been removed. If you have customised the overlay stack (e.g. removed some layers), pressing Reset FOV will restore them all.

### Spatial visualiser: no interactivity for rectangles

When using the **Rectangle** target type for mosaics, the rectangle cannot be dragged, resized, or rotated in the visualiser. All parameters (field centre, dimensions, position angle) must be entered numerically in the parameter panel.

### Mosaic reset when changing source

{: .warning }
When a source has been defined together with a mosaic setup and a **new source is subsequently loaded**, the web-based OT removes the mosaic setup. If you need to change the source coordinates for an existing mosaic, update the coordinates manually rather than loading a new source.

---

## Differences from the desktop OT

For users migrating from the desktop OT, here is a summary of the key behavioural differences:

{: .new }
> **Staging area replaces local files.** All proposals live on the server. There are no `.aot` files and no local saves.

{: .new }
> **Three proposal statuses.** Draft, Submitted, and Submitted with Unsubmitted Changes. The desktop OT did not distinguish between these states in the same way.

{: .new }
> **Draft deletion, submitted retraction.** Draft proposals can be deleted from the staging area. Submitted proposals can only be retracted via a helpdesk ticket.

{: .new }
> **Proposal cloning.** The "Open project as new proposal" function allows you to copy any proposal. This was not available in the desktop OT.

{: .new }
> **Multi-user access to drafts.** All investigators (PI, CoPI, CoI) have access to draft proposals. In the desktop OT, only the person with the `.aot` file could edit the proposal.

{: .new }
> **Autosaving replaces manual save.** There is no save button — changes are saved automatically and immediately. There is only one version of the proposal at any time.

{: .new }
> **Angular resolution: Single/Range merged into Custom.** In the desktop OT, "Single" and "Range" were separate options for the Desired Angular Resolution. In the web-based OT, both are handled under "Custom" — to request a single resolution, enter the same value in both the minimum and maximum fields.

---

## Useful resources

- [OT documentation](https://almascience.eso.org/proposing/observing-tool) — the official user and reference manual.
- [OT FAQ and known issues](https://almascience.eso.org/proposing/observing-tool/faq-and-known-issues) — maintained list of known problems and workarounds.
- [OT video tutorials](https://almascience.eso.org/proposing/observing-tool/video-tutorials) — video walkthroughs of the OT interface.
- [ALMA Proposer's Guide](https://almascience.eso.org/proposing/proposers-guide) — comprehensive guide to the proposal process, including policies, capabilities, and technical constraints.
- [ALMA Sensitivity Calculator](https://almascience.eso.org/proposing/sensitivity-calculator) — standalone sensitivity calculator (also accessible from the header bar within the OT).
- [Splatalogue](https://splatalogue.online/) — spectral line database for identifying transitions by molecule, frequency, and redshift.

---

[← Validation and submission](08_validation_and_submission.md) · [Home](../index.md)

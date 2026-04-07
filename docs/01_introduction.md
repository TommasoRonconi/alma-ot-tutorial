---
layout: default
title: Introduction
nav_order: 1
---

# Introduction

## Why are we here?

Starting from Cycle 13, the ALMA Observing Tool (OT) is no longer a desktop application. The Java-based tool that many of you have used for years has been replaced by a **web-based OT**, running entirely in your browser.

The transition brings some significant changes to the way you prepare and manage proposals. Some things will feel familiar; others will require adjusting your workflow. The goal of this tutorial is to guide you through the new tool, step by step, using a concrete science case as a running example.

## What has changed

The most important differences between the desktop OT and the web-based OT are summarized below.

{: .new }
> **No local files.** Proposals are no longer saved as `.aot` files on your computer. Everything lives on the server. There is no "save to disk" option, and `.aot` files from previous cycles cannot be imported into the new tool. If you have an unsubmitted proposal from a previous cycle that you want to reuse, you will need to recreate it from scratch.

**Autosaving.** The web-based OT saves your work automatically. For text fields (project name, abstract, duplicate observations), the save is triggered after you stop typing for 500 ms. For all other fields, saving happens when you click away from the field. There is only one version of a proposal at any time — each autosave overwrites the previous state.

**Multi-user access.** All investigators listed on a proposal (PI, CoPI, CoI) have access to the same draft. This is convenient for collaboration, but it also means that two people editing the same proposal simultaneously can overwrite each other's changes without warning. Clear communication among collaborators about who is editing and when is essential.

{: .tip }
If you want to test a different observing strategy or let a collaborator experiment, make a copy of the proposal first using "Open project as new proposal". This creates an independent draft.

**Proposal statuses.** Proposals in the staging area can be in one of three states: *Draft*, *Submitted*, or *Submitted with Unsubmitted Changes*. Draft proposals can be deleted. Submitted proposals can only be retracted via a helpdesk ticket. If a submitted proposal has unsubmitted changes, you can revert it to the last submitted version — but the unsubmitted changes will be lost.

**Copying proposals.** You can make a copy of any proposal (draft or submitted) via the "Open project as new proposal" function. The copy is created in draft status. This is useful for testing different observing strategies without modifying your original proposal.

{: .warning }
Use the **tab** key rather than Enter to move between fields. The Enter key does not work reliably in all input fields of the web-based OT.

## What has stayed the same

The scientific content of a proposal — science goals, field setup, spectral setup, calibration, control and performance, technical justification — follows the same logic as in the desktop OT. If you have prepared ALMA proposals before, the concepts and the information you need to provide are unchanged. The interface is different, but the workflow is not.

## How this tutorial is organized

We will walk through the proposal preparation process in the order you would naturally encounter it in the OT. Along the way, we will use a concrete science case — Band 7 observations of the Cosmic Eyelash, a gravitationally lensed starburst galaxy at z = 2.3 — as a running example.

A separate [science background](docs/06_science_background.md) page covers the technical foundations (flux estimation, largest recoverable scale, ACA usage, spectral line sensitivity) that apply regardless of the specific proposal you are preparing. If you are new to interferometry or to ALMA, you may want to read that page first.

---

[Next: Before you start →](02_before_you_start.md)

---
layout: default
title: Before you start
nav_order: 2
---

# Before you start

Before opening the OT, you should have a clear picture of what you want to observe and why. The OT is a tool for translating your science case into a technical specification — it is not the place to figure out your science case from scratch.

Here is what you should have ready.

## A science case

This may sound obvious, but the proposal process goes much more smoothly when you have already thought through the key questions: What do you want to observe? What physical quantity do you want to measure or constrain? What angular resolution and sensitivity do you need to achieve your science goals?

## Source information

For each target you plan to observe, you will need:

- **Coordinates** (RA, Dec) in the ICRS/J2000 system
- **Radial velocity** or **redshift** (if relevant)
- **Proper motion** (if relevant, e.g. for solar system objects or nearby stars)

{: .tip }
You can use the "Resolve source" button in the OT to look up coordinates by source name (it queries SIMBAD/NED). However, it is good practice to verify the coordinates independently, especially for sources with multiple components or poorly defined centres.

## Observing frequency and spectral setup

You should know:

- Which **receiver band** you need (Bands 1–10)
- The **rest frequency** of the spectral line(s) you want to observe, or the frequency range for continuum observations
- The **spectral resolution** required by your science (e.g., channel width in km/s)
- Whether you need **TDM** (low spectral resolution, 2 GHz bandwidth per baseband) or **FDM** (high spectral resolution, narrower bandwidth)

{: .tip }
> [Splatalogue](https://splatalogue.online/) is useful for identifying which spectral lines fall within a given ALMA band at a given redshift. You can filter by band, redshift, and molecule.
>
> The OT also has a built-in **spectral line picker**, but it is based on an offline catalogue and does not contain all transitions. If your line is not listed, you can add it manually by entering the rest frequency directly.

## Angular resolution and largest angular scale

You should have estimates of:

- The **angular resolution** needed to resolve the structures you are interested in
- The **largest angular structure (LAS)** present in your source

The angular resolution determines which array configuration(s) are needed. The LAS determines whether you need ACA (the Atacama Compact Array) to recover extended emission that the 12m array would filter out.

{: .note }
> If the largest angular scale of your source is smaller than the maximum recoverable scale (MRS) of the requested configuration, ACA is not needed. If it is larger, you should request ACA observations. See the [science background](06_science_background.md) page for details on how to estimate this.
>
> Once the resolution and LAS are defined the OT automatically defines which configuration you need and if you should combine more 12m configurations, ACA or the Total Power (TP) array. No extra action is needed.

## Required sensitivity

You need to estimate the **rms noise level** required to detect your source at the desired signal-to-noise ratio. This depends on whether you are observing continuum or spectral lines, and on the assumed source morphology (point source vs. extended).

For spectral line observations, the relevant quantity is the **peak flux density** (in mJy) of the line in a single velocity channel of the width you plan to use. The rms you request in the OT should be the peak flux divided by your desired S/N.

{: .note}
All the fluxes that are shown or that have to be inserted in the OT are intended to be *per synthesized beam* 

{: .important }
> The sensitivity you need to request depends critically on assumptions about the source morphology. A source that is unresolved at the resolution of previous observations may break up into multiple resolved components at ALMA's resolution. This can change the required rms by orders of magnitude.
>
> See the [science background](06_science_background.md) and [worked example](07_worked_example.md) pages for a detailed discussion of this issue.

## Dynamic range

If your field contains a bright source alongside the faint emission you want to detect, you may need to consider dynamic range limitations. ALMA's standard imaging dynamic range is of the order of a few hundred to one. Higher dynamic range may require self-calibration or special observing strategies.

## Summary checklist

Before you open the OT, make sure you have:

- [ ] A well-defined science case
- [ ] Source coordinates and redshift/velocity
- [ ] Receiver band and rest frequency of your line(s)
- [ ] Required spectral resolution
- [ ] Required angular resolution
- [ ] Estimate of the largest angular scale in your source
- [ ] Required rms sensitivity (and the assumptions behind it)

It might also be a good idea to 

- [ ] check if it might be a duplication of previous observations

**With all of this in hand, you are ready to open the OT and start building your proposal.**

{: .note}
> Experienced users will also have:
> - [ ] An estimate of the requested time (to say if it is a large or a standard project)
> - [ ] An idea whether the observation is time-constrained, requires full-Stokes polarimetry, or requires specific observing modes (e.g. VLBI, Phased array, Target of Opportunity, Joint project)

---

[← Introduction](01_introduction.md) · [Next: Navigating the Web OT →](03_navigating_the_web_ot.md)

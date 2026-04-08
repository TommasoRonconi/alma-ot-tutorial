---
layout: default
title: "Worked example: the Cosmic Eyelash"
nav_order: 7
---

![Under construction](../images/under_construction.png)

{: .warning}
This page is under construction

# Worked example: the Cosmic Eyelash

This page walks through a complete proposal preparation, applying the concepts from the [science background](06_science_background.md) to a concrete case. The goal is not just to show you which buttons to click, but to illustrate the reasoning behind each technical choice.

---

## The science case

We want to observe the **Cosmic Eyelash** (i.e. SMM J2135-0102), a gravitationally lensed starburst galaxy at $z = 2.3$. The goal is to resolve the continuum and molecular gas emission at high angular resolution using ALMA Band 7.

The target observations are:
- **CO(9-8)** line emission (rest frequency $\nu_\mathrm{rest} = 1036.91\;\mathrm{GHz}$, observed at $\sim 314.2\;\mathrm{GHz}$ at $z = 2.3$)
- **Band 7 continuum** (around $312\;\mathrm{GHz}$)

---

## Previous observations

We base our planning on two existing datasets:

### SMA continuum at 850 μm (Band 7)

- Angular resolution: $\theta_\mathrm{SMA} = 0.2''$
- Source angular extent: $\sim 5''$
- Multiple resolved components (labelled A1, A2, B1, B2, C1, C2, D1, D2 in the literature)
- Largest angular structure of individual components: $\sim 1''$
- Total flux density: $S_\mathrm{tot} = 86\;\mathrm{mJy}$
- Faintest component: $\sim 6\;\mathrm{mJy}$ ($3\sigma$ detection) <span style="color:red">**[CHECK: f.c. acronym interpreted as "faintest component"]**</span>

<!-- IMAGE NEEDED: cosmic_eyelash_sma.png -->
![SMA continuum image of the Cosmic Eyelash](../images/cosmic_eyelash_sma.png)

<span style="color:red">**[IMAGE REQUIRED: SMA 850 μm continuum image of the Cosmic Eyelash showing the multiple lensed components. Annotate with arrows indicating the total source extent (~5″) and the largest angular scale of individual components (~1″). Mark the synthesized beam in the corner. This grounds the entire worked example — it shows the source morphology driving all subsequent estimates. A schematic diagram of the component layout is acceptable if the original published figure cannot be used.]**</span>

### PdBI CO(3-2) at 104.5 GHz (Band 3)

- Angular resolution: $\theta_\mathrm{PdBI} = 1''$
- Gaussian line profile with $\mathrm{FWHM} \approx 600\;\mathrm{km\;s^{-1}}$
- Integrated flux: $F[\mathrm{CO(3\text{-}2)}] = 13.8\;\mathrm{Jy\;km\;s^{-1}}$
- Peak flux density: $F_\mathrm{peak}[\mathrm{CO(3\text{-}2)}] = F[\mathrm{CO(3\text{-}2)}] / \mathrm{FWHM} = 13.8 / 600 \approx 23\;\mathrm{mJy}$
- Source unresolved at $\theta_\mathrm{PdBI} = 1''$

<!-- IMAGE NEEDED: cosmic_eyelash_co32.png -->
![PdBI CO(3-2) spectrum](../images/cosmic_eyelash_co32.png)

<span style="color:red">**[IMAGE REQUIRED: PdBI CO(3-2) spectrum showing the Gaussian-like line profile with FWHM ~600 km/s. Annotate with the FWHM, the peak flux (~23 mJy), and the integrated flux (13.8 Jy km/s). This is the starting point for estimating the CO(9-8) flux.]**</span>

---

## Choosing the observing band and line

We want CO(9-8), which has a rest frequency of $1036.91\;\mathrm{GHz}$. At $z = 2.3$, the observed frequency is:

$$
\nu_\mathrm{obs} = \frac{\nu_\mathrm{rest}}{1 + z} = \frac{1036.91}{3.3} \approx 314.2\;\mathrm{GHz}
$$

This falls within ALMA **Band 7** ($275$–$373\;\mathrm{GHz}$).

{: .tip }
> You can use [Splatalogue](https://splatalogue.online/) to check which CO transitions fall in a given ALMA band at a given redshift. Select the molecule (CO), the band (Band 7), and enter the redshift. At $z = 2.3$ in Band 7, the available CO transitions are $J = 8$–$7$ ($279.3\;\mathrm{GHz}$), $J = 9$–$8$ ($314.2\;\mathrm{GHz}$), and $J = 10$–$9$ ($349.1\;\mathrm{GHz}$).

---

## Angular resolution and largest angular scale

### Required angular resolution

The SMA continuum observations resolve the source into multiple components at $\theta_\mathrm{SMA} = 0.2''$. To resolve these same components with ALMA, we request a similar angular resolution:

$$
\theta_\mathrm{ALMA} \approx 0.2''
$$

In Band 7, ALMA configurations provide angular resolutions ranging from <span style="color:red">**[CHECK: verify angular resolution range for Cycle 13 Band 7 — Cycle 2 value was $0.13''$–$1.19''$]**</span>, so $0.2''$ is well within the accessible range.

### Largest angular scale

From the SMA image, the individual components have angular sizes of $\sim 1''$ or less. The total source extent is $\sim 5''$, but the emission is not uniform — it consists of discrete, compact components. The relevant LAS for our science is the size of the largest individual component, approximately $1''$.

### Do we need ACA?

From the Configuration Information tab in the OT (or from the configuration tables):

- Most extended 12m configuration at $314\;\mathrm{GHz}$: $\mathrm{MRS} \approx$ <span style="color:red">**[CHECK: verify MRS for most extended 12m config at 314 GHz in Cycle 13 — Cycle 2 value was $2.9''$]**</span>
- Most compact 12m configuration at $314\;\mathrm{GHz}$: $\mathrm{MRS} \approx$ <span style="color:red">**[CHECK: verify MRS for most compact 12m config at 314 GHz in Cycle 13 — Cycle 2 value was $8.3''$]**</span>

Our estimated LAS of $1''$ is well below the MRS even for the most extended configuration. **ACA is not needed.**

{: .note }
If the source had significant smooth emission on scales of several arcseconds (e.g. a diffuse halo around the lensed components), we would need to consider ACA. But based on the SMA image, the emission is concentrated in compact components.

---

## Estimating the CO(9-8) flux

We have not observed CO(9-8) directly. We estimate its flux from the CO(3-2) observations using assumptions about the CO spectral line energy distribution (SLED):

**Assumptions:**
- CO(9-8) has a Gaussian profile with FWHM similar to CO(3-2): $\mathrm{FWHM} \approx 600\;\mathrm{km\;s^{-1}}$
- The $\mathrm{CO(3\text{-}2)/CO(9\text{-}8)}$ flux ratio is approximately $2.5$ (motivated by models and observations of similar high-redshift starbursts)

This gives:

$$
F[\mathrm{CO(9\text{-}8)}] = \frac{F[\mathrm{CO(3\text{-}2)}]}{2.5} = \frac{13.8}{2.5} = 5.52\;\mathrm{Jy\;km\;s^{-1}}
$$

$$
F_\mathrm{peak}[\mathrm{CO(9\text{-}8)}] = \frac{F[\mathrm{CO(9\text{-}8)}]}{\mathrm{FWHM}} = \frac{5.52}{600} \approx 9.2\;\mathrm{mJy}
$$

{: .warning }
> These are estimates based on assumed line ratios. The actual CO(9-8) flux could be higher or lower depending on the excitation conditions. State your assumptions clearly in the scientific justification and technical justification of the proposal.

---

## Required sensitivity

This is where the source morphology assumptions become critical. We want $\mathrm{S/N} = 20$ on the CO(9-8) peak. But the required rms depends on what we assume about the source structure at $0.2''$ resolution.

### Case 1: source unresolved at $\theta_\mathrm{ALMA}$

If the CO(9-8) emission remains unresolved at $\theta_\mathrm{ALMA} = 0.2''$ (i.e. the emitting region is smaller than $0.2''$), then the peak flux per beam is the same as the total peak flux:

$$
\mathrm{rms} = \frac{F_\mathrm{peak}}{\mathrm{S/N}} = \frac{9.2}{20} \approx 0.5\;\mathrm{mJy}
$$

### Case 2: source resolved into one extended component

If the emission is unresolved at $\theta_\mathrm{PdBI} = 1''$ but will be resolved by ALMA into a single component of angular size $D \approx \theta_\mathrm{PdBI} = 1''$ with uniform surface brightness:

$$
\mathrm{rms} = \frac{F_\mathrm{peak} \times R}{\mathrm{S/N}}
\quad\text{where}\quad
R = \left(\frac{\theta_\mathrm{ALMA}}{\theta_\mathrm{PdBI}}\right)^2 = \left(\frac{0.2}{1}\right)^2 = 0.04
$$

$$
\mathrm{rms} = \frac{9.2 \times 0.04}{20} \approx 0.02\;\mathrm{mJy}
$$

### Case 3: source resolved into $N$ components

If the emission is resolved into $N = 5$ components (guided by the SMA continuum morphology), each with angular size $D_\mathrm{cc} = 0.8''$, with the flux equally and uniformly distributed among them:

$$
\mathrm{rms} = \frac{(F_\mathrm{peak}/N) \times R_N}{\mathrm{S/N}}
\quad\text{where}\quad
R_N = \left(\frac{\theta_\mathrm{ALMA}}{D_\mathrm{cc}}\right)^2 = \left(\frac{0.2}{0.8}\right)^2 = 0.0625
$$

$$
\mathrm{rms} = \frac{(9.2/5) \times 0.0625}{20} \approx 0.006\;\mathrm{mJy}
$$

### Summary of the three cases

| Assumption | rms required |
|---|---|
| Unresolved at $0.2''$ | $\sim 0.5\;\mathrm{mJy}$ |
| 1 component, $D \approx 1''$, uniform | $\sim 0.02\;\mathrm{mJy}$ |
| 5 components, $D_\mathrm{cc} \approx 0.8''$, uniform | $\sim 0.006\;\mathrm{mJy}$ |

{: .important }
> The required sensitivity spans nearly two orders of magnitude depending on the assumed morphology. For this source, the SMA continuum data show resolved, compact components, so Case 1 (unresolved) is the most realistic assumption for the individual clumps. We adopt $\mathrm{rms} \approx 0.5\;\mathrm{mJy}$ in a $100\;\mathrm{km\;s^{-1}}$ channel.

---

## Bandwidth used for sensitivity

The CO(9-8) line has an expected $\mathrm{FWHM} \sim 600\;\mathrm{km\;s^{-1}}$. If we want approximately 6 independent velocity channels across the line profile, we need a channel width of $\sim 100\;\mathrm{km\;s^{-1}}$.

The "Bandwidth used for Sensitivity" in the OT should therefore be set to $100\;\mathrm{km\;s^{-1}}$.

{: .note }
This is the velocity resolution at which the requested rms ($0.5\;\mathrm{mJy}$) will be achieved. The native spectral resolution of the correlator will typically be much finer — you average channels in post-processing to reach the desired velocity resolution.

---

## Continuum sensitivity

For the continuum, we use 3 of the 4 basebands (the fourth is allocated to CO(9-8)), giving an aggregate bandwidth of approximately $6\;\mathrm{GHz}$ ($3 \times \sim 2\;\mathrm{GHz}$).

From the SMA data, the faintest continuum component has a flux of $\sim 6\;\mathrm{mJy}$ at $0.2''$ resolution. If we want to detect it at $\sim 15\sigma$, we need:

$$
\mathrm{rms}_\mathrm{cont} \approx \frac{1\;\mathrm{mJy}}{15} \approx 0.07\;\mathrm{mJy}
$$

With $6\;\mathrm{GHz}$ aggregate bandwidth and the integration time driven by the line sensitivity requirement, the continuum rms achieved is typically well below this threshold. In other words, the continuum is "for free" — the time needed for the line observations already provides more than sufficient continuum sensitivity.

---

## Spectral setup in the OT

The spectral setup for this observation uses **Spectral Line** type with **DUAL** polarisation:

- **Baseband 1** — continuum, centre frequency $\sim 313.0\;\mathrm{GHz}$ (sky), TDM
- **Baseband 2** — CO(9-8), centre frequency $\sim 314.2\;\mathrm{GHz}$ (sky), TDM. This baseband is selected as the **Representative Window**.
- **Baseband 3** — continuum, centre frequency $\sim 301.0\;\mathrm{GHz}$ (sky), TDM
- **Baseband 4** — continuum, centre frequency $\sim 302.0\;\mathrm{GHz}$ (sky), TDM

<!-- IMAGE NEEDED: worked_example_spectral_setup.png -->
![Spectral setup for the Cosmic Eyelash](../images/worked_example_spectral_setup.png)

<span style="color:red">**[IMAGE REQUIRED: OT screenshot of the spectral setup for this observation. Show the frequency visualisation panel with the four basebands placed (one on CO(9-8), three on continuum), and the baseband table below showing the centre frequencies, transitions, bandwidths, and the Representative Window selection. This is the payoff screenshot — it shows what a correctly configured spectral setup looks like for a realistic observation.]**</span>

{: .tip }
In TDM mode, each baseband provides <span style="color:red">**[CHECK: verify TDM bandwidth and channel count for Cycle 13 — expected $\sim 2\;\mathrm{GHz}$ bandwidth with 128 channels, giving $\sim 15.6\;\mathrm{MHz}$ or $\sim 30\;\mathrm{km\;s^{-1}}$ channel width at $314\;\mathrm{GHz}$]**</span>. Since we need $100\;\mathrm{km\;s^{-1}}$ channels for the line sensitivity, we will average $\sim 3$ channels in post-processing.

---

## Control and Performance settings

In the Desired Performance sub-tab:

| Parameter | Value |
|---|---|
| Desired Angular Resolution | Custom: $0.2''$ to $0.2''$ |
| Largest Angular Structure in source | $1.0''$ |
| Desired mosaic sensitivity | $0.5\;\mathrm{mJy}$ |
| Bandwidth used for Sensitivity | User, $100\;\mathrm{km\;s^{-1}}$ |
| ACA | No |
| Time-constrained | No |

<!-- IMAGE NEEDED: worked_example_control_performance.png -->
![Control and Performance for the Cosmic Eyelash](../images/worked_example_control_performance.png)

<span style="color:red">**[IMAGE REQUIRED: OT screenshot of the Desired Performance sub-tab filled in with the values from the table above. This confirms that the numbers computed in the previous sections translate directly into specific OT fields.]**</span>

---

## Time estimate

After entering all the parameters, navigate to the **Planning and Time Estimate** sub-tab to see the estimated observing time.

For this example, the OT gives an estimated total time of approximately <span style="color:red">**[CHECK: re-run the time estimate in the Cycle 13 OT — Cycle 2 value was $\sim 45$ minutes total, with $\sim 12$ min on source, $\sim 19$ min on calibrators, $\sim 14$ min overheads. The Cycle 13 value will differ due to changes in the number of antennas, overhead model, and correlator configuration.]**</span>.

<!-- IMAGE NEEDED: worked_example_time_estimate.png -->
![Time estimate for the Cosmic Eyelash](../images/worked_example_time_estimate.png)

<span style="color:red">**[IMAGE REQUIRED: OT screenshot of the Planning and Time Estimate sub-tab showing the full time breakdown for this science goal. Include the input parameters summary, the estimated total time, the source table, the configuration combinations, and the calibration breakdown. This is a sanity-check screenshot — users can compare their own time estimates against this example.]**</span>

---

## Technical justification

The technical justification for this science goal would cover:

**Sensitivity:**  
We request an rms of $0.5\;\mathrm{mJy}$ in $100\;\mathrm{km\;s^{-1}}$ channels at the representative frequency of $314.2\;\mathrm{GHz}$. This gives $\mathrm{S/N} \approx 20$ on the expected CO(9-8) peak flux of $\sim 9.2\;\mathrm{mJy}$ per beam, assuming the emission is concentrated in compact components unresolved at $0.2''$ (consistent with the SMA continuum morphology). The aggregate continuum bandwidth of $\sim 6\;\mathrm{GHz}$ gives a continuum rms of <span style="color:red">**[CHECK: verify continuum rms from the Cycle 13 OT — Cycle 2 value was $\sim 0.07\;\mathrm{mJy}$]**</span>, providing $\mathrm{S/N} > 15$ on the faintest continuum component ($\sim 1\;\mathrm{mJy}$).

**Imaging:**  
We request $0.2''$ angular resolution to match the SMA continuum resolution at 850 μm and resolve the known lensed components. The largest angular structure is $\sim 1''$ (individual components), well within the MRS of the 12m array in even the most extended configuration (<span style="color:red">**[CHECK: verify MRS for the most extended config at $314\;\mathrm{GHz}$ in Cycle 13 — Cycle 2 value was $\sim 2.9''$]**</span>). ACA is not needed.

**Correlator configuration:**  
We use TDM with 4 basebands: one centred on CO(9-8) at $314.2\;\mathrm{GHz}$ and three on continuum. The native TDM resolution of <span style="color:red">**[CHECK: verify TDM native resolution at $314\;\mathrm{GHz}$ for Cycle 13]**</span> is adequate; we will average $\sim 3$ channels to reach $100\;\mathrm{km\;s^{-1}}$ for the line analysis. This gives $\sim 6$ independent velocity channels across the expected CO(9-8) FWHM of $600\;\mathrm{km\;s^{-1}}$.

---

## Entering expected source properties

In the Field setup, the Expected Source Properties should be filled in as:

| Field | Value | Rationale |
|---|---|---|
| Peak Continuum Flux Density per Synthesized Beam | $0.006\;\mathrm{Jy}$ ($6\;\mathrm{mJy}$) | Brightest component from SMA at similar resolution |
| Peak Line Flux Density per Synthesized Beam | $0.0092\;\mathrm{Jy}$ ($9.2\;\mathrm{mJy}$) | Estimated CO(9-8) peak flux (Case 1: unresolved) |
| Line Width | $600\;\mathrm{km\;s^{-1}}$ | From CO(3-2) FWHM |

{: .tip }
The OT uses these values to compute S/N estimates displayed in the Technical Justification summary. Make sure they are consistent with the sensitivity you requested — if they are not, the S/N displayed will look wrong and reviewers may notice the inconsistency.

---

[← Science background](06_science_background.md) · [Next: Validation and submission →](08_validation_and_submission.md)

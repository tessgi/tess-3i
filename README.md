# TESS - 3I/ATLAS 
---

This repository contains information on the data reduction and analysis for the High Level Science Products (HLSP) created by the TESS Science Support Center (TSSC) for the observations of 3I/ATLAS performed in 2026. If you use these in your work, please cite Martinez-Palomera et al. (2026, to be submitted) (Research note describing the creation of these in detail) and the [Zenodo data repository](https://doi.org/10.5281/zenodo.18344942). This work is based off the data analysis and reduction in [Martinez-Palomera et al. (2025)](https://ui.adsabs.harvard.edu/abs/2025ApJ...994L..51M/abstract).

## January 2026 Data

TESS observed a field contained 3I/ATLAS (Sector 1751) between January 16th and 22nd, 2026.. 
For further details on TESS sector 1751 observations visit the [TSSC website](https://heasarc.gsfc.nasa.gov/docs/tess/tess-special-news-bulletin-dec-18th.html).

> **<font color="salmon">As of January 24, 2026, 513 full frame images processed by the SPOC pipeline have been archived, corresponding to observations between 2026-01-15 06:04:18 and 2026-01-19 05:36:52 UTC.</font>**

The data created here are available in a [Zenodo repository](https://doi.org/10.5281/zenodo.18344942) that will be updated with new data as soon as newly processed full frame images are available at the MAST archive. 
We will also update this repository with new data products, figures, and details as more data becomes available at the MAST archive.

Here, you'll find dedicated notebooks to:
* Create object-centered moving TPF from TESS sector 1751 using [tess-asteroids](https://altuson.github.io/tess-asteroids/), which models the scattered background light and star field and extracts lightcurves using aperture and PSF photometry. 
  * Using the SPOC full-frame images [here](notebooks/2026/make_mTPF_from_ffi.ipynb).
* Open the data products published in this [Zenodo](https://doi.org/10.5281/zenodo.18344942) repository, [here](notebooks/2026/open_hlsp_data.ipynb).

Below are animations of the TESS observations of 3I/ATLAS with the raw (left) and corrected (right) images. The corrected images are background (scattered light and stars) subtracted. The bright pixels in the field are residuals from the background subtraction, primarily from very bright stars.
<p float="left">
    <img alt="TESS stacked images" src="data/2026/figures/tess_3iatlas_spoc_s1751a_tp_raw.gif" width="49%">
    <img alt="TESS stacked images" src="data/2026/figures/tess_3iatlas_spoc_s1751a_tp_corrected.gif" width="49%">
</p>


Below are the light curves extracted from the data. We defined two aperture masks, one for the core (blue) and another for the core plus tail (orange). Additionally we computed PSF photometry which only accounts for the comet nucleus (green).
The noisier photometric points near BTJD 4056.4 are due to a bright saturated star. The ramped change in brightness in the total flux (orange) at the beginning and end of each segment are due to edge effect in the background star model which affected the tail of the comet. 
<p align="center">
    <img alt="TESS Light Curve" src="data/2026/figures/tess_3iatlas_spoc_s1751a_lc.png" width="100%">
</p>

Below is a clean version of the light curve after removing cadences with high background model noise due to the saturated star. We also highlighted times when the comet passed over background stars. The increase in brightness in the PSF photometry during the second segment of data should be investigated when the next orbit data is included.
<p align="center">
    <img alt="TESS Light Curve" src="data/2026/figures/tess_3iatlas_spoc_s1751a_lc_clean.png" width="100%">
</p>


If you have questions regarding data processing, access, content, and suggestions on how to improve them in future versions, contact us through the [TSSC helpdesk](https://heasarc.gsfc.nasa.gov/docs/tess/helpdesk.html), GitHub issues in this repository, or via email.

#### Credits
Development done by [Jorge Martinez-Palomera](https://github.com/jorgemarpa) with the support of the [TESS Science Support Center](https://heasarc.gsfc.nasa.gov/docs/tess/). Based on the `tess-asteroids` package developed by [Amy Tuson](https://github.com/altuson).

---

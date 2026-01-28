# TSSC comet-centered data products from TESS 3I/ATLAS observations.

NASA's TESS performed dedicated observations of the comet 3I/ATLAS during January 15 and 22, 2026. These observations have been split into two segments, due to spacecraft orbit and data downlink. For more details on these observations visit the [TESS Science Support Center (TSSC)](https://heasarc.gsfc.nasa.gov/docs/tess/tess-special-observation-of-interstellar-comet-3iatlas-update-jan-16th.html) webpage. 

> Data version 1.0 includes TESS observations between 2026-01-15 06:04:18 and 2026-01-19 05:36:52 UTC. New versions will be uploaded as new observations become available.

The TSSC presents high level data products that contain the pixel corrected flux and the comet light curve. This document describe the data products contained in this folder which are of two types.

Target Pixel File
---
`hlsp_tess-3i_tess_ffi_3iatlas-s1751-cam2-ccd3_tess_v1.1_tp.fits`
Is a multi extension FITS file with the image time series. The `PIXELS` extension contains the image timeseries centered on the comet, the `APERTURE` extension has an example aperture mask used for photometry. The `EXTRA` extension has arrays that help to characterize the data.

```
Filename: ../../data/2026/hlsp_tess-3i_tess_ffi_3iatlas-s1751-cam2-ccd3_tess_v1.1_tp.fits
No.    Name      Ver    Type      Cards   Dimensions 
  0  PRIMARY       1 PrimaryHDU      48   ()   
  1  PIXELS        1 BinTableHDU    204   513R x 10C 
  2  APERTURE      1 ImageHDU        43   (91, 91)   
  3  EXTRAS        1 BinTableHDU     40   513R x 8C  
```

NOTE: the WCS stored in the `PIXELS` and `APERTURE` extension are dummy solutions and only included to meet the TPF-like data structure. Because the target moves across the target, the pixel grid changes in time and therefore the reference frame at each frame changes too. If you want to recover the WCS solutions we recommend using `tesswcs` to access the archive of solutions per sector/camera/CCD and times. A tutorial on how to do this can be found in our GitHub tutorials (see below).

Light Curve File
---
`hlsp_tess-3i_tess_ffi_3iatlas-s1751-cam2-ccd3_tess_v1.1_lc.fits`
Is a multi extension FITS file with the extracted light curves. There are 4 binary tables in the file, two dedicated to aperture photometry, `LIGHTCURVE_AP0` which has the nucleus photometry, `LIGHTCURVE_AP1` which has the nucleus and tail.
The `LIGHTCURVE_PSF` extension has the PSF photometry of the nucleus, and an `EXTRA` extension with additional 
arrays that help to characterize the data.

```
Filename: ../../data/2026/hlsp_tess-3i_tess_ffi_3iatlas-s1751-cam2-ccd3_tess_v1.1_lc.fits
No.    Name          Ver    Type      Cards   Dimensions
  0  PRIMARY           1 PrimaryHDU      46   ()      
  1  LIGHTCURVE_AP0    1 BinTableHDU     90   513R x 20C 
  2  LIGHTCURVE_AP1    1 BinTableHDU     90   513R x 20C 
  3  LIGHTCURVE_PSF    1 BinTableHDU     70   513R x 16C 
  4  EXTRAS            1 BinTableHDU     55   513R x 13C     
  ```

See our [Jupyter notebook tutorials](https://github.com/jorgemarpa/tess-3iatlas) for details on how to read these files, explanation on extraction and correction process, and detailed descriptions of the table content.

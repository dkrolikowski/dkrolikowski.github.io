---
layout: page
title: Software
subtitle: Spectroscopic data reduction and analysis, stellar and exoplanetary astronomy
cover-img:
  - "/assets/img/neid_echelle.jpg" : "NEID Echellogram of 51 Peg, Credit: The NEID Team"
---
{% include mathjs %}

My favorite part of my job is writing software to support astronomical instrumentation and the research done by other astronomers. That joy is largely what led me to my current role on the NEID software team, where I am continuing my years of experience working on the reduction and analysis of spectroscopic data, even extending my work to influence the extreme precision radial velocity (EPRV) community at large.

## NEID Data Reduction Pipeline

I have significantly contributed to the NEID pipeline in my current role, the documentation for which can be found [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/). Beyond addressing issues and helping to restart the instrument after the June 2022 wildfire shutdown, my main contributions to the pipeline have been rewriting its **telluric model creation** and **wavelength calibration** modules.

### Telluric Modeling

In version 1.3 of the NEID pipeline, I introduced a new telluric model generation routine. Large swaths of light in the visible and infrared are absorbed by Earth's atmosphere, contaminating our astronomical observations. However, we can generate a model of how the atmosphere absorbs the light and provide a correction to the spectra. This is a difficult problem though!

Details about and examples of the new telluric model can be found in the documentation [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/algorithms.html#telluric-model), but to summarize:

+ I remade the telluric model grid using [```LBLRTM```](https://github.com/AER-RC/LBLRTM) to remove issues we were encountering with the sampling of the model spectra.
+ I parameterized NEID's non-Gaussian instrument profile using laser frequency comb observations across the spectrum.
+ I implemented a variable kernel convolution to convolve the telluric model with NEID's variable instrument profile, generating an accurate representation of how NEID sees telluric absorption.
+ I added functionality to simultaneously fit for the precipitable water vapor column using multiple regions of the spectrum.

There is still work to be done, though, including accounting for asymmetries in NEID's instrument profile (which all spectrometers have!) and a more efficient convolution.

<!-- [![O2 Gamma Band](/assets/img/o2_gamma_band.png){: width="400" align='right'}](/assets/img/o2_gamma_band.png)

On the right I show an example of the new telluric model correction with the latest version of the NEID pipeline for an A star -- so the spectrum should be flat. This is a portion of the spectrum covering the O<sub>2</sub> gamma band, which is the weakest of the three strong O<sub>2</sub> bands in the visible. In <span style="color:#50b29e; font-weight: bold;">teal</span> is the correction with the old pipeline (without a variable LSF) and in <span style="color:#db6d1b; font-weight: bold">orange</span> is the new correction with the variable LSF. Since these are O<sub>2</sub> lines, they are only highligthing the improvement from the LSF, and the correction is **much** better! There are a few weak water lines in this span, like at 6299 Angstrom, which are also better corrected in the new pipeline version. -->

#### Standalone Telluric Model Module

I created a standalone version of the NEID pipeline's telluric module that is available on my GitHub at [```eprv_telluric_correction```](https://github.com/dkrolikowski/eprv_telluric_correction). This is primarily designed for use with HPF,  which *greatly* benefits because its near infrared bandpass has much more telluric contamination.

### Wavelength Calibration

Wavelength calibration is perhaps the most important step in a pipeline for extreme precision radial velocity instruments. Without a precise and stable wavelength calibration, you cannot measure stellar radial velocitites to the precision required for detecting and characterizing exoplanets!

In version 1.4 of the NEID pipeline, I completely refactored the complex wavelength calibration module to be more maintainable, readable, and most importantly more extensible for future improvement to the constituent wavelength calibration algorithms.

In version 1.5 of the NEID pipeline, I leveraged the refactor to add a new wavelength calibration mode that better handles poor calibration data, providing our users with higher quality data even during times when our calibration sources are struggling.

You can find more details about the wavelength calibration module in the documentation [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/algorithms.html#wavelength-calibration).

## The EPRV Community Data Format Standard and Translators

As a member of the collaboration to create a standardized EPRV data format, I am the primary developer of the code to translate native NEID data into the standard format. The package with the translator code, which works on many many EPRV instruments, can be found in the repository [RVData](https://github.com/EPRV-RCN/RVData). There is thorough documentation about the standard format and the translator code, including a tutorial on using NEID data in the standard format. This code is pip installable, and just had its v1.0.0 release!

## Tull Coudé Spectrograph Reduction and Analysis Pipeline

While a grad student at UT Austin, I wrote a reduction pipeline for the Tull coudé spectrograph on the Harlan J. Smith 2.7-m telescope at McDonald Observatory. The original pipeline was written in python 2.7 and is still on my GitHub at [```coudereduction```](https://github.com/dkrolikowski/coudereduction).

In 2023, I finally got around to updating the pipeline: writing it in Python 3, making it more user friendly, and implementing its steps in a more modular way. This version of the pipeline can be found on my GitHub at [```tull_coude_reduction```](https://github.com/dkrolikowski/tull_coude_reduction) (with [documentation](https://tull-coude-reduction.readthedocs.io/en/latest/)). As of now, the pipeline runs from processing the raw CCD images to measuring radial velocities from extracted and wavelength calibrated stellar spectra.

<!-- 
While the pipeline is written specifically for the Tull spectrograph, it is being developed with a modular design so that:
  + It is easy to add more functionality, or different algorithms/methods for any of the reduction or analysis steps.
  + It could be adapted for use with similar optical echelle spectrographs.
  + The individual modules can be used as a basis for other pipelines or teaching spectral reduction and analysis.
 
I'm still actively developing the pipeline -- so stay tuned for improvements and more functionality! -->

## Miscellaneous

### Orbits Code

I wrote code for a Planetary Astrophysics class in grad school to take in parameters of a planetary system and output observable quantities such as the stellar RV, astrometric orbits, and when transits would occur. My version can be found as [```HW1_Orbits```](https://github.com/dkrolikowski/HW1_Orbits) on my GitHub.

I haven't gone back and edited the code since I created it (I was an early grad student so it might be a little rough), but it might still be useful to take a look at for people needing to generate planetary system observations!

### Minor Contributions

+ [```saphires```](https://github.com/tofflemire/saphires) is a code developed by [Ben Tofflemire](https://www.seti.org/people/ben-tofflemire/) (a TESS Pipeline Scientist at SETI) that implements broadening functions to measure radial velocities from high resolution spectra. This code is great! Broadening functions are a very useful tool for measuring RVs and understanding stellar spectra, and there are great discussions of why in the [```saphires```](https://github.com/tofflemire/saphires) documentation.
+ [```comove```](https://github.com/adamkraus/Comove) is a code devloped by Adam Kraus (my Ph.D. advisor and UT Austin professor) to use Gaia to search for comoving companions to any input star. It searches through a whole bunch of catalogues to provide plots with which one can assess whether or not a star is a member of a larger stellar association or not. It is super useful for searching for unidentified and "looser" young stellar populations.

## Future Plans

+ Creating a package to measure equivalent width of the Helium 10830 Angstrom triplet from HPF spectra. This would be a public release of the code used to measure EWs presented in my [recent paper on the Helium triplet in young stars](https://ui.adsabs.harvard.edu/abs/2024AJ....167...79K/abstract). My hope is that you could point to any HPF spectrum of a (late F through early M) star and output a Helium EW!
+ Expanding the telluric correction package to work on more instruments than just HPF.

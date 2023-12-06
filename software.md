---
layout: page
title: Software
subtitle: Spectroscopic data reduction and analysis
cover-img:
  - "/assets/img/neid_echelle.jpg" : "NEID Echellogram of 51 Peg, Credit: The NEID Team"
---
{% include mathjs %}

Writing software, in particular to support others, is one of my favorite parts of being an astronomer. That joy is largely what led me to my current job on the NEID software team, where I am continuing my years of experience working on the reduction and analysis of spectroscopic data.

Below I detail software that I have written or plan to write, and my contributions to the NEID pipeline.

## Coude Reduction Pipeline

While a grad student at UT Austin, I wrote a reduction pipeline for the Tull coudé spectrograph on the Harlan J. Smith 2.7-m telescope at McDonald Observatory. I've maintained the original Python 2 version of the pipeline since 2017, which can be found on my GitHub page as [```coudereduction```](https://github.com/dkrolikowski/coudereduction).

Recently, I finally got around to updating the pipeline -- writing it in Python 3, making it more user friendly, and implementing its steps in a more modular way to make future development easier. This version of the pipeline can be found on my GitHub as [```tull_coude_reduction```](https://github.com/dkrolikowski/tull_coude_reduction) and its documentation can be found [here](https://tull-coude-reduction.readthedocs.io/en/latest/). As of now, the pipeline runs from processing the raw CCD images to measuring radial velocities from extracted and wavelength calibrated stellar spectra.

While the pipeline is written specifically for the Tull spectrograph, it is being developed with a modular design so that:
  + It is easy to add more functionality, or different algorithms/methods for any of the reduction or analysis steps.
  + It could be adapted for use with similar optical echelle spectrographs.
  + The individual modules can be used as a basis for other pipelines or teaching spectral reduction and analysis.
 
I'm still actively developing the pipeline -- so stay tuned for improvements and more functionality!

## NEID Work

I have also contributed to the NEID data reduction and analysis pipeline in my current postdoc role. Although the NEID pipeline is not yet public, you can find detailed documentation about the NEID data format, pipeline architecture, and reduction/analysis algorithms [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/).

Beyond addressing issues and helping to restart the instrument after the June 2022 wildfire shutdown, my main contribution to the pipeline has been rewriting its **telluric model creation module**.

NEID has a variable line spread function across its spectrum, with a significant amount of width, shape, and asymmetry changes within an order and from order to order. This needs to be included in the telluric model for it to be an accurate representation of what NEID observes as the atmospheric transmission. 

![O2 Gamma Band](/assets/img/o2_gamma_band.png){: width="400" align='right'}

I detailed the improvements I made to the telluric module in the NEID pipeline documentation [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/algorithms.html#telluric-model), and outline them below:
  + I chose a parameterization of the line spread function (a Gaussian convolved with a Top Hat) and measured it across the NEID spectrum using observations of the LFC. 
  + I remade the telluric model grid using [LBLRTM](https://github.com/AER-RC/LBLRTM) to remove issues we were encountering with the sampling of the model spectra, introducing interpolation errors.
  + I implemented variable kernel convolution to convolve the telluric model grid with the variable LSF, allowing for a different convolution kernel (LSF) at every pixel.
  + I added functionality to simultaneously fit for the precipitable water vapor column using multiple regions of the spectrum.

There is still work to be done on the telluric module. For one, the variable LSF is only mapped where we have LFC spectra, which does not cover the full NEID bandpass. I also intend to apply these methods to HPF spectra, which will *greatly* benefit from improved telluric correction given its NIR bandpass. 

Beyond the telluric module, I am currently helping to overhaul the wavelength calibration module to extract as much information as possible from the ensemble of wavelength calibration source data we taken every day.

## Miscellaneous

Here's some other random software I've worked on, including recommendations to packages that I have (minorly) contributed to that I think are very cool and useful!

### Orbits code

For a Planetary Astrophysics class in grad school, we had to write code to take in parameters of a planetary system and output observable quantities such as the stellar RV, astrometric orbits, and when transits would occur. My version can be found as [```HW1_Orbits```](https://github.com/dkrolikowski/HW1_Orbits) on my GitHub page. 

I haven't gone back and edited the code since I created it (I was an early grad student so it might be a little rough), but it might still be useful to take a look at for people needing to generate planetary system observations!

### Minor contributions

+ [```saphires```](https://github.com/tofflemire/saphires) is a code developed by [Ben Tofflemire](https://tofflemire.github.io/index.html) (51 Peg postdoctoral fellow at UT Austin) that implements broadening functions to measure radial velocities from high resolution spectra. This code is great -- broadening functions are a very useful tool for measuring RVs and understanding stellar spectra, and there are great discussions of why in the ```saphires``` documentation.
+ [```comove```](https://github.com/adamkraus/Comove) is a code devloped by Adam Kraus (my Ph.D. advisor and UT Austin professor) to use Gaia to search for comoving companions to any input star. It searches through a whole bunch of catalogues to provide plots with which one can assess whether or not a star is a member of a larger stellar association or not. It is super useful for searching for unidentified and "looser" young stellar populations.

## Future plans

Beyond improvements and expansions to the Tull coudé reduction and analysis pipeline, other software I am thinking about is:

+ Creating a package to measure equivalent width of the Helium 10830 Angstrom triplet from HPF spectra. This would be a public release of the code used to measure EWs presented in my recent paper on the Helium triplet in young stars, which can be found on arXiv [here](https://arxiv.org/abs/2311.04971). My hope is that you could point to any HPF spectrum of a (late F through early M) star and output a Helium EW! This also would include the HPF application of the NEID telluric correction described above.


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

While a grad student at UT Austin, I wrote a reduction pipeline for the Tull coudé spectrograph on the Harlan J. Smith 2.7-m telescope at McDonald Observatory. I've maintained the original Python 2 version of the pipeline since 2017, which can be found on my GitHub page.

Recently, I finally got around to updating the pipeline -- writing it in Python 3, making it more user friendly, and implementing its steps in a more modular way to make future development easier. This version of the pipeline can be found on my GitHub as ```tull_coude_reduction``` and its documentation can be found [here](https://tull-coude-reduction.readthedocs.io/en/latest/). As of now, the pipeline runs from processing the raw CCD images to measuring radial velocities from extracted and wavelength calibrated stellar spectra.

While the pipeline is written specifically for the Tull spectrograph, it is being developed with a modular design so that:
  + It is easy to add more functionality, or different algorithms/methods for any of the reduction or analysis steps.
  + It could be adapted for use with similar optical echelle spectrographs.
  + The individual modules can be used as a basis for other pipelines or teaching spectral reduction and analysis.
 
I'm still actively developing the pipeline -- so stay tuned for improvements and more functionality!

## NEID Work

## Miscellaneous

### Orbits code

### Contributions/shoutouts

## Future plans

### HPF Helium EWs
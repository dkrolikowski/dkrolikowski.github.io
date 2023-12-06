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

I have also contributed to the NEID data reduction and analysis pipeline in my current postdoc role. Although the NEID pipeline is not yet public, you can find detailed documentation about the NEID data format, pipeline architecture, and reduction/analysis algorithms [here](https://neid.ipac.caltech.edu/docs/NEID-DRP/).

Overview of pipeline: documentation.

Overview of my contributions: telluric model/LSF and wavelength calibration improvements.

### NEID Telluric Model

Why? Variable line spread function. Rebuild grid, build map of LSF, implement variable kernel convolution. Link to documentation.

What else -- apply to HPF!

## Miscellaneous

here are some miscellaneous

### Orbits code

From class homework. Not well maintained but people may find it useful to look at.

### Contributions/shoutouts

Shout outs to some packages that are cool and useful that I contributed to in a minor way -- mostly through testing and consultation on implementation.

  + saphires
  + comove

## Future plans

Beyond improvements to coude pipeline, other things I'm thinking about.

### HPF Helium EWs

Analysis pipeline for HPF -- measure He EWs like in my paper. Make use of the telluric code from above. Point to any late F through early M dwarf HPF spectrum and output a He EW! Would be useful for running on large data sets. Also transparency: pipeline is described in my paper but the code is not published somewhere, and it should be.



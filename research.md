---
layout: page
title: Research Projects
subtitle: young stars, their planetary systems, and the spectroscopic data to understand them
cover-img:
  - "/assets/img/taurus_cloud.jpg" : "The Taurus Dark Clouds, Credit: Digitized Sky Survey 2"
  - "/assets/img/gj3470b.jpg" : "Illustration of GJ 3470 b's evaporating atmosphere, Credit: NASA, ESA, D. Player (STScI)"
---
{% include mathjs %}

My research interests broadly include young stars and planets, in particular:

+ Young stellar activity, as a probe of stellar astrophysics and its effect on radial velocity or exoplanet atmospheric measurements.
+ Leveraging Gaia to understand young stellar populations and their star forming histories.
+ The properties and architectures of young planetary systems to understand their formation pathways.
+ And very importantly, spectroscopic data handling, processing, and analysis, which underpin much of the above work!

<!-- + Leveraging Gaia to understand young stellar populations and their star forming history. (See my paper about the Taurus star forming region [here](https://ui.adsabs.harvard.edu/abs/2021AJ....162..110K/abstract))
+ Young stellar activity, including as a probe of stellar astrophysics and its effect on RV observations. (See my paper about the NIR Helium triplet's activity [here](https://arxiv.org/abs/2311.04971) and a conference talk about the work [here](https://www.youtube.com/watch?v=agLcXqk2zRA))
+ The architecture of young planetary systems and their formation pathways
+ Spectroscopic data reduction and analysis

Below I talk in more detail about some of the main projects I have worked on. -->

## Stellar activity in the NIR Helium triplet at young ages

Over the last 5 years, the NIR Helium triplet absorption feature (~10830 angstrom) has emerged as an extremely important probe of exoplanet exospheres and atmospheric mass loss. The commissioning of multiple NIR precision spectrometers (such as HPF) have made it easier to observe the NIR Helium triplet and observe *samples* of planets to search for exospheres and measure mass loss across planetary and stellar properties. This will help elucidate the cause and timescale of atmospheric mass loss. To understand the timescale, it is necessary to look for exospheres as a function of age, particularly at young ages.

*However*, the NIR Helium triplet, which is a chromospheric stellar spectral line, is sensitive to stellar activity. Since activity is higher at younger ages, potential contamination of exosphere observations from the host star activity itself is a greater issue for young exoplanets. The activity-driven behavior of the NIR Helium triplet at young ages is not well-studied though.

[![Helium Variability vs Age](/assets/img/he_var_vs_age.pdf){: width="40%" align="left" style="padding:10px"}](/assets/img/he_var_vs_age.pdf)

In [work I published](https://ui.adsabs.harvard.edu/abs/2024AJ....167...79K/abstract), I used a large HPF data set for a sample of young exoplanet host stars to analyze the NIR Helium triplet stellar absorption as a function of age, activity, and time. We find that the NIR Helium triplet is indeed variable from stellar activity, with increased variability at younger ages and the fastest rotation periods. The plot to the left shows the intrinsic stellar Helium triplet absorption variability vs. age, highlighting a precipitous decrease from high variability at the youngest ages. Stellar activity can definitely affect and confuse exosphere observations, although for stars with ages above 200-300 Myr it shouldn't prevent the detection of exospheres.

**The main takeaway is just to be careful!** While stellar activity isn't a death knell for finding young exospheres, we just need to carefully considering transit timing, other activity indicators, etc. when interpreting exosphere observations.

## EPRV community efforts for data and software standardization

For the last few years, I have been heavily involved in EPRV community-wide efforts to standardize our data formats and software. Pushing EPRV science to the goal of 10 cm/s precision will require combining data from multiple instruments and thorough understanding of how hardware and software design choices affect RV measurement. To enable this, we need to standardize the format of our high resolution spectroscopic data, for which each instrument has a slightly (or not so slightly) different format.

An effort led by [Jenn Burt](https://science.jpl.nasa.gov/people/burt/) successfully defined a standardized data format, which is explained on this [documentation page](https://eprv-data-standard.readthedocs.io/en/latest/overview.html). The data format covers multiple data levels (L0 through L4) with progressive levels of processing. We also developed translator code for each instrument's native data format into the standard format. That code is found in the repository [```RVData```](https://github.com/EPRV-RCN/RVData/) on GitHub, and I was a primary developer of the NEID translator.

I am PI of a NASA-funded follow-up effort to develop the software infrastructure of a standardized community data reduction and analysis framework. This effort focuses on the *transition* between data levels, rather than handling the data level products themselves. We specifically are not developing a "community pipeline". The idea is that this framework can hold all of the modules and algorithms required to build an EPRV pipeline, but that there is no "top down" single pipeline. Instead, this framework should encourage mix-and-match testing of different algorithms on data from different instruments, and the development of cutting edge methods for data processing and analysis.

## The Taurus star forming region's substructure and history

Gaia has provided an unprecedented level of high quality astrometry and photometry across the entire sky. With its high precision, we can use Gaia data to map the 3D (and when including radial velocities 6D) structure of stellar populations and back out a picture of how they formed. These formation histories constrain theories of star formation, such as the role of different star formation triggers or the dispersal mechanisms of stellar groups.

[![Taurus XY Plane](/assets/img/taurus_xyplane.png){: width="380" align="right"}](/taurus)

In [work I published](https://ui.adsabs.harvard.edu/abs/2021AJ....162..110K/abstract), I compiled the most comprehensive census of the Taurus star forming region's stellar population to date, and used Gaia to map its structure and uncover its star forming history. Taurus is the canonical region of low mass star formation, but it has a complex history with multiple populations. We found significant spatial substructure in Taurus's stellar population, with two types of subgroups: those tightly confined in space (and preferentially near the molecular clouds) and those that are distributed throughout the region. Check out a [cool interactive plot](/taurus) showing the Taurus stellar population and our identified subgroups in galactic 3D space. The plot to the right shows the Taurus stellar population in the galactic XY plane, with different markers indicating different stellar groups.

The region as a whole is fairly coherent in kinematics, although there are some hints of kinematic substructure that correlate with position. On average, the tightly confined groups are younger than the distributed groups, which makes sense as they are closer to the areas of ongoing star formation. This all points to a highly complicated star formation history, having at least two successive epochs of star formation featuring multiple modes (clustered and distributed) of star formation simultaneously.

## Outer architectures of young planetary systems

I am also using my HPF data sets to search for outer giant planets in young systems with known short-period transiting planets using HPF RVs. Mapping the outer orbital architectures of these systems is a crucial constraint on their formation pathways, particularly the mechanisms behind orbital migration. The connection between inner and outer planets as a function of age, particularly in the first billion years when systems are most rapidly evolving, could elucidate the role of planet-planet scattering in the dynamical history of planetary systems. Thankfully, K2 and TESS have found dozens of transiting planets in young star clusters and associations, which provide a good grasp on their ages.

[![Starspots](/assets/img/starspot.gif){: width="300" align="right"}](/assets/img/starspot.gif)

The animation on the right shows how star spots, which are prevalent on young stars, can distort the spectral lines that we observe as they rotate in and out of view. This makes it hard to disentangle stellar activity-drive RV noise from a planet's RV signal. One way to mitigate this is to observe in the infrared where the star spot contrast is lower, and HPF is one such instrument!

My survey for outer giant planets in these young systems is still ongoing and the full data set has not been analyzed in depth. There is a preliminary set of results in the third chapter of [my dissertation](https://repositories.lib.utexas.edu/items/0fda0b8f-2b6b-473a-82c2-ac104096787b) (although there is emphasis on the word *preliminary*). We find evidence for long-term trends in a few of the systems, but the sparse cadence of the long-term RV monitoring makes the detection of periodic signals difficult. These data will also be useful for understanding NIR RV jitter and its connection to other spectroscopic activity indicators.

## Other assorted projects

### Searching for new young stellar groups

Gaia's precise data doesn't just let us understand stellar associations we already know about, but can be used to search for new ones! We can look for stars that have similar positions (in the sky and in distance) and on-sky motions, which could indicate they are related to each other. A key missing piece though is a clear age indicator and a radial velocity to get full 3D kinematics. I have carried out many observations with the Tull spectrograph at McDonald Observatory of candidate members of young stellar groups to measure RVs and traditional youth indicators like H-alpha and lithium abundance. For example, I have looked for new members of the Taurus complex and for the host stellar populations of isolated young transiting planet hosts. You can take a look at a [poster with results from my Taurus survey](/assets/pubs/poster_coolstars20.pdf)!

### Panchromatic RV activity signals in M-dwarfs

I have collaborated with astronomers at NASA JPL to combine precision RVs from multiple instruments across wavelength to study the chromatic behavior of stellar activity-driven RV noise. We targeted active M-dwarfs with known rotation periods and activity signals, and observed using [the APF](https://www.lickobservatory.org/explore/research-telescopes/automated-planet-finder/) in the visible and [HPF](https://hpf.psu.edu) in the NIR. With these high cadence, simultaneous RV time series, we can analyze the chromatic and temporal behavior of the activity signals. This is important because knowing activity's timescales and manifestation in different wavelength RVs is crucial to best plan and analyze extreme precision observations. You can take a look at a [poster](/assets/pubs/poster_eprv5.pdf) with preliminary results!

### Lithium abundances in star clusters across time

As an undergrad at SUNY Geneseo, I worked with [Dr. Aaron Steinhauer](https://www.geneseo.edu/physics/steinhauer/) on a variety of projects studying the lithium abundances of open and globular star clusters. Lithium is am important tracer of chemical evolution in stars, where it can be produced and destroyed easily. Lithium depletes over time because it burns at relatively low temperatures, which makes it a fairly robust youth indicator. Lithium can also be created in the interiors of stars, although it often is immediately destroyed. However, there are non-standard processes that can bring fresh Li to the stellar surface, making Li an observable test of stellar interior modeling! I worked on projects to map the Li abundances of both main sequence and red giant stars in multiple clusters.

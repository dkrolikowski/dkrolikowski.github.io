---
layout: page
title: Research
subtitle: young stars, their host populations, and their planetary systems
cover-img:
  - "/assets/img/taurus_cloud.jpg" : "The Taurus Dark Clouds, Credit: Digitized Sky Survey 2"
---
{% include mathjs %}

My research interests broadly include young stars, the stellar populations in which they reside, and the planets around them. This includes projects that cover scales from entire regions of young or forming stars, down to the individual planets in these systems. I'm in my 5th year as a Ph.D. student at [UT Austin](https://astronomy.utexas.edu) where I work with Adam Kraus. During my undergraduate education at [SUNY Geneseo](https://www.geneseo.edu/physics), I worked with Aaron Steinhauer studying the lithium abundances of star clusters, to map the chemical evolution of lithium across time and stellar type.

# Young stellar populations

To understand how planetary systems form and evolve, we must understand how the stars they orbit do the same. One pillar of my research is the study of young stars, and in particular the groups they form in. Most stars form in clusters, or at the very least loose associations. By studying an ensemble of stars that formed together, it is easier to determine the age, and thus other stellar properties, of all stars in the group. With a well defined census, we can look at the spatial and velocity distributions of the stars in these groups to back out a picture of how they formed, which can constrain the theories and physics of star formation in general.

## Taurus

The bulk of the work I have done so far on young stars has been in the Taurus star forming region, which is the canonical region of low mass star formation in the Milky Way, and one of the nearest sites of ongoing star formation to us. Because it is so close, Taurus has been studied for a long time, leading to a rich history of knowledge of the region (my current record for oldest reference used is 1890). However, as with anything studied for so long, or really anything in astronomy, there are peculiarities in the greater Taurus region that elude total explanation.

[![Taurus in H2](/assets/img/taurus_h2.png){: width="400" align="right"}](https://ui.adsabs.harvard.edu/abs/2008ApJ...680..428G/abstract)

For example, Taurus has a rich census of disk-bearing, young objects near the clouds featuring ongoing star formation, but it also has disk-bearing objects at wide separations from those clouds. Additionally, there are disk-free objects distributed throughout the Taurus region, which might be the result of an older epoch of star formation. The gas in Taurus is also highly structured, featuring filaments and overdensities of gas (see the image to the right from [Goldsmith et al. 2008](https://ui.adsabs.harvard.edu/abs/2008ApJ...680..428G/abstract)). The formation of these gas structures is intimately tied to the role of gravity and turbulence (and magnetic fields, ...) in the star formation process. Tying the gas structure to the substructure distribution of stars in the region would elucidate the process by which stars decouple from their parent cloud and evolve after formation. All of this together implies that the star formation history of Taurus is quite complicated, and unraveling its mysteries is key to our understanding of low mass star formation.

I have undertaken a couple of different projects to help answer these questions about the Taurus region, in particular looking to leverage the high precision astrometry from the *Gaia* mission to: 1) disentangle the complicated 6D position and velocity substructure of the Taurus stellar population and 2) search for new members of the Taurus region, especially older objects that may have eluded previous biased surveys of the region.

### Substructure in the Taurus region using *Gaia* EDR3

[![Taurus XY Plane](/assets/img/taurus_xyplane.png){: width="380" align="right"}](/taurus_interactive_3d)

The main project involving Taurus I have worked on is using *Gaia* EDR3 to investigate the substructure in the region, and paint a picture of the star forming history of the region. In this project, we have compiled an expansive census of Taurus members -- basically anything that has had some sort of youth confirmation and has been considered a member of the Taurus region -- and have matched with *Gaia* EDR3 to tease out the structure of Taurus's stellar population. We find that there is significant spatial substructure, with two types of subgroups: those that are tightly confined in space (and are preferentially near the clouds of star formation), and those that are distributed throughout the entire Taurus region. Check out a cool interactive plot [here](/taurus_interactive_3d) showing the Taurus stellar population and our identified subgroups in galactic 3D space.

The region as a whole is fairly coherent in kinematics, although there is some hints of kinematic substructure that correlates with spatial position. On average, the tightly confined groups are younger than the distributed groups, which makes sense as they are nearer to the areas of ongoing star formation. In all, this points to a highly complicated star formation history of Taurus, having at least two successive epochs of star formation featuring multiple modes (clustered and distributed) of star formation simultaneously. This work has been accepted for publication in The Astronomical Journal, and you can read the preprint for more about the methods and conclusions [here]().

### A survey for new members of the Taurus region

For my second year project at UT, I also started a spectroscopic survey for new members of the Taurus region, particularly in the older, distributed population identified in [Kraus et al. 2017](https://ui.adsabs.harvard.edu/abs/2017ApJ...838..150K/abstract). Comprehensively surveying the Taurus region away from the molecular clouds is quite complicated because it spans such a large area on the sky, and any large scale photometric surveys are biased towards certain types of stars (such as young disk-bearing objects). To systematically search for new members of this population, we need 1) full 6D phase space (position and velocity) information to ensure membership and 2) some sort of youth indicator. While *Gaia* provides exquisite positions and on-sky motions, spectroscopy is necessary for the 6th dimension of phase space (radial velocity) and youth indicators (such as lithium). This is extremely observationally intensive, requiring a large amount of time with a high resolution spectrograph.

We have access to resources for this through [McDonald Observatory](https://mcdonald.utexas.edu) and the Tull coudé spectrograph on the 2.7-m Harlan J. Smith Telescope, and have slowly built up a survey observing over a hundred candidate members of the broader Taurus region. A poster featuring preliminary results from this survey can be found [here](/assets/pubs/poster_coolstars20.pdf).

# Newly formed and evolving planetary systems

Planets are at their most dynamic in the first billion years of their lifetime, when the bulk of atmospheric and orbital evolution occurs. Observing the properties of planets across this timeframe is crucial in constraining competing models of planet formation and evolution, which make contrasting predictions for the distributions of such properties over time. For example, different orbital migration mechanisms result in different planet occurrence as a function of age, and different causes of atmospheric sculpting predict different planetary mass loss rates and radii distributions. Dozens of young planets have been discovered by missions such as K2 and TESS, including in young clusters and associations or around young field stars. Precisely characterizing the properties of these planets (mass, bulk density, atmospheric composition) and their systems (i.e. other planets in the system and their orbital properties) will greatly increase our understanding of the early evolution of planetary systems.

## Probing the architectures of young planetary systems

Young stars are active, leading to a high level of photometric and spectroscopic variability that make discovering and characterizing planets around them quite difficult. For example, the presence of starspots introduces radial velocity jitter, which is temporally coherent noise that inflates the scatter of RV measurements of a star. This makes it extremely difficult to measure the mass of young planets, particularly those with small masses. One way to mitigate this issue is to observe in the infrared, where starspot contrast is decreased and RV jitter is smaller. The Habitable-zone Planet Finder spectrograph, a precision near-infrared spectrograph on the 10-m Hobby-Eberly Telescope at McDonald Observatory, is an ideal instrument to precisely measure the RVs of young stars and try to detect the doppler signal of planets around them.

Paragraph on what I'm doing and what I'm trying to answer. Sentence on the program set up and the sample. Sentence on ancillary science and other results. Sentence on status and future work.

## The occasional intensive campaign

# Li abundances in star clusters across time

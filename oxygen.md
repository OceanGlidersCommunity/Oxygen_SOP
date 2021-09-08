---
Title: "OceanGliders Standard Operating Procedure (SOP)"
Subtitle: "Oxygen"
Version: 0.3
---

![](images/logo-ocean-gliders.png)

**Authors**
*(1) [Patricia López-García](https://github.com/patricialg), Ocean Technology and Engineering Group, National Oceanography Centre, Southampton, UK*
*(2) [Tom Hull](https://github.com/tomhull), Centre for Environment Fisheries and Aquaculture Science, Lowestoft, UK*
*(3) [Soeren Thomsen](https://github.com/soerenthomsen), LOCEAN, ISPL, Sorbonne University, Paris, France*
*(4) Johannes Hahn, Federal Maritime and Hydrographic Agency (BSH), Hamburg, Germany*
*(5) [Bastien Y. Queste](https://github.com/bastienqueste), Department of Marine Science, University of Gothenburg, Gothenburg, Sweden*
*(6) Gerd Krahmann, GEOMAR Helmholtz Centre for Ocean Research Kiel, Germany* 
*(7) Charlotte Williams, Marine Physics and Ocean Climate Group. National Oceanography Centre, Liverpool, UK*
*(8) Mun Woo, IMOS Ocean Gliders, UWA Oceans Institute and Oceans Graduate School, The University of Western Australia, Perth, Australia*
*(9) Charitha Pattiaratchi, IMOS Ocean Gliders, UWA Oceans Institute and Oceans Graduate School, The University of Western Australia, Perth, Australia*
*(10) Laurent Coppola, Sorbonne Université, CNRS, Laboratoire d’Océanographie de Villefranche (LOV), 06230 Villefranche-sur-Mer, France*
*(11) Tania Morales, Plataforma Oceánica de Canarias (PLOCAN), Canary Islands, Spain*
*(12) Virginie Racape, Institut Universitaire Européen de la mer CNRS-UMS 3113, IFREMER-coriolis, Plouzané France*
*(13) Claire Gourcuff, Euro-Argo ERIC, Brest, France*
*(14) John Allen, SOCIB, Palma de Mallorca, Spain*
*(15) Eva Alou-Font, SOCIB, Palma de Mallorca, Spain*
*(16) Nikolaos D. Zarokanellos, SOCIB, Palma de Mallorca, Spain*

# SOP development process

1) Initial SOP was drafted by Patricia López-García, Tom Hull, Sören Thomsen and Johannes Hahn.

2) Two expert sessions during OceanGliders Best Practice Workshop, May 11 - 25 2021. 
Additional authors joined: Bastien Y. Queste, Gerd Krahmann, Charlotte Williams, Mun Woo, Charitha Pattiaratchi, Laurent Coppola, Tania Morales, Virginie Racape, Claire Gourcuff, John Allen, Eva Alou, Nikolas D. Zarokanellos 
First community and  user feedback was provided during the workshop by attendees. 

3) SOP moved to this repository by: Patricia López-García, Tom Hull, Sören Thomsen in September 2021.

4) Next step: Several months of community review on GitHub starting in October 2021.

# Introduction
This standard operating procedure (SOP) document for dissolved oxygen (DO) aims to guide the user through the steps necessary for collection of good quality dissolved oxygen using gliders for both real time and post deployment data streams.

## Aanderaa Optodes
Aanderaa optodes are the most widely used oxygen sensor on gliders and a large body of work has now been dedicated to their characterisation (e.g. [@Bittig2018]).
These sensors are based on the oxygen luminescence quenching of a platinum porphyrin complex (fluorescent indicator) that is immobilized in a sensing foil. These offer low power consumption, good long-term stability, low fouling sensitivity while not being sensitive to H2S or freezing.
Aanderaa optodes have seen several important developments since they were introduced in 2002, with various hardware and firmware revisions which we outline below.

### Hardware design: blue or black
While mostly cosmetic, the colour of the optode is a useful short-hand for the two main optode designs.
The 3835 and 4835 optodes both feature a black housing with the temperature sensor integrated into the base of the sensor near the connector. 
This results in a large thermal mass and increases the response time of the temperature sensor significantly. 
The blue 4330 and 4831 sensors move the thermistor next to the sensing foil which results in much improved performance of the temperature sensor.
All optodes other than the 4831 use a 10 pin Lemo connector, these connectors can’t be connected when wet and are prone to crevice corrosion. 
The 4831 is therefore recommended with it’s Subconn wet-pluggable connector.
Older optode versions (3830) have a titanium housing in the same form factor as the 3835. 
Some early Slocum gliders were  delivered with optodes of type 5013, these are identical to the 3830.

### Foil type: F or standard
Most optodes use the PreSens PSt3 foil (PreSens - Precision Sensing GmbH), these have as standard a black opaque protective layer protecting the pink sensing layer.
For glider applications the “F” type foils are typically preferred as these remove the opaque layer which results in much faster diffusion across the foil, and therefore faster sensor response (8 s compared to ~ 25 s [@Bittig2014]). 
However, removal of the protective layer makes the foil more susceptible to UV radiation, and is known to reduce the sensor stability, especially when exposed to strong sunlight.
Newer 4330F and 4831F optodes (Since July 8th 2018) use an improved formulation of the Presens fast foil which are less sunlight sensitive and have much lower noise levels. These can be identified by their white appearance. 
It is recommended that older F-type instruments (with the pink foils) are upgraded with these improved foils. Otherwise foils should typically not be replaced unless mechanically damaged (light intrusion) as older foils perform better, with less drift than new ones.

### Calibration equation and firmware versions
The way optode foils are initially calibrated by Aanderaa, and how the measured values are processed by the optode varies between different optode versions.
The optode illuminates the sensing foil with both a red and blue LED. 
Since the red light does not produce fluorescence in the foil the phase measurements are obtained from the difference between the blue (P1) and the red (P2) excitation.

P_T = A(T) + (P1 - P2) · B(T)

Where P_T is the temperature compensated phase (known as ‘TCphase‘). 
A and B are temperature dependent coefficients which allow for temperature compensation of the phase measurement. 
However for most 4330, 4831 and 4835 optodes these are not used, such that A(T) = 0 and B(T) = 1. 
This can be confirmed by communicating with an optode and inspecting the ‘PTC0Coef‘ and ‘PTC1Coef‘ properties. 
For older optodes (4330 serial numbers < 1000) the temperature compensated phase is then used to calculate ‘calphase‘ (P_c). 
For newer optodes P_T = P_c. Similarly older optodes have their calibration (and recalibration) applied though the modification of the ‘PhaseCoef‘ coefficients. 
On later optodes the calibration is not applied in phase space, but on the oxygen concentration though the use of the ‘ConcCoef0‘ and ‘ConcCoef1‘ coefficents (‘PhaseCoef0‘ and ‘PhaseCoef1‘ are set to zero and 1 respectively). 
Consult your optode calibration sheet and confirm which terms are being used.
There are three different calibration equations used to convert the measured phase to oxygen equations:
The “Mk1” equation used by the older 3835 optodes uses a 5x4 matrix of coefficients. 
The “Mk2” equation is used by non-multipoint calibrated 4330(F) and 4835 optodes, and uses a 2x14 matrix (FoilCoefA and FoilCoefB) together with a 2x27 matrix for the polynomial degree, this second matrix is the same across all of these type optodes. 
Newer multipoint calibrated optodes use the Stern-Volmer (SVU) equation proposed by [@Uchida2008] which has 6 terms.
Non-multipoint foil calibrations are based on a common characterisation of a production batch. 
Multipoint calibrations consist of 40 calibration points across a range of concentrations and temperatures and offer improved accuracy and should be preferred when purchasing these sensors.
Consult your optode foil calibration document to verify which version your optode is using. 
Understanding these differences in how the calculations are performed is important when recalculating oxygen from the phase readings, such as when compensating for lag.
Regardless of the optode version, oxygen can be recalculated from calphase using the approach of [@Uchida2008].

During the initial months of storage/use a Foil maturation process occurs resulting in lower readings by several %. 
The maximum observed maturation induced drift on more than 1000 sensor has been 8 % for sensors with non-factory pre-matured WTW foils (model: 4835, 4531 and 5730 Steinsvik) and 6 % for sensors with factory pre-matured PSt3 foils (model: 4330, 4831, 5331 hadal). 
During/between field deployments there are possibilities for end users to post-adjust the sensors either by a one-point air-saturation adjustment or by taking reference samples (e.g. water samples and Winkler titration) and/or using a well-calibrated sensor in parallel. 
If done correctly such an adjustment should result in an absolute accuracy of around 1 % for multipoint calibrated sensors (model: 4330, 4831, 5331 and 5730) and 3 % for two-point calibrated (model: 4835, 4531), see below for more information about factory calibrations. 
The drift will decrease over time so that during the second year it is not likely to be more than 1-2 %. 
After this it should be less than 0.5 % per year, unless the foil is mechanically damaged (Aanderaa Best Practices for Maintaining High Data Quality). 

## RBR coda T.ODO
The RBRcoda T.ODO uses the same foils and methods as the 4831 and 4831F so everything above specified for the 4831 will also apply to those instruments as well.
RBR refers to the standard optode (~30 s tau) foil as “slow” and the fast (~8 s) as the standard.
They also use further foil design (~1 s response) which they call fast. 
The RBR sensor has a smaller form factor than the Aandera optodes, but is overall more similar to a 4831 with the temperature sensor very closely located to the sensing foil. 
This sensor is still fairly recent on gliders and little is known for now.

## JFE Advantech RINKO

# Pre-deployment operations

## Storage and cleaning

## Sensor integration

## Pre-deployment calibration

# Missions execution

# Real time data processing & Quality Control

# Post-recovery operations and calibrations

# Delayed Mode Quality Control (DMQC)

# Data delivery to public open access archives

# Acknowledgement 
The coordination of producing this document was supported by the European Commission via the EuroSea.eu project under H2020 funding (Grant agreement 862626) and GROOM || Horizon 2020 research and innovation programme (Grant agreement No 951842).

Patricia Lopez-Garcia was supported by TechOceanS project which received funding from the European Union’s Horizon 2020 research and innovation programme under grant agreement No 101000858 (TechOceanS). This output reflects only the author’s view and the Research Executive Agency (REA) cannot be held responsible for any use that may be made of the information contained therein.

Tom Hull was supported by “Alternative framework to assess marine ecosystem functioning in shelf seas" (https://projects.noc.ac.uk/altereco/). AlterEco represents a pilot study of a novel monitoring framework to deliver improved spatiotemporal understanding of key shelf sea ecosystem drivers through the use of autonomous systems, primarily underwater gliders. It was funded by the UK National Environment Research Council (NERC), the UK government’s Department for Environment, Food and Rural Affairs (Defra), the World Wide Fund for Nature (WWF) grant numbers NE/P013899/1, NE/P013902/2, NE/P013740/1 and NE/P013864/1.

This work also contributes to the MOOSE network, which is funded by the CNRS-INSU and the French Ministry for Education and Research (ILICO).

# References

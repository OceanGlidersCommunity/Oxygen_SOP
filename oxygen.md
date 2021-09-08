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
*(5) Bastien Y. Queste, Department of Marine Science, University of Gothenburg, Gothenburg, Sweden*
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

## RBR coda T.ODO

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

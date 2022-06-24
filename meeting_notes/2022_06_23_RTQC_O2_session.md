# Real Time 0xygen data management

# Date: June 23 2022, 15:00 - 16:30 CEST

Session chair: Victor Turpin (OceanOPS, France)
Experts : Virginie Racape (POKAPOK, France), Patricia López-García (NOC, UK)
Notes: **need support here**

# Participants
Justin Buck (BODC, UK), Victor Turpin (OceanOPS, France), Soeren Thomsen (LOCEAN, France), Dave Hebert (BIO/DFO Canada), catherine Schmechtig(CNRS,France), Maryam Hassani (UT,Iran), Kimmo Tikka (FMI, Finland), Carolina Amadio (OGS), Anthony Bosse (MIO, France), Claire Gourcuff (Euro-Argo),Thania Papapostolou (HCMR), Pierre Testor (LOCEAN/CNRS, France), Corentin Guyot (Ifremer), Antonio Bussani (OGS)

# Agenda
1) Workshop objectives 
2) Assessment of the Real Time Oxygen data uptake
3) [The Oxygen SOP](https://oceangliderscommunity.github.io/Oxygen_SOP/sections/authors_SOP_development_process.html)
    - recommended configuration
    - pending case of uncompensated salinity
    - RTQC
    - Oxygen time respond correction in real time: the example of Argo
4) Wrap up

View presentation [here](https://github.com/OceanGlidersCommunity/Oxygen_SOP/blob/main/meeting_notes/WS6%20-%20Focus%20on%20Real%20Time%20data%20management%20of%20Oxygen%20Data%20V5.pdf)

# Meeting notes
Victor: Presents intro slides
-huge gap between what is declared in the GDAC and what is really usable 
-Impossible to recompute DOXY with present glider information
=> need to improve the metadata
-sensor model
-sensor SN
-Calibration date
-Calibration coefficients 

intermediate parameters are also needed 

Virginie Racapé presents the computation table of the ARGO DOXY cookbook http://doi.org/10.13155/39795 

Essential to have a link between the glider parameter name and EGO parameter

RTQC 
-initial QC=3 (there is a need to correct the storage drift)
-Global Range 
-spike and gradient
-stuck value 
-Report PRES_QC and TEMP_QC on DOXY_QC (PSAL)
-Additionnal test for Saturation(Biofouling) in Copernicus product

RT Adjustment 
for Coriolis, all floats are adjusted in NRT (after Five cycles) with an estimated gain applied on the partial pressure of DOXY (PPOX) the new value is compare to GLODAP_V2 

Is it needed for Glider ?


Questions: 
Soeren: If someone does a pre-deploymenet and get's new calibration coefficients. Can they be added in real time to the existing sheet? or how could that work?

Kimmo: Asking again, is it possible, that there is a bug in Aanderaa optode's firmware? (handling calibration coefficients) [Soeren@Kimmo, i think Tom Hull answered this somewhere on GitHub or? Remember he mentioned something. Otherwise ask there again?]

Kimmo: we, actually, need a common API for each sensor, wherefrom identification, properties and qalibrations may be queried. (When glider/argo/… is turned on, it could just ask, which sensors it has, and report in log-files)



Justin: There are 2 considerations for calibration sheets and coefficients, the now and the future. Current calibraiton sheets are largely in PDF and not machine readable, these need a DOI or PID to reamin accessible and linking to from the OG 1.0 file. In future we need electronic versions of ceofficients that can be used in common community tools for derivation and processing.

Justin: the metadata telemetered form gliders on optode model etc is currently ambiguous, e.g. different optode models are installed agianst any of the optode integrations on seagldiers. The metadata configued on the gliders is also enter by human operators to also subejct to human error.

Justin: Some base stations reprocess data, potentially with updated verisons of metadata, so care is needed in handling versions of data form near real time to later versions.


Pierre to Everyone (15:50): French gliders: it was centralized in 2009 and the procedures have evolved in time then but these should be the same for all PIs/deployments for relatively long periods of time

Claire Gourcuff (Euro-Argo ERIC): We should aim at reducing the human intervention as much as possible.


Justin: We need to work on defining the data chain and dependencies from sensor, though to the glider, to the basestation and to the output formats. This differs by platform type. Once this is understood we can then define the data workflows needed for gliders.



JUstin: question for Catherine@ How much resource and time does it take to progress this type of work per sensor? It is will be a key element to include int eh roadmaps.

question for Catherine@ How much resource and time does it take to progress this type of work per sensor? It is will be a key element to include int eh roadmaps.
catherine schmechtig (CNRS, FRANCE) to Everyone (16:12)
@justin, writing documentation or providing calibration factors ?
@catherine, the entire process form beginning to consider what a sensors needs are to having a SoP in place with supporting tools?
@justin a lot of time, I ve been working on that for 10 years (half time) for 6 bgc argo parameters and it is not done yet 



Time response issue: 
https://oceangliderscommunity.github.io/Oxygen_SOP/sections/oxygen_dmqc.html 


Soeren: Calibration coefficient should be updated at the start of the mission, otherwise data are not correct.

Claire : Users of Oxygen data in RT may not have the same requirements in term of quality than the scientists?

Victor : I hope so... otherwise it is useless to spend time on it.

Pierre: gliders do not always do up AND down casts but up OR down casts... see SOP Oxygen for recommandations (need to do up AND down a couple of time every week or so). What about Sprays? They can only do upcasts to my knowledge.


Justin : UK fleet have fast and long time response optode films, depending on the sceitnific application. need to apply different correnction to different type of sensor. Also, slcoum gliders send time, seagliders bin data so different corrections needed here too.



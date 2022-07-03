Welcome to the “Oxygen - Standard Operating Practice (SOP)” room.


Session co-leads: Patricia Lopez-Garcia, Soeren Thomsen, Laurent Coppola, Tom Hull


Skills map around oxygen

There are many people interested in the oxygen (SOP) developed here and many who can provide expertise. The question was: For which variable would you like to have an OceanGliders Standard Operating Procedure (SOP) soon? 


## Agenda
May 12 Wednesday 
	07:00 - 08:30 CEST / 22:00 - 23:30 PDT (May 11) / 13:00 - 14:30 AWST
	Oxygen SOP: Assign people to paragraphs (P. Lopez Garcia, S. Thomsen, Tom Hull) 

Participants: Soeren Thomsen, Tom Hull, Johannes. Hahn, N. Zarokanellos, B. Queste, Charlotte Williams, Chari, Eva Alou, G. Krahmann, J. Whitefield, S. Pearce, J. Allen, D. Correa, Patricia Lopez-Garcia, Emi Anastasopoulou.

Meeting notes:

Link to Oxygen SOP draft document
SOP sections:
Introduction   
Aanderaa Optodes	
Hardware design: blue or black   
Foil type: F or standard   
Calibration equation and firmware versions   
RBR coda T.ODO	
JFE Advantech RINKO	

Pre-deployment operations and calibrations   
Storage	
Integration with gliders	
Mounting location	
Antifouling	
Air saturation quality check   
Pre-deployment lab calibration	
Two point calibration procedure, optode example   
Validation in the tank during ballasting   
Missions execution	
Deployment	
In-situ reference samples	
Calibration during deployment/recovery from a small boat.	
Calibration during deployment/recovery from a ship with a CTD rosette equipped with a calibrated oxygen sensor	
Piloting	
Gather data to help correct for sensor response time:	
Gather data to correct for sensor drift:   
Deep water masses or known anoxic waters   
In-air calibration	
Gather data for in-situ inter-comparisons:   
Biofouling   
Real time quality control (RTQC)   
Post-recovery	operations and calibrations   
Delayed Mode Quality Control (DMQC)   
Sensor drift correction	
Sensor time response correction   
2nd quality control, inter-comparison   
Data delivery to public open access archives:   
Appendix	
References	
Acknowledgement	


→ After reading the SOP for Oxygen:
Add any comment/suggestion you might have in each section
Indicate in which section you would like to contribute to (or if you consider we should contact another expert)
The sections in red are those which need more work and inputs from experts at the moment

Consider that these sections are not fixed; we will follow OBP recommendations for the final document. Therefore, sections can be reorganised, and we can add/remove sections.


→ Next steps and milestones for next meeting (20/5/21):
Adding data examples for problems in different sections and lessons learned on how to identify them. Chari will add information regarding biofouling. 
Get an agreement on how to proceed about information for different regions (different oxygen values, etc.). There is one section for deep waters, maybe adding for shallow waters? Oxygen Minimum Zones, Soeren: We should also mention the vertical O2 gradient as it is not only about the absolute values, 
Gerd to send method he uses for correcting T data
Check we have in the doc very well defined the protocol of how to correct data. Please Hahn and Queste add your inputs.



→ Chat history: 

06:07:49 From  Soeren Thomsen   to  Everyone : https://docs.google.com/document/d/11IaU_ZTeiDda-aMd3GH221BOzWTNxbhtMGUZ3cXwP1g/edit?ts=609ad913#
06:09:31 From  Tom Hull  to  Everyone : Should have mentioned anything about my background. I am not a morning person. working at Cefas with their buoy network and CTD, last 3 years working with seaglider oxygen to air-sea gas exchange studies of the UK shelf with the UEA. aanderaa, RINKO (on the SBE CTD)
06:10:48 From  Soeren Thomsen   to  Everyone : I also missed that we deployed a glider fleet off Peru in the OMZ. But all the hard work was done by Johannes Hahn and Gerd Krahmann.
06:11:47 From  Bastien Queste  to  Everyone : Work-wise: deploying gliders in the Arabian Sea OMZ again from this summer onwards, and maintaining 4 observatories in the Batlic Sea.
06:12:34 From  Charlotte A. J. Williams  to  Everyone : I forgot to mention that I have been using the GEOMAR toolbox developed by Gerd to process some of the glider data from NOC
06:33:02 From  Charlotte A. J. Williams  to  Everyone : There is an issue with CTD temp from the glider though as it is not always measuring the same water either as optode in laminar flow at back (for slocum at least)
06:40:03 From  Soeren Thomsen   to  Everyone : I think Chari also wants to say something
06:41:48 From  Tom Hull  to  Everyone : I think example data is a really good idea
06:42:11 From  Charlotte A. J. Williams  to  Everyone : Yes that would be very useful
06:48:42 From  Gerd Krahmann  to  Everyone : So I am calculating all up-down oxygen differences for
	delays_o = [10:4:50];  <-- these should be foil delays
	delays_t = [0:40:200];  <-- these should be the temp
We do not correct for distance CTD- Opt
I do not have access from here to the results from the fits.
Basically all our deployments are deep water...
06:49:46 From  Soeren Thomsen   to  Everyone : i suggest everyone to write these comments into the document. Or I copy them over later
06:50:00 From  Soeren Thomsen   to  Everyone : To ensure we don’t loose these comments
06:50:36 From  Chari2  to  Everyone : I think you can save the chat at the end of the meeting
06:50:43 From  Soeren Thomsen   to  Everyone : true!
06:52:38 From  Gerd Krahmann  to  Everyone : What are you doing about the times at which the measurements are made on slocums ? CTD times are not Optode times...
I oversample everything (!) to full seconds to have the same times for everything
06:53:01 From  Charlotte A. J. Williams  to  Everyone : or fast response foil maybe?
06:53:18 From  Bastien Queste  to  Everyone : I'm switching to RBR Codas so I get 16Hz and therefore my dt error is less than 0.05s ;)
06:53:51 From  Johannes Hahn  to  Everyone : Maybe the mathematical design of the applied inverse low pass filter is not optimal?
06:54:06 From  Johannes Hahn  to  Everyone : :-)
06:56:29 From  Charlotte A. J. Williams  to  Everyone : is this the best practice doc Chari? This is the one I have used previously and found very helpful: https://imos.org.au/fileadmin/user_upload/shared/ANFOG/ANFOG_QAQC_Best_Practice_Manual_v1.pdf
07:02:04 From  Gerd Krahmann  to  Everyone : Since we at GEOMAR do not use real time data except for piloting/checking there is nothing implemented as rt qc
All is delayed mode for us
07:02:19 From  Bastien Queste  to  Everyone : For RT data we ignore lags as we subsample too much to be able to correct. We also don't get raw data or take the effort to correct, so we actually discard all except returned oxygen saturation, and then calculate concentration from saturation to have an ok absolute value.
07:02:43 From  Bastien Queste  to  Everyone : (and get rid of issues linked to onboard salinity settings)
07:04:02 From  Chari2  to  Everyone : Here is the link to the updated version 3.0: http://content.aodn.org.au/Documents/IMOS/Facilities/Ocean_glider/Delayed_Mode_QAQC_Best_Practice_Manual_OceanGliders_LATEST.pdf
07:04:24 From  Bastien Queste  to  Everyone : @ Gerd : where do you apply your lags? on phase data, on partial pressure data, or on final concentration?
07:06:00 From  Bastien Queste  to  Everyone : I've found best results applying lag corrections at the partial pressure step - but keen to hear what others have found
07:09:38 From  Bastien Queste  to  Everyone : No one?
07:10:03 From  Tom Hull  to  Everyone : I've tried both doing it in phase space and in pp
07:14:38 From  Johannes Hahn  to  Everyone : Regarding lag corrections:Bittig et al. (2018) show, that
07:15:03 From  Gerd Krahmann  to  Everyone : @Bastien  one lag to the CTD temperature goes into the oxygen from phase calculation, and one lag is on the resulting oxygen I think
07:16:11 From  Charlotte A. J. Williams  to  Everyone : I have tried applying to phase
07:16:39 From  Tom Hull  to  Everyone : @Gerd, great that's the approach that looks to be working best for us as well.
07:18:02 From  Johannes Hahn  to  Everyone : egarding lag corrections:Bittig et al. (2018) show, that both (1) application of calibration coefficients to partial pressure or (2) phase are both reasonable. I think, what does this mean for the lag corrections is that both (pp and phase) can be used. However, I guess the optimized variable would be oxygen in the end.
07:19:23 From  Gerd Krahmann  to  Everyone : we tried 500000 schoville chili powder. though not the optode. just made for spicier barnacle soup
07:19:39 From  Patricia LG  to  Everyone : https://repository.oceanbestpractices.org/handle/11329/1362 
07:20:43 From  Soeren Thomsen   to  Everyone : i think Bastien was happy about this spicy cooking tip
07:20:57 From  Bastien Queste  to  Everyone : Oh yeah !!
07:21:24 From  Bastien Queste  to  Everyone : I've got long glider deployments coming up with an upward facing ADCP in Oman... Even long dips in the OMZ don't kill the barnacles
07:21:31 From  Gerd Krahmann  to  Everyone : and the sailors hated handling the glider
07:21:32 From  Bastien Queste  to  Everyone : I'll happily try Vaseline and chili
07:21:58 From  Chari2  to  Everyone : Make sure you wash hands after - could have painfil eyes
07:22:18 From  Nikolaos Zarokanellos  to  Everyone : Good point!
07:22:43 From  Gerd Krahmann  to  Everyone : going to the toilet is also no fun...



May 20 Thursday 
	16:00 - 17:30 CEST / 7:00 - 8:30 PDT / 22:00 - 23:30 AWST
Oxygen SOP: Reviewing of SOP (P. Lopez Garcia, L. Coppola, S. Thomsen, Tom Hull) 

Agenda points:
Real Time Quality Control, status for Oxygen, how can we improve it? What can we learn from the DMQC

Updates from SOP during the Plenary meeting for discussion during this meeting:

General:
Overview paper: How will RT and DM QC chapters align? There is a good chunk of DMQC can also actually be RT
SOP: Real Time QC is the weakest part at the moment
Integration
inputs and examples (e.g in integration with gliders. This will be a very visual part and should include previous experiences)
Sensors
info from other sensors: if people have experience with other sensors, it will be great if they can start filling in the sections where there is a difference between Aanderaa and the Sensor?  For example, the 0 and 100% calibration is the same for optodes and electrodes? (when I worked with electrodes, they consume oxygen, so you need bigger water containers and moving the sensor a lot, etc..)
	tom: drift correction -> more examples from other groups?
Specific regions/ O2 distribution settings
Add a part for Oxygen Minimum Zone, how to work there (i.e. STOX sensor for validation needed?)
Data management / dissimilation 
more input into delivering the oxygen data to repositories yet …

Participants: Soeren Thomsen, Patricia Lopez, Tom Hull, Laurent Coppola, Claire Gourcuff, Johannes Hahn, Gerd Krahmann, Anthony Bosse, Charlotte Williams, Theo, Pierre Testor, Chari, YUmi Song, Johannes Hahn, Gerd Krahmann, Tania Morales, Nikolaos Zarokanellos.


Link to Oxygen SOP draft document
Contents of the SOP and comments: (sections that need more inputs and new sections)
Introduction
Aanderaa Optodes 
Hardware design: blue or black 
Foil type: F or standard
Calibration equation and firmware versions
RBR coda T.ODO
JFE Advantech RINKO
Pre-deployment operations and calibrations
Storage and cleaning
Sensor configuration for deployment (check list?)
Integration with gliders
Mounting location: Spray, Seaglider, Slocum, SeaExplorer
Antifouling
Air saturation quality check
Pre-deployment lab calibration
Two point calibration procedure, optode example
0 / 100 % saturation protocol
Communicating with the sensor using a terminal program and a cable
Calibration procedure
In situ intercomparison in the tank during ballasting 
Missions execution
Deployment 
In-situ reference samples 
In situ intercomparison during deployment/recovery from a small boat.
Calibration during deployment/recovery from a ship with a CTD rosette equipped with a calibrated oxygen sensor
Deploying gliders in Oxygen Minimum Zones (OMZ)
Piloting 
Gather data to help correct for sensor response time: 
Gather data to correct for sensor drift:
Deep water masses or known anoxic waters
In-air calibration 
Gather data for in-situ inter-comparisons: 
Observe data for evidence of biofouling 
DO computation
Real time quality control (RTQC)
Post-recovery operations and calibrations
Delayed Mode Quality Control (DMQC)
Sensor drift correction 
Sensor time response correction 
2nd quality control, inter-comparison
Data delivery to public open access archives:
Appendix
References 
Acknowledgement	


Meeting notes: 
Inputs from Claire: they add information about which variables to use, etc for DO computing. They will write that part and maybe adding it before RTQC and some part there/ 

Data for Spray glider: Chari will contact researchers at Scripps for some info.

Discussion about 0/100% calibration: 
Laurent: old optode in tank to put gliders before deployments, together with Winkler 
Johannes Hahn: agrees with importance of 0/100% calibration, cover different temperature ranges important, 0/100% depends on the general calibration of the sensing foil, certification certificates for a batch but the foil batch is different from a multi point calibration, better foil/optode together, smaller errors, Bittig et al. 2018 for overview.

Soeren: any recommendations on how to proceed for 0/100% when you want to do two temperatures but don’t have a thermostatics bath. Maybe using a fridge, AC,... No experience in tropical regions.
Tom: it will be important to give the different accuracy you can get with the different options (gold calibration, or you need to reduce options, etc.). Tom will start working in this table/document. 
Tom: when doing two points calibration at different temp, the information collected is for DMQC? Johannes: they use the info just for post-processing.
Soeren: could you use calibrations done before the deployment to modify the internal values of the sensor? Johannes: data were used on DMQC.
Gerd: you can not get the better data when you deploy the glider, the corrections have to be done later., full resolution temperature information missing

Biofouling: any possibility of RT detection/correction? we need expertise on this area.

Tom Hull to Everyone (4:50 PM)
ah right so,
TCphase = Rphase - Bphase
and Calphase = TCphase
and Calphase goes into the SVU formula

I think older optodes didn't have Rphase (reference phase)
(or red phase really)
Claire Gourcuff to Everyone (4:50 PM)
Yes, it dépends on optodes model


Soeren: important to give inputs if there is any adaptation if the water masses changes (e.g. strong thermo gradient)

OMZ: Soeren: we don’t need STOX sensor, it’s more for microbiologist to check real values. From previous experience parking the glider a few hours in the OMZ, will produce good data.
also winkler/calibration in extreme strong vertical gradients is an issue
Winkler at 0 oxygen don’t work, DL of 1-2 uM.

Data management: discussion with Victor.
Tom: should we include in this section which data to include? Pierre: The metadata are already identified. 
Gerd: What we need is a documentation about what you have done with the data.
Tom: maybe include final data, raw data and info about the processing in between.
Tania: for real time PLOCAN has to submit oxygen data with all raw data.
Soeren: there is a group already working on RTQC, some inputs will good to add them to the oxygen SOP but not too much.
Claire: check what ARGO has done and get some tips (for flags)
Gerd: just use 30 s timelag, there is enough data to do something
Seaglider are sending a few data points, 
Chari: depends how you operate the glider
Tom: optode salinity set? corrected?
Tania: refers to netcdt
Charlotte A. J. Williams to Everyone (5:09 PM)
and not for BODC netcdf of NOC slocum RT data
Claire: good metadata is needed to do salinity compensation correction for oxygen
Claire: documentation is key
Laurent: table with “real” in-situ accuracy, past experience, 
everyone can provide errors from past experiment, z-depency, i.e. within strong vertical gradients the biggest error results from time lag correction
Soeren: expand on in-air calibration,  See: Nicholson & Feen 2017, Slocum in-air calibration 
special bracket has been used to attached the oxygen sensor (Figure 1)


Pierre: community review needed, open for 6 months, with a clear deadline

Community review process: 
get this version finished with the main authors (maybe two month to finish all contributions? people are really adding information from their own experience/data, so it should be quick) and deadline mid July? 
Soeren: I will be on a research cruise from June 8 - July 3- OK for me, I can keep doing cleaning and formatting (Patry)
Mid July: Tom and Soeren move it to an online document (put a few editors, train them), 
End of July: advertise it through all kind of channels (OceanGliders mail also as pdf) but insist on that comments are made via version controlling on the online document, combine with training of the community, example for other SOPs
6 months community review
Final SOP submission for peer-review


Gerd Krahmann: I have added some thoughts to RTQC in the SOP document. I have been unable to copy them here and don’t want to write them again...

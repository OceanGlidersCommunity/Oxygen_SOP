# Introduction

This standard operating procedure (SOP) document for dissolved oxygen (DO) aims to guide the user through the steps necessary to collect good quality dissolved oxygen data using ocean gliders for both real time and post deployment data streams.

## Overview cheat sheet
The most important actions to be taken are summarized in this simple cheat sheet below.
This short summary allows the reader check under time pressure whether key points are taken into account prior to deployment.
We recommend reading each chapter in detail to ensure the best quality data.

**Pre-deployment/Deployment**  
(1) Check that sensors are in good condition, and you have selected the best option for the planned mission.  
    - BEST: Do two-point calibration ({numref}`two_point_calibration`).  
(2) Mount the sensor(s) ({numref}`sensors_integration`).  
(3) Configure sensor for deployment ({numref}`sensor_configuration`). Make sure your glider is configured to record phase with correct timings.  
(4) Keep sensor foil wet at least 8 hours before deployment. If it cannot be kept submerged in water, have a wet sponge covering the foil ({numref}`storage_and_cleaning`).  
(5) Do two-point calibration shortly before deployment ({numref}`two_point_calibration`).  
(6) In-situ reference measurements, recommended using hierarchy of decreasing quality:
    - BEST: Optodes attached to a CTD ({numref}`deployment_ship_CTD`). 
    - BEST: multiple co-located CTD casts in well mixed waters (including Winkler samples at different depths) and in-air drift correction.
    - GOOD: single point Winkler sample and CTD from nearby and no drift correction (see section {numref}`deployment_small_boat`).
    - OK: in-air calibration only ({numref}`in-air-calibration`).

**Mission and Real Time data flow** ({numref}`mission-execution`)  
(7) Ensure data stream is set up correctly including relevant metadata is sent to allow real time data corrections ({numref}`rtqc`).

**Recovery** ({numref}`post-recovery`)  
(8) Keep sensor foil wet until finish post deployment in-situ reference measurements.  
(9) Download data.  
(10) In-situ reference measurements, using hierarchy of decreasing quality as mentioned above.  
(11) Clean and store the sensor.  

**DMQC** ({numref}`dmqc`)  
(12) Determine and correct optode lag. 

**Data sharing** ({numref}`data-sharing`)  
(13) Share high quality data in public open access archives.

## Overview sensor glider combinations

*Table 1: List of the known sensor/glider combinations. We aim to cover all combinations in this document.*

| Sensor / Glider  |  Slocum |  Autosub/ ALR (NOC) |  Seaglider | Deepglider  |  SeaExplorer |  Spray |  Information |
|---|---|---|---|---|---|---|---|
| Aanderaa 3835, 4330, 4330F, 4831, 4831F and 5013 optodes  | X |   | X | X |   |   | [Link](https://www.aanderaa.com/productsdetail.php?Oxygen-Optodes-2) |
| RINKO-II  | X |   |   |   |   |  | [Link](https://www.jfe-advantech.co.jp/eng/ocean/rinko/rinko22d.html) |
| RINKO- AROD FT  |   |   |   |   | X |   | [Link](https://www.jfe-advantech.co.jp/eng/ocean/rinko/rinko-ft.html) |
| SBE 43 and 43F  |   | X | X |   | X |   | [Link](https://www.seabird.com/sbe-43-dissolved-oxygen-sensor-with-titanium-housing-mcbh-connector-0-5-mil-profiling-membrane-standard-43-plenum/product?id=54627923854) |
| SBE 63  |   |   |   |   |   | X | [Link](https://www.seabird.com/oxygen-sensors/sbe-63-optical-dissolved-oxygen-sensor/family?productCategoryId=54627869933) |
|  RBRcoda T.ODO |   |   |   |   | X |   | [Link](https://rbr-global.com/products/sensors/rbrcoda-odo) |
|  Contros Hydroflash (1) |   |   | X |   |   |   | [Link](https://www.kongsberg.com/globalassets/maritime/km-products/product-documents/hydroflash-accurate-fast-and-versatile-oxygen-optode/Download) |

(1) The advanced, optical sensor is based on the principle of fluorescence quenching. Contros are no longer in operation, the sensors cannot be calibrated and are likely to become obsolete in the future. 

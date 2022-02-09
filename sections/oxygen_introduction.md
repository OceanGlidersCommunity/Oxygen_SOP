# Introduction

This standard operating procedure (SOP) document for dissolved oxygen (DO) aims to guide the user through the steps necessary to collect good quality dissolved oxygen data using ocean gliders for both real time and post deployment data streams.

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

(1)The advanced, optical sensor is based on the principle of fluorescence quenching. Contros are no longer in operation, the sensors cannot be calibrated so they are likely to become obsolete in the future. 

## Summary of all steps recommended in this SOP.

The most important steps described in this SOP can be summarised in this simple To-Do list:  

**Pre-deployment/Deployment**
1. Check that sensors are in good condition and you have selected the best option for the planned mission.
    • BEST: Do two-point calibration (see section {numref}`Two_point_calibration_procedure,_optode_example`).
2. Mount the sensor(s) (see section {numref}`Sensor_integration_with_gliders`). 
3. Configure sensor for deployment (see section {numref}`Sensor_configuration_for_deployment`). Make sure your glider is configured to record phase with correct timings.
4. Keep sensor foil wet at least 8 hours before deployment. If it cannot be kept submerged in water, have a wet sponge covering the foil (see section {numref}`Storage_and_cleaning`).
5. Do two-point calibration shortly before deployment (see section {numref}`Two_point_calibration_procedure,_optode_example`).
6. In-situ reference measurements recommended to do, using hierarchy of decreasing quality:
    • BEST: Optodes attached to a CTD (see section {numref}`Calibration_during_deployment/recovery_from_a ship_with_a_CTD_rosette_equipped_with_a_calibrated_oxygen_sensor`).
    • BEST: multiple co-located CTD casts in well mixed waters (including Winkler samples at different depths) and in-air drift correction.
    • GOOD: single point Winkler sample and CTD from nearby and no drift correction (see section {numref}`In_situ_intercomparison_during_deployment/recovery_from_a_small_boat`).
    • OK: in-air calibration only (see section {numref}`In-air_calibration`).

**Recovery** (Section {numref}`Post-recovery_operations_and_calibrations`).
7. Keep sensor foil wet until finish in-situ reference mesurements (Point 9).
8. Download data.
9. In-situ reference measurements recommended to do, using hierarchy of decreasing quality as mentioned in Point 6.
10. Clean and store the sensor.

**DMQC** (Section {numref}`dmqc`).
11. Determine and correct optode lag

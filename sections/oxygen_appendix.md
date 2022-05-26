# Appendices

(sensor_calibration_commands)=
## Optodes commands

As discussed in {numref}`calibration_procedure` the commands required to calibrate an optode varies depending on optode firmware version.
Here we present the key commands needed to perform a 0-100 calibration for all known optode variants. 

*NOTE: A multipoint DO calibration is necessary to obtain new foil coefficients and that can be done at the manufacturer laboratories or in any fully equipped calibration lab. These values shouldn’t be changed otherwise.*

The framework 3 firmware saw many changes to the output and commands from the optodes which are summarized in the optode manual Appendix 11.
For optode calibration the key changes are:

- `do stop` and `do start` are now simply `stop` and `start`.
- `set interval(0)` does not switch the optode to polled mode, `enable polled mode` is now used.

Certain settings within an optode are protected, such that an unlocking command needs to be entered before the setting can be changed, these are `passkey` or `protect` depending on firmware.

It is recommended not to set the sampling rate of the optode too high during calibration to avoid self heating. We suggest a 30-second interval is appropriate.

(comm_sensor_terminal_cable)=
### Communicating with the sensor using a terminal program and a cable
When the DO sensor is disconnected from the glider connect the sensor to a PC by using the cable (Cable #3855 for 4330/4835 optodes, Cable #5335 for 4831).
These cables can be purchased from Aanderaa and provide power to the optode via USB.

The following terminal configuration works for all optode types:

- 9600 baud rate
- 8 data bits
- 1 stop bit
- No parity
- Xon/Xoff flow control on
- Local echo
- CR+LF receive and transmit

### Framework 3 (since 2013)

4835 optodes with a serial number greater than 300, 4330 optodes with a serial number greater than 1000 and all 4831 optodes are using the Framework 3 command set.

1. Immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get all` - to see the current optode configuration
1. `set passkey(1000)` - to allow protected settings to be modified
1. `set enable polled mode(no)` - if the optode is set to polled mode for your glider
1. `set interval(30)` - to set the optode to collect data every 30 seconds
1. `start` - to start measuring data
1. wait for the temperature and oxygen measurements to stabilize. Variance between samples should be less than ±0.05 °C and ±0.1 µmol L<sup>-1</sup>.
1. Record the local atmospheric air pressure in hPa
1. `do collectcaldatasat` - to collect data for the 100 % data point and update the optode settings
1. `set caldataapress(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilized (several minutes)
1. `do collectcaldatazero` - to collect data for the 0 % data point and update the optode settings
1. `do calibrate` - to finalize the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilization
1. `set interval(X)` and `set enable polled mode(X)` to return the optodes back the sampling interval and mode required by your glider.

### Older type 4835 and 4330 (pre-2013)

4835 optodes with a serial number less than 300 and 4330 optodes with a serial number less than 1000 use the following command set.
These optodes can use two different levels of passkey (1 and 1000) depending on which setting needs to be changed.

1. Immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get all` - to see the current optode configuration
1. `set protect(1000)` - to allow protected settings to be modified
1. `set interval(30)` - to set the optode to collect data every 30 seconds
1. `set enable polled mode(no)` - if the optode is set to polled mode for your glider
1. Wait for the temperature and oxygen measurements to stabilize. Variance between samples should be less than ±0.05 °C and ±0.1 µmol L<sup>-1</sup> (or ±0.5 for µmol L<sup>-1</sup> 4330F)
1. record the local atmospheric air pressure in hPa
1. `do collectcaldatasat` - to collect data for the 100 % data point and update the optode settings
1. `do caldataapress(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilized (several minutes)
1. `set collectcaldatazero` - to collect data for the 0 % data point and update the optode settings
1. `do calibrate` - to finalize the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilization
1. `set interval(X)` and `set enable polled mode(X)` to return the optodes back the sampling interval and mode required by your glider.

### Type 3830 and 3835

1. Immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get_all` - to see the current optode configuration
1. `set_protect(1)` - to allow protected settings to be modified
1. `set_interval(30)` - to set the optode to collect data every 30 seconds
1. wait for the temperature and oxygen measurements to stabilize. Variance between samples should be less than ±0.1 °C and ±0.5 µmol L<sup>-1</sup>.
1. Record the local atmospheric air pressure in hPa
1. `do_calair` - to collect data for the 100 % data point and update the optode settings
1. `set_calairpressure(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilized (several minutes)
1. `do_calzero` - to collect data for the 0 % data point and update the optode settings
1. `do_calibrate` - to finalize the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilization
1. `set_protect(1)` - to allow protected settings to be modified
1. `set_interval(X)` to return the optodes back the sampling interval required by your glider. With `X` set to 0 being polled mode.

# Appendices

(optode_calibration_commands)=
## Optodes commands

As discussed in section {numref}`comm_sensor_terminal_cable` the commands required to calibrate an optode varies depending on optode firmware version.
Here we present the key commands needed to perform a 0-100 calibration for all known optode variants.

The framework 3 firmware saw many changes to the output and commands from the optodes which are summarised in the optode manual Appendix 11.
For optode calibration the key changes are:
- `do stop` and `do start` are now simply `stop` and `start`.
- `set interval(0)` does not switch the optode to polled mode, `enable polled mode` is now used.

Certain settings within an optode are protected, such that an unlocking command needs to be entered before the setting can be changed, these are `passkey` or `protect` depending on firmware.

### Framework 3 (since 2013)

4835 optodes with a serial number greater than 300, 4330 optodes with a serial number greater than 1000 and all 4831 optodes are using the Framework 3 command set.

1. immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get all` - to see the current optode configuration
1. `set passkey(1000)` - to allow protected settings to be modified
1. `set interval(30)` - to set the optode to collect data every 30 seconds
1. XXX `save`
1. XXX `start` - to start collecting data
1. wait for the temperature and oxygen measurements have stabilised
1. record the local atmospheric air pressure in hPa
1. `do collectcaldatasat` - to collect data for the 100 % data point and update the optode settings
1. `set caldataapress(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilised (several minutes)
1. `do collectcaldatazero` - to collect data for the 0 % data point and update the optode settings
1. `do calibrate` - to finalise the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilisation

### Older type 4835 and 4330 (pre 2013)

4835 optodes with a serial number less than 300 and 4330 optodes with a serial number less than 1000 use the following command set.

XXX note these optodes use two different levels of passkey (1 and 1000) depending on which setting needs to be changed.

1. immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get all` - to see the current optode configuration
1. `set passkey(1)` - to allow protected settings to be modified
1. `set interval(30)` - to set the optode to collect data every 30 seconds
1. XXX ?polled mode
1. XXX `save`
1. XXX `do start` - to start collecting data
1. wait for the temperature and oxygen measurements have stabilised
1. record the local atmospheric air pressure in hPa
1. `set passkey(1000)` - to allow protected settings to be modified
1. `do collectcaldatasat` - to collect data for the 100 % data point and update the optode settings
1. `do caldataapress(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilised (several minutes)
1. `set collectcaldatazero` - to collect data for the 0 % data point and update the optode settings
1. `do calibrate` - to finalise the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilisation

### Type 3830 and 3835

1. immerse the optode in the 100 % solution
1. connect to the optode and open a terminal session
1. configure your terminal to log output to a file
1. `get_all` - to see the current optode configuration
1. `set_protect(1)` - to allow protected settings to be modified
1. `set_interval(30)` - to set the optode to collect data every 30 seconds
1. wait for the temperature and oxygen measurements have stabilised
1. record the local atmospheric air pressure in hPa
1. `do_calair` - to collect data for the 100 % data point and update the optode settings
1. `set_calairpressure(XXXX.X)` - to update the local air pressure where XXXX.X is the pressure in hPa
1. immerse the optode in the 0 % solution
1. wait for the temperature and oxygen measurements have stabilised (several minutes)
1. `do_calzero` - to collect data for the 0 % data point and update the optode settings
1. `do_calibrate` - to finalise the calibration and update the optode settings
1. rinse the optode very thoroughly and return it to the 100 % solution and confirm the optode is reading correctly after 10 minutes of stabilisation
1. `set_protect(1)` - to allow protected settings to be modified
1. `set_interval(X)` to return the optodes back the sampling interval required by your glider. With `X` set to 0 being polled mode.


The Sensor Front End board is an intermediate board which connects various test stand sensors to the data acquisition system. This board is intended to interface sensors with the Marionette DAQ Rev2.2. The Marionette documentation and board files can be found at https://marionette-daq.github.io/ 


The board allows connections for 44 analog sensors. These are broken into 14 channels which go through this board and to the Marionette board and 30 on this board, which connect to the Marionette via SPI.  Signals sent to the Marionette should be limited to the  0-3V range.

Currently (4/16/21), the 14 channels which go through this board and to the Marionette's ADC are  on sheet 2: Analog and consist of the 4 load cell sensors for thrust detection and 10 4-20mA pressure sensors which are labeled for either 1k PSI or 3k PSI. The signals go through TVS circuit protection before they are sent to the Marionette. The load cells are speced to TE Connectivity MPN: FC2311-0000-1000-L while the pressure sensors are speced to TE Connectivity 1k Sensors: 824-M305100000501KPG and 3k Sensors: M3051-000005-05KPG.

Currently (4/16/21), the 30 channels which are on this board go through TVS circuit protection, to an ADC chip (ADS7953QDBTRQ1), and then sent over SPI to the Marionette; these sensors can be found on sheet 3: Digital and sheet 4: Extra Sensors. These 30 channels consist of 7 thermocouples for temperature sensing, 9 hall effect sensors for valve position sensing, and 14 extra sensor lines which are unallocated. Note: The hall effect sensor lines come from the Valve Indicator board rather than directly from the sensors. 

The ADC channels on the Marionette sample 12-bits at up to 1Msps. The Front End board ADC channels sample 16-bits at 100ksps, which is sent to the Marionette over SPI.

There are 2 power regulators and two power inputs on this board. This board receives 24V from the POE Input Board and 5V from the POE Input Board. The two regulators take the 24V power and step it down to both 12V and 3V3. The 24V input serves as the main power source. The 12V power is used for the Pressure Sensors and is sent off board to the Thrust Plate Amplifier Board. The 5V power is used for the thermocouple amplifier circuits and the ADC reference voltage signal. The 3V3 line is used for the ADC chips. 

## Sensor Front End Block Diagram

![Level 1 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/sensor_front_block.png?raw=true)


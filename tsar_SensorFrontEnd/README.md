This folder contains the Eagle files for the Sensor Front End board. This board is intended to interface sensors with the Marionette DAQ Rev2.2. The Marionette documentation and board files can be found at https://marionette-daq.github.io/ 

The Sensor Front End board is an intermediate board which connects various test stand sensors to the data acquisition system.  The board allows connections for 30 analog sensors. These are broken into 14 channels which are on the Marionette board and 16 on this board, which connect to the Marionette with SPI.  Signals sent to the Marionette should be limited to the  0-3V range.

The adc channels on the Marionette sample 12-bits at upto 1Msps. The Front End board adc channels sample 16-bits at 100ksps, which is sent to the Marionette over SPI.

## Sensor Front End Block Diagram

![Level 1 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/sensor_front_block.png.png?raw=true)


# Thrust Plate Amplifier

This board amplifies the signals of the four load cells present on the thrust plate. The thrust plate measures the thrust of the liquid fuel engine. The load cells are compression only using part number FC2311-0000-1000-L. The signals from the amplifier are sent to the Sensor Front End board. This amplifier board must be as close as possible to the load cells on the thrust plate; otherwise the signals will be degraded and invalid. 

The thrust plate amplifier is powered by the Sensor Front End board's 12V rail.

## POE+ Block Diagram

![Level 1 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/thrust_plate_amplifier_block.png?raw=true)

# Actuator Controller

All valve and ignitor control is done via the Actuator Controller, which is currently implemented using a Nucleo mounted on a PCB. 

This board reads commands and data from the BeagleBone-AI over USB cable which it uses to switch test stand states and perform an Automatic Shutdown in the event of a system failure. Failure is defined as non-nominal sensor conditions; meaning that if pressure and/or temperature readings are outside of nominal ranges or if the physical state of the valves do not match the expected state of the valves (i.e. a valve is potentially stuck or frozen) then the system will go into an automatic shutdown state. The automatic shutdown state purges all propellants from the lines, depressurizes the system, and returns all valves to the Safety State (unpowered). This Automatic Shutdown can be triggered by the Actuator Controller automatically and it can be commanded by the user. 

The Actuator Controller requires a consistent heartbeat and emergency response code. If for some reason this heartbeat stops, or any other emergency indicator is tripped, the Actuator Controller will execute the emergency shutdown routine in accordance with the emergency response code most recently sent.

The Actuator Controller is also connected via UART to the Valve Indicator board. This connection is solely for sending the current state updates to the Valve Indicator board for other purposes. There is no data coming to the Actuator Controller from the Valve Indicator. 

The Nucleo board is powered by the USB cable from the BeagleBone-AI. The valves and ignitor are powered by a 24V power input coming from the Test Stand Battery. There is one 24V to 12V regulator on this board, it is used for an valve which runs at 12V; all other valves run at 24V. The 24V battery power is isolated from the Nucleo by the Mosfet circuits on sheet 2; the GPIO pins from the Nucleo trigger the Mosfets and allow the 24V power to switch on or restrict off the valves.


## Actuator Controller Block Diagram

![ac_block](https://github.com/psas/tsar-hardware/blob/master/images/Actuator_Controller_Block.png?raw=true)

## Actuator Controller Software

All actuator control software and documentation can be found [here](https://github.com/psas/tsar-software). Specifically, [the testing software](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Test), [the firmware](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Firmware), and [the state machine](https://github.com/psas/tsar-software/tree/master/state-machine)
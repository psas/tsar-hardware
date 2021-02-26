# Actuator Controller

The Actuator Controller's purpose is kept as simple as possible: It is to reliably relay control instructions from the Central Manager (the BeagleBone-AI), and at all times monitor basic sensor inputs and the connection to the Central Manager for signs of a failure. Failure is defined as non-nominal sensor conditions; meaning that if pressure and/or temperature readings are outside of nominal ranges or if the physical state of the valves do not match the expected state of the valves (i.e. a valve is potentially stuck or frozen) then the system will go into an automatic shutdown state. The automatic shutdown state purges all propellants from the lines, depressurizes the system, and returns all valves to the Safety State (unpowered). The Actuator Controller requires a consistent heartbeat and emergency response code. If for some reason this heartbeat stops, or any other emergency indicator is tripped, the Actuator Controller will execute the emergency shutdown routine in accordance with the emergency response code most recently sent.

All actuator control is done via the Actuator Controller, which is currently implemented using a Nucleo mounted on a PCB.

The Actuator Controller is the central pathway for all control over actuators. It serves as a final defense against system failure. Its programming is kept as simple as possible, and is focussed solely on producing reliable control signals for all actuators on the test stand. 


## Actuator Controller Block Diagram

![ac_block](https://github.com/psas/tsar-hardware/blob/master/images/Actuator_Controller_Block.png?raw=true)

## Actuator Controller Software

All actuator control software and documentation can be found [here](https://github.com/psas/tsar-software). Specifically, [the testing software](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Test), [the firmware](https://github.com/psas/tsar-software/tree/master/Actuator%20Controller%20Firmware), and [the state machine](https://github.com/psas/tsar-software/tree/master/state-machine)
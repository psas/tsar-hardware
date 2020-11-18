# Tsar Hardware
Hardware for the Test Stand Automation and Regulation project that runs [PSAS' Liquid Fuel Engine Test Stand](https://github.com/psas/liquid-engine-test-stand)

The TSAR system controls the test stand at a safe distance with several safety features in place. The system monitors the pressure, temperature, and valve states of the system. For automation software and controls see the [tsar software repo](https://github.com/psas/tsar-software). 

## Tsar Hardware System Architecture 

Below you can see the block diagram of the whole system,

![sys_arch](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture.png?raw=true)

## Systems Within the Repo

Within this repo there are several subsystems.

### LOTO

The LOTO Repo is the Lock-Out Tag-Out subsystem.

![sys_arch_loto](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture_LOTO.png?raw=true)

This system prevents the test stand from being powered while key-holders are past the safety line. 


### Thrust Plate Amplifier

The Thrust Plate Amplifier amplifies the thrust plate signal! WOW!

![sys_arch_tpa](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture_TPA.png?raw=true)


### Actuator Controller

This board communicates with the BB-AI over UART and controls the valves. The processor is a STM32F0 using a Nucleo-board. 

![sys_arch_ac](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture_AC.png?raw=true)

For more information on the software for this board please see [Actuator Controller Code](https://github.com/psas/tsar-software/tree/master/actuator-controller)

### Tsar Sensor Front End

This board collects the data from all of the sensors (temperature, pressure, thrust plate) and conditions the signals to the Marionette for compilation. 

![sys_arch_dib](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture_DIB.png?raw=true)

### Valve Indicator

This board collects the valve position data and compares it to the expected valve state. If there is an error it will display a HEX code over LEDs which valve is misbehaving. 

![sys_arch_ac](https://github.com/psas/tsar-hardware/blob/master/images/TSAR System Architecture_VI.png?raw=true)

For more information on the software for this board please see [Valve Indicator Code](https://github.com/psas/tsar-software)

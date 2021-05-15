# Eagle Schematics & Boards


## Valve Indicator

Purpose:
This board will collect valve position data using hall effect sensors mounted on nine solenoid valves and will report the current commanded state of the valves. 
The processor will compare the expected valve states with the correct reported valve states, 
if the states do not match the processor will output an indication over the LED arrays.
The LED arrays will display specific binary codes to indicate which valve does not match. 
If multiple valves do not match then the LED arrays will display all binary codes one after another based upon priority information.

Inputs:
- POE+ 24V Power
- UART Data
- Nine Hall Effect Sensors
- ST-Link V2 Emulator

Processor:
- STM32F042K

Outputs:
- Three LED Arrays
- One Buzzer
- SD Card Data Backup

### Libraries In Use

- Power Regulators: Diodes Inc. - AZ34063UMTR-G1.lbr
- Test Points: oresat-misc.lbr
- Processor: U-ST-STM32F042K-uC.lbr
- JTAG Emulator Connector: J-Samtec-FTSH-105-XXX-DV-K-ARM-SWD.lbr
- Diode: On Semiconductor - 1N5819G.lbr

### Design Rules

We are using the OshPark design rules for a 2-layer board.

### Safety Bar Level 0 Block Diagram:
![Level 0 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/level0.png?raw=true)

### Safety Bar Level 1 Block Diagram:
![Level 2 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/level1.png?raw=true)

![Level 2 Block Diagram](https://github.com/psas/tsar-hardware/blob/master/images/level1annotated.png?raw=true)

### Extra Pinout
This board is equipped with a 32 pin header to access all unused STM32 pins.

1. PB2
2. +10V
3. PB10
4. PC9
5. PB11
6. PC8
7. PB12
8. PC1
9. PB13
10. PC10
11. PB14
12. PC4
13. PB15
14. PC5
15. PC11
16. PC6
17. GND
18. PC7
19. GND
20. PC12
21. PD2
22. PC3
23. PC14-OSC32_IN
24. BOOT0
25. PC13
26. PB9
27. +3V3
28. PC0
29. PC15_OSC32_OUT
30. PC2
31. GND
32. GND



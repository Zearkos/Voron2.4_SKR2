# Voron2.4_SKR2
Tentative Configs and changes to add use of SKR2 boards in Voron Documentation.

20JUN: Added Default configuration, Wiring Diagram PDF, images used in Wiring Diagram.

# SUMMARY OF CHANGES:
## File: [SKR2_Config.cfg](https://github.com/Zearkos/Voron2.4_SKR2/blob/main/Voron2_SKR2_Config.cfg)
Original file was [Voron2_SKR_14_Config.cfg](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/firmware/klipper_configurations/SKR_1.4/Voron2_SKR_14_Config.cfg)

1. Remapped all pins to new naming convention on SKR2 board.
	- Lines: Multiple
2. Added [output_pin motor_power] and a multi-pin named "output_power"  		
	- Lines: 95-100
	> [output_pin motor_power] only allows for one pin to be listed, but both boards must have power applied or UART will fail.  Multi-pin solves issue without over-complicating the fix.
	
## File: [SKR2 (Rev B) Wiring Diagram.pdf](https://github.com/Zearkos/Voron2.4_SKR2/blob/main/SKR2%20(Rev%20B)%20Wiring%20Diagram.pdf)
Mimic'd file [Voron2_SKR_14_Wiring.pdf](https://github.com/VoronDesign/Voron-2/blob/Voron2.4/firmware/klipper_configurations/SKR_1.4/Voron2_SKR_14_Wiring.pdf)
1. Generated new diagrams using SKR2 board image.
2. Added Board Revision check and Addendum A with reference images of MOSFETs.
> Don't use the REV A boards.  The workaround is annoying, and users are better off returning their boards to the vendor.
3. Added green "Install Jumpers" box around "U disk/RRF Wifi" jumper pad. 
> Tested with jumpers in both positions, no change in activation or features for Klipper. 
4. Added stepper driver diagrams, with guidance to NOT cut diag pins.
>Sensorless homing now requires a jumper on the pins to the side of the diag pin.  Jumper not installed, no need to cut pin.
5. Moved Probe Power pins on Z board from FAN2 from SKR 1.4 to FAN3 on SKR2.
> -NOTE: No Activation Pin required in Firmware to power the Probe with this change.  Probe will always receive 24v (if board powered by 24V)

TO DO:

Add section noting which settings to use for "make menuconfig" for proper firmware for SKR2
> Need to copy data from Kevin's generic SKR2 cfg.  As follows:
```
# This file contains common pin mappings for the BigTreeTech SKR 2.
# To use this config, the firmware should be compiled for the
# STM32F407 with a "32KiB bootloader".
```

      

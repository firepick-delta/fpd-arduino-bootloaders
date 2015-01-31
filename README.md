### FirePick Delta Bootloaders for Arduino IDE

#### Summary / Context

This is a mashup of:

* mega1284duino: https://github.com/cano64/mega1284duino
* mighty-1284p: https://github.com/maniacbug/mighty-1284p

The purpose of this fork is to get our EMC01 motion controller board, that is based on an ATmega1284P, to work with our Marlin fork.  Because Atmega1284P is not officially supported in Arduino, the files within this repo are needed to trick Arduino into supporting it.  While other Marlin boards have been successfully run on Sanguinololu (Atmega644P @ 16 MHz) boards, we wanted to go with the Atmega1284P at 20 MHz.  There are existing 1284p arduino shims out there, however none but Mega1284duino supported 20 MHz.  Even though the Mega1284duino supports 1284P at 20 MHz, the Arduino IO pins DO NOT line up with those in the Marlin 'fastio.h' file.  Therefore, our fork of mega1284duino is needed to get everything working together... 

#### Features

This mashup provides what I feel is the best and most up-to-date way to interface arduino, the atmega1284p, and the firepick delta emc01 motion controller board in its current state.  This includes:

* Atmega1284p
* 20 MHz
* Optiboot bootloader (bootloaders/optiboot/optiboot_atmega1284p_slow.hex)
* Lists fuses correctly
* Marlin/Sprinter/Repetier fastio.h compatible (changes to variants/emc01/pins_arduino.h)
* Latest Arduino core files (All of the existing 1284p shims out there are outdated by quite a few arduino versions)
* Named properly so it's easy to find in the Arduino IDE among all the other entries under 'Tools->Board'

Hope that made sense.  Please email njansen1@gmail.com for any further questions about the fork.


#### Licensing

* mega1284duino is licensed GPL v2.  
* Optiboot is licensed GPL v2.
* Arduino is licensed GPL v2.  Arduino uses the GNU avr-gcc toolchain, avrdude, avr-libc, and code from Processing and Wiring.
* The changes that I've made to this repo for FirePick Delta usage are therefore GPL v2, however, other parts of the FirePick Delta project are licensed under other open-source terms.
PlatformIO
==========


**Quick Links:** `Home Page <http://platformio.org>`_ |
`PlatformIO Plus <https://pioplus.com>`_ |
`PlatformIO IDE <http://platformio.org/platformio-ide>`_ |
`Project Examples <https://github.com/platformio/platformio-examples/>`_ |
`Docs <http://docs.platformio.org>`_ |
`Donate <http://platformio.org/donate>`_ |
`Contact Us <https://pioplus.com/contact.html>`_


--------

* `PlatformIO IDE <http://platformio.org/platformio-ide>`_
* `PlatformIO Core <http://docs.platformio.org/page/core.html>`_
* `PIO Remote™ <http://docs.platformio.org/page/plus/pio-remote.html>`_
* `PIO Unified Debugger <http://docs.platformio.org/page/plus/debugging.html>`_
* `PIO Unit Testing <http://docs.platformio.org/page/plus/unit-testing.html>`_
* `PIO Delivery™ <http://platformio.org/pricing#solution-pio-delivery>`_
* `Cloud Builder <http://platformio.org/pricing#solution-cloud-builder>`_

Registry
--------

* `Libraries <http://platformio.org/lib>`_
* `Development Platforms <http://platformio.org/platforms>`_
* `Frameworks <http://platformio.org/frameworks>`_
* `Embedded Boards <http://platformio.org/boards>`_

Solutions
---------

* `Library Manager <http://docs.platformio.org/page/librarymanager/index.html>`_
* `Cloud IDEs Integration <http://platformio.org/pricing#solution-cloud-ide>`_
* `Standalone IDEs Integration <http://docs.platformio.org/page/ide.html#other-ide>`_
* `Continuous Integration <http://docs.platformio.org/page/ci/index.html>`_

Development Platforms
---------------------

* `Atmel AVR <http://platformio.org/platforms/atmelavr>`_
* `Atmel SAM <http://platformio.org/platforms/atmelsam>`_
* `Espressif 32 <http://platformio.org/platforms/espressif32>`_
* `Espressif 8266 <http://platformio.org/platforms/espressif8266>`_
* `Freescale Kinetis <http://platformio.org/platforms/freescalekinetis>`_
* `Intel ARC32 <http://platformio.org/platforms/intel_arc32>`_
* `Lattice iCE40 <http://platformio.org/platforms/lattice_ice40>`_
* `Maxim 32 <http://platformio.org/platforms/maxim32>`_
* `Microchip PIC32 <http://platformio.org/platforms/microchippic32>`_
* `Nordic nRF51 <http://platformio.org/platforms/nordicnrf51>`_
* `Nordic nRF52 <http://platformio.org/platforms/nordicnrf52>`_
* `NXP LPC <http://platformio.org/platforms/nxplpc>`_
* `Silicon Labs EFM32 <http://platformio.org/platforms/siliconlabsefm32>`_
* `ST STM32 <http://platformio.org/platforms/ststm32>`_
* `Teensy <http://platformio.org/platforms/teensy>`_
* `TI MSP430 <http://platformio.org/platforms/timsp430>`_
* `TI Tiva <http://platformio.org/platforms/titiva>`_
* `WIZNet W7500 <http://platformio.org/platforms/wiznet7500>`_

Frameworks
----------

* `Arduino <http://platformio.org/frameworks/arduino>`_
* `ARTIK SDK <http://platformio.org/frameworks/artik-sdk>`_
* `CMSIS <http://platformio.org/frameworks/cmsis>`_
* `Energia <http://platformio.org/frameworks/energia>`_
* `ESP-IDF <http://platformio.org/frameworks/espidf>`_
* `libOpenCM3 <http://platformio.org/frameworks/libopencm3>`_
* `mbed <http://platformio.org/frameworks/mbed>`_
* `Pumbaa <http://platformio.org/frameworks/pumbaa>`_
* `Simba <http://platformio.org/frameworks/simba>`_
* `SPL <http://platformio.org/frameworks/spl>`_
* `STM32Cube <http://platformio.org/frameworks/stm32cube>`_
* `WiringPi <http://platformio.org/frameworks/wiringpi>`_

Contributing
------------

See `contributing guidelines <https://github.com/platformio/platformio/blob/develop/CONTRIBUTING.md>`_.

License
-------

Copyright (c) 2014-present PlatformIO <contact@platformio.org>

The PlatformIO is licensed under the permissive Apache 2.0 license,
so you can use it in both commercial and personal projects with confidence.




1. Make sure python 2.7 is installed
2. sudo python -c "$(curl -fsSL https://raw.githubusercontent.com/platformio/platformio/develop/scripts/get-platformio.py)"
3. Restart the terminal
4. platformio --help
5. create new direcotry 
   mkdir smartfarm
6. go to it  cd smartfarm
7. Initialize project  
   platformio init --board uno
8. Create main.cpp file and place it to src folder 

/**
 * Blink
 *
 * Turns on an LED on for one second,
 * then off for one second, repeatedly.
 */
#include "Arduino.h"

#ifndef LED_BUILTIN
#define LED_BUILTIN 13
#endif

void setup()
{
  // initialize LED digital pin as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(LED_BUILTIN, HIGH);

  // wait for a second
  delay(1000);

  // turn the LED off by making the voltage LOW
  digitalWrite(LED_BUILTIN, LOW);

   // wait for a second
  delay(1000);
}

9. The final Project structure:

smartfarm
├── lib
│   └── readme.txt
├── platformio.ini
└── src
    └── main.cpp
10.platformio run        Building the file + (download necessary packages)
11.platformio run --target upload      upload the file


12.creat a shellscript
   	#!/bin/bash
	cd smartfarm
	sudo platformio run --target upload 

13. make your script executable: sudo chmod +x /home/pi/smartfarm/launcher.sh
14. execute your script:    sudo /home/pi/smartfarm/launcher.sh

15. Add the shell script the the startup
    cd ~
    sudo nano .bashrc
    Scroll down to the bottom and add the line: /home/pi/smartfarm/launcher.sh
    Ctrl+X, Y, Enter


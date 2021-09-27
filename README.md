# cuplTag
The [cuplTag](https://cupl.co.uk/index.php/cupltag/) firmware runs on an [MSP430FR2155](https://www.ti.com/product/MSP430FR2155). It collects samples from an [HDC2022](https://www.ti.com/product/HDC2022) sensor 
and passes it to the encoder part of [cuplcodec](https://github.com/cuplsensor/cuplcodec) at a used-defined time interval. The output is a URL. This is written to an NFC EEPROM 
([NT3H2111](https://www.nxp.com/docs/en/data-sheet/NT3H2111_2211.pdf)), which is connected to a Type 6 antenna. 
The URL origin is configurable. 

Configuration parameters are written over a serial port at 9600 baud. Alternatively, these are transmitted in an NFC text record.

The firmware spends much of its time in LPM3.5 in order to achieve an average current consumption ~0.5uA, which gives years of operation from a CR1220 coin cell battery.

[Buy one on Crowd Supply!](https://crowdsupply.com/cupl/cupltag)

<img src="cupl-front.jpg" alt="Board photo" width="50%"/>

## Pinout

J30 is a 2.54mm pitch 2x4 way header.

| Pin | Name | Direction | Description       | Note                           |
|-----|------|-----------|-------------------|--------------------------------|
| 1   | TX   | Output    | UART transmit     | Transmit from MSP430           |
| 2   | RX   | Input     | UART receive      | Receive to MSP430              |
| 3   | GND  |           | GND               |                                |
| 4   | TST  | Input     | Spy-Bi-Wire Clock | Also TEST signal for BSL entry |
| 5   | GND  |           | GND               |                                |
| 6   | nRST | I/O       | Spy-Bi-Wire Data  | Also active low RESET signal   |
| 7   | VDD  | Input     | Power in          | +3V3                           |
| 8   | nPRG | Input     | Prog. Mode Enable | Active low                     |

## Documentation 

* [Getting Started](docs/firmware/gettingstarted.rst) by loading the project into Code Composer.
* [Programming](docs/firmware/programming/index.rst) the MSP430.

    
## Licence

### Firmware

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

### Hardware

[CERN Open Hardware Licence Version 2 - Strongly Reciprocal](https://ohwr.org/cern_ohl_s_v2.txt)

### Documentation

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)

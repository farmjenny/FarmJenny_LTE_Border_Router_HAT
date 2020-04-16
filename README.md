# Farm Jenny LTE Border Router HAT
Turn a Raspberry Pi or compatible Single Board Computer with 40-pin header into a feature-packed cellular Border Router. Just add your favorite pre-certified cellular modem.

A Border Router connects a local wireless network to other IP-based networks. This board was designed to implement a Thread Border Router, but its Nordic Semiconductors nRF52840-based radio module can support a variety of wireless protocols, including (Thread, BLE, Zigbee, and proprietary).

![Farm Jenny LTE Border Router HAT](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/images/PCB_ASSY_WITHOUT_MODULE.png)

![OTBR Thread Certified Component](https://openthread.io/images/ot-thread-certified.png)
When this board is used with a Raspberry Pi Model 3B and the OpenThread Border Router (OTBR) software, it is a Thread Certified Component. Learn more [here](https://openthread.io/guides/border-router).

# Features
![Farm Jenny LTE Border Router Features](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/images/features.PNG)

* Socket for Nimbelink(R) or compatible end-certified cellular modem (not included)
* Certified nRF52840-based BLE/Zigbee radio with PA/LNA for long range
* Radio programming via standard Tag-Connect socket
* NFC Tag interface (flex/antenna required)
* Four (4) status LEDs (Power, Cell, BLE/802.15.4, User)
* One (1) momentary pushbutton
* Connector for LEDs/Button on external overlay
* USB interface for full cell modem access
* Pass-thru 40-pin connector for stacking

# Pinout
This board conforms to the electrical specifications at [https://github.com/raspberrypi/hats](https://github.com/raspberrypi/hats). The board does not back-feed power on the 5V pins.  You must provide an adequate power supply for the Pi that can handle the current required by Pi and cell modem. Unless otherwise specified, all I/O uses 3.3V logic levels.

![Farm Jenny LTE Border Router Pinout](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/images/pinout.PNG)

Where practical, the board has been carefully designed to play nicely when stacked with other HATs. Non-essential I/O has been connected using cuttable jumpers on the back side of the board, in case it conflicts with another HAT used in your system.  See below for jumper locations.
![Farm Jenny LTE Border Router Jumper Locations](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/images/BOT_HR.png)

# Mechanical
This board conforms to the mechanical specifications for a Raspberry Pi HAT, refer to:   [https://github.com/raspberrypi/hats/blob/master/hat-board-mechanical.pdf](https://github.com/raspberrypi/hats/blob/master/hat-board-mechanical.pdf)
![Farm Jenny LTE Border Router Mechanicals](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/images/dimensions.JPG)

# Power:
**IMPORTANT** You must provide an adequate power supply for the Pi that can handle the current required by Pi and cell modem. This HAT includes a very robust 3A power supply for the cellular modem with generous bulk capacitance, however depending on the modem model, peak and sustained current demand can be very high.

The HAT draws less than 50mA from the 3.3V power supply of the Pi.

# 2.4GHZ Radio Module
The board includes a Fanstel [BT840XE](https://www.fanstel.com/bt840x-nrf52840-module-with-pa) radio with full modular certification.  This module includes a Power Amplifier (PA) and Low-Noise recieve Amplifier (LNA) for long range and can use a variety of internal and external antennas connected using the u.FL port.  The radio module includes a 32.768kHz crystal for accurate timing or low power sleep modes.

The Radio interfaces with the Pi using a high-speed SPI port, including an optional interrupt line.

By default, the Radio comes programmed with OpenThread Network Co-Processor (NCP) firmware and no bootloader.  Custom programming is available on request.  Firmware can also be programmed using a compatible SWD programmer/debugger and [6-pin Tag-Connect cable](https://www.tag-connect.com/product-category/products/cables/6-pin-target).

# USB Port:
The board includes a micro-USB port (J2) connected to the cellular modem. This connection is for data only. The board CANNOT be powered through this USB connection and is intended for use only when installed on a suitable Single-Board Computer.

# Serial Port:
Connector J1 provides an easy connection point for a serial adapter for development.  Signals are 3.3V logic level and are ESD-protected, but not isolated or buffered.  Use of a UART-to-USB adapter, such as TTL-232RG-VSW3V3-WE or TTL-232RG-VIP-WE from [FTDI](https://www.ftdichip.com/Products/Cables/USBTTLSerial.htm) is recommended.  If you wish to extend this interface outside the end device enclosure, additional protection circuitry or drivers may be necessary.  By reconfiguring the jumpers, the Raspberry Pi's serial port can also be connected to the cellular modem (see pinout for more details).  In most cases, this is not necessary as the cellular modem will enumerate multiple virtual serial ports (e.g., data, AT commands, etc.) over the single USB interface.

# User Interface
TBD

# NFC Tag Interface
TBD

# Additional Resources:
* [Schematic](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/schematic/3000121-Rv0_SCHM%2CPCBA%2CADAPTER%2CGATEWAY%2CCELL-MESH.pdf)
* [Mechanical Drawing](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/mechanical/FARMJENNY-CELL_GATEWAY_PI_HAT-Mechanicals-Rv0.pdf)
* [STEP (3D) Model without modem](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/3d_models/PCBA%2C%20ADAPTER%2C%20GATEWAY%2C%20CELL-MESH.step)
* [STEP (3D) Model with example Nimbelink modem](https://github.com/farmjenny/FarmJenny_LTE_Border_Router_Hat/blob/master/3d_models/PCBA%2C%20ADAPTER%2C%20GATEWAY%2C%20CELL-MESH%20W%20MODULE.step)

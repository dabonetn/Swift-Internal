These are internal Swiftlink compatible High Speed Uart for the Commodore 64/128.
Uses swiftlink drivers in your favorite terminal program/bbs.

Premade units are available on my Tindie store.

https://www.tindie.com/stores/dabone/

I got lazy in the schematics and mainly used busses, so they aren't that easy to follow on paper.

Modem commands are under the Zimodem directory.

Quick install guides are uner the QuickInstallGuides directory.

Much thanks to Dr. Evil Laboratories for designing the original Swiftlink Cart.
And of course Bo Zimmerman for the very excellent Zimodem firmware.

Firmware on this page defaults to:

19200 Baud
Hardware Flow Control (CTS/RTS)




The current zimodem firmware is forked from version "3.5.5"

For usage of zimodem, see the readme in the zimodem directory.
Link232-Wifi is based off the ESP-12, not the ESP32, so No esp32 only features will work.



Changes I've made.

zimodem.ino

Set default flow control to RTS/CTS
# define DEFAULT_FCT FCT_RTSCTS

Comment out RS232_INVERTED to prevent inverted signals using the esp12
// # define RS232_INVERTED 1


2. Changing the default baud rate to 19200
#define DEFAULT_BAUD_RATE 19200



zcommand.ino

1. Changing the address for firmware updates to keep people from locking up their units by installing inverted firmware. If the DCD line on the 6551 isn't held low by default, the chip is disabled.
#ifdef ZIMODEM_ESP32
  if((!doWebGetBytes("www.dabone.xyz", 80, "/otherprojs/guru-latest-version.txt", false, buf, &bufSize))||(bufSize<=0))
    return ZERROR;
#else
  if((!doWebGetBytes("www.dabone.xyz", 80, "/otherprojs/c64net-latest-version.txt", false, buf, &bufSize))||(bufSize<=0))
    return ZERROR;
#endif

2. Changing the firmare response
  serial.prints("Link232-Wifi Zimodem Firmware v");



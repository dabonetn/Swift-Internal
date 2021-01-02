These are internal Swiftlink compatible High Speed Uart for the Commodore 64/128.
Uses swiftlink drivers in your favorite terminal program/bbs.

Premade units are available on my Tindie store.

https://www.tindie.com/stores/dabone/

I got lazy in the schematics and mainly used busses, so they aren't that easy to follow on paper.


Modem commands are under the Zimodem directory.

Quick install guides are uner the QuickInstallGuides directory.

I've added replacement swiftlink drivers for Centipede 128 bbs that allows DE,DF, and D7 usage. (Not with the same driver...)


Much thanks to Dr. Evil Laboratories for designing the original Swiftlink Cart.
And of course Bo Zimmerman for the very excellent Zimodem firmware.

Firmware on this page defaults to:

19200 Baud
Hardware Flow Control (CTS/RTS)




The current zimodem firmware is forked from version "3.5.6"


To update to the current firmware use the command

at&u6502


For usage of zimodem, see the readme in the zimodem directory.
Link232-Wifi is based off the ESP-12, not the ESP32, so No esp32 only features will work.



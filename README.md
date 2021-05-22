# Super Phoenix PCB
## Welcome
This is my contribution to the Super Phoenix PCB.

This is based around the ESP32-C3 processor from Espressif.  It is a successor to the popular ESP8266.

You can check out the [ESP32-C3 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-c3_datasheet_en.pdf)

This project specifically uses the [ESP32-C3-DevKitM-1](https://docs.espressif.com/projects/esp-idf/en/latest/esp32c3/hw-reference/esp32c3/user-guide-devkitm-1.html).

You can order them from [Digikey](https://www.digikey.com/en/products/detail/espressif-systems/ESP32-C3-DEVKITM-1/13684315) or [Mouser](https://www.mouser.com/ProductDetail/Espressif-Systems/ESP32-C3-DevKitM-1?qs=%2Fha2pyFadugxHGixwoNRgyjoJM2GQZovR%2FjTmjaiFq6LaZpmhjW939ll5bKcpIjO).  Digikey has had better stock availability.  If you find some in stock, you should order them right away.

The easiest way to run the board is to plug it into a Solderless Breadboard and power it through a Micro USB connection, which serves as the flashing and Console port as well.  The ESP32-C3-DevKitM-1 has a USB to UART [CP2102N](https://www.silabs.com/documents/public/data-sheets/cp2102n-datasheet.pdf) capable of controlling the Boot and Reset Push Buttons the ESP32-C3 through the DTR and RTS lines.

You can see the most basic setup here: [ESP32-C3 Breadboard](https://github.com/lafarkle/Super-Phoenix/blob/main/docs/esp32-c3-first-flash.png)

You can see the Hardware Reference Manual here: [ESP32-C3-DevKitM-1](https://docs.espressif.com/projects/esp-idf/en/latest/esp32c3/hw-reference/esp32c3/user-guide-devkitm-1.html)

You can see what you need to get started here:  [GETTING_STARTED](https://github.com/lafarkle/Super-Phoenix/blob/main/docs/GETTING_STARTED.md)

# TUDCTF2025-hardware

In this repo you will find the firmware and a library to run MicroBlocks on the TUDCTF2025 ESP32S3 hardware. This version supports alle the hardware components and furthermore, it also supports graphics on an ILI9341 touch screen.

## MicroBlocks Firmware

You can use the [online esptool](https://espressif.github.io/esptool-js/) for flashing your unit. Put your hardware unit in flashing mode by pressing the reset button while holding the boot button. Erase the flash before loading the firmware `firmware_tudctf-lvgl_all.bin`. Set flash address to 0x0.

<img width="766" height="272" alt="image" src="https://github.com/user-attachments/assets/c9fdfae6-6ea5-4bc0-a506-c66104a1573a" />


## Library for TUDCTFESP32S3

In the library `tudctf.ubl` all the hardware components are available. A small demo program showing how to use the hardware (including the IR detection) can be found in `tudctf_demo.ubp'.

## LVGL

In the repo [microblocks_lvgl](https://github.com/ste7anste7an/microblocks_lvgl) you find the MicroBlocks LVGL library and examples in the MicroBlcoks directory. Some preliminary documentation can be found on [Antonsmindstorms.com](https://www.antonsmindstorms.com/docs/lvgl-for-microblocks/) and [in this repo](https://github.com/ste7anste7an/lvgl_for_MicroBlocks)

The cool thing about programming LVGL in MicroBlocks, is that while programming, you see the GUI in real time on the display it self.

## Ordering and connecting a touch screen
The specifications of the display should be:
- ILI9341 controller
- XT2046 touch controller

You can order a cheap ILI9341 display at [TinyTronics](https://www.tinytronics.nl/en/displays/tft/2.4-inch-tft-display-240*320-pixels-with-touchscreen-spi-ili9341). The one from TinyTronics has already the SPI interfaces for the graphics controller and touch controller combined (in order to limit the number of wires). If you order a display with AliExpress, you have to connect the SCLK, MOSI and MISO of the touch controller yourself to the same signals of the graphics controller.

These are the pins on the ESP32S3 board:

| Display | GPIO |
|------|-------|
|TFT_MISO | 12 |
|TFT_MOSI | 13 |
| TFT_SCLK | 14 |
| TFT_CS | 15 |
| TFT_DC | 36 |
| TFT_RST | 37 | 
| TOUCH_CS | 38 |
| LED | 39 | 

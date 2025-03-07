+++
date = '2025-03-04T07:35:57Z'
draft = false
title = 'Pico W5 (Elecrow) Review'
+++

Let's review and play with the Elecrow Pico W5.

The Elecrow Pico W5 is a microcontroller development board based on the RP2040 chip (the same chip used in Raspberry Pi Pico) with enhanced wireless capabilities. Key features include:

- RP2040 microcontroller with dual-core Arm Cortex M0+ processor
- Support for both 2.4GHz and 5GHz WiFi using the BW16 module from AiThinker
- Bluetooth 5 connectivity
- USB-C connector for power and programming
- Compatible with MicroPython, C/C++, and other programming languages


#### Pros

- The dual-band WiFi (2.4GHz and 5GHz) is a significant upgrade over the standard Raspberry Pi Pico W, which only supports 2.4GHz
- RP2040 is a proven microcontroller with good community support
- USB-C connection is more modern than micro-USB found on some other boards


#### Cons

- As a third-party board, it may have less community support than official Raspberry Pi products

# Setting Up MicroPython on Elecrow Pico W5

## Initial Setup

I decided to use MicroPython for my Elecrow Pico W5. Here's how to set it up:

1. Connect the board to your computer via USB
2. Enter bootloader mode:
   - Press and hold the BOOT button
   - While holding BOOT, press and release the RESET button
   - Then release the BOOT button

3. A flash drive should appear on your computer (in my case with the label `RPI-RPI2`)

4. Download the MicroPython firmware from:
   https://www.elecrow.com/download/product/CMB12201R/MicroPython/MicroPython_Demo.zip

5. Extract and locate the file: `RPI_PICO-20240602-v1.23.0.uf2`

6. Copy or drag this file to the flash drive

7. Safely eject the drive and press the RESET button on your board

## Testing with a Blink Example

To test your setup:

1. Open a terminal and connect to the board with:
   ```
   screen /dev/cu.usbmodem2101 115200
   ```
   *Note: Your device name may be different than `cu.usbmodem2101`*

2. Copy and paste the Blink.py example code into the terminal

3. If everything is working correctly, you should see the LED blinking

## Using the WiFi Module

The Pico W5 uses a BW16 WiFi module which can be controlled with AT commands.

- You can find the complete AT command list at:
  https://aithinker-combo-guide.readthedocs.io/en/latest/docs/command-set/index.html

## Future Exploration: OTA Updates

Since the board has WiFi capabilities, Over-The-Air (OTA) updates would be useful. 

Currently, I haven't found a ready-to-use MicroPython example, but there are C language implementations for the Pico W:

- https://github.com/usedbytes/picowota
- https://github.com/usedbytes/picowota_blink

This remains an open area for exploration.

## Useful link
- https://www.elecrow.com/pico-w5-microcontroller-development-boards-rp2040-microcontroller-board-support-wifi-2-4ghz-5ghz-bluetooth5.html?idd=6

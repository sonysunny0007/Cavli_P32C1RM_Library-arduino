# ESP32 Firmware Flashing Guide

This guide explains the process to upload firmware to the ESP32 Series module using the Arduino IDE.

## Steps to Flash Firmware

### 1. **Connect the ESP32 Device**
   - Use a **USB Type B cable** to connect the ESP32 device to your computer.
   - This will **power** the device and initiate **UART communication**.

### 2. **Configure the Board Manager in Arduino IDE**
   - Open **Arduino IDE** and configure the board settings for the ESP32.
   
   - Set the following parameters:
     - **Upload Speed**: 926000 (important for stable flashing).
     - **CPU Frequency**: 40MHz (mandatory for flashing).
     - **Flash Size**: 2MB (mandatory to match the device specifications).

### 3. **Enter Boot Mode**
   - Press and hold the **BOOT button** on the ESP32.
   - While holding the **BOOT button**, press and release the **RESET button**.
   - Once in **BOOT mode**, the device will display a "BOOT" message on the COM port.

### 4. **Upload Firmware**
   - Flash the firmware to the ESP32 module at the configured **upload speed of 926000**.
   
### 5. **Reset the Device**
   - After the firmware upload is complete, **reset** the device by pressing the **RESET button**.
   
Your ESP32 should now be ready with the new firmware.

## Troubleshooting

- Ensure that the **upload speed** and **CPU frequency** are set correctly in the Arduino IDE.
- If the device fails to enter BOOT mode, try pressing the **BOOT** and **RESET** buttons in different sequences until you see the "BOOT" message.

## License

This project is licensed under the terms of the license specified in the source code header. (Replace `****` with the actual license type).

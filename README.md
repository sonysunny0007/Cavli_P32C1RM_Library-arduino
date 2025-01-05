# ESP32 + Cavli C10QM Cellular Modem Integration

This project demonstrates how to integrate the ESP32 with the Cavli C10QM cellular modem, providing different APIs to interact with network services, such as GPRS, SMS, MQTT, CoAP, TCP, UDP, and HTTP. It serves as a getting-started guide for developers interested in cellular modem firmware development.

## Features

- **Modem Reset and Initialization**: Interact with the Cavli C10QM cellular modem for setup and initialization.
- **SIM and Network Attachment**: Wait for eSIM readiness, attach to the network, and configure the preferred network.
- **Data Connection**: Enable packet data and monitor the network connection status.
- **Networking APIs**:
  - SMS functionality.
  - MQTT connectivity for publish/subscribe.
  - CoAP support for sending/receiving data.
  - TCP and UDP communication.
  - HTTP GET/POST/PUT requests.

## Hardware Requirements

- **ESP32 Development Board** (with at least 2MB flash)
- **Cavli C10QM Cellular Modem**
- **SIM card** (with eSIM support, depending on the configuration)

## Software Requirements

- **Arduino IDE** with the ESP32 board manager installed
- **Cavli C10QM Firmware** and necessary libraries (like `C1RMCore.h`)

## Setup Instructions

### 1. **Connect the Hardware**
   - Connect the **ESP32 development board** to your computer via USB Type B cable.
   - Attach the **Cavli C10QM modem** to the ESP32 via UART or other suitable interfaces.

### 2. **Configure the Board in Arduino IDE**
   - Open **Arduino IDE** and install the **ESP32 board package** via the board manager.
   - Select the **ESP32 board** and set the following configuration:
     - **Upload Speed**: 926000
     - **CPU Frequency**: 40MHz (mandatory for flashing)
     - **Flash Size**: 2MB

### 3. **Upload the Firmware**
   - Press and hold the **BOOT button** on the ESP32.
   - While holding the **BOOT button**, press and release the **RESET button** to enter **BOOT mode**.
   - Upload the firmware to the ESP32 via the Arduino IDE.

### 4. **Verify Modem and Network Initialization**
   - After uploading, open the **Serial Monitor** to observe the device's boot-up process.
   - The serial output will show whether the modem, eSIM, and network are initialized successfully.

## Code Overview

This code demonstrates the following steps:

1. **Modem Reset and Initialization**:
   - The modem is reset and initialized using `Network.modemReset()` and `Network.SerialInit()` functions.
   
2. **SIM and Network Attachment**:
   - The code waits for eSIM readiness using `Network.isESIMReady()`.
   - The device will attempt to attach to the network using `Network.isNetworkAttached()`. If the network is not available, it switches to manual mode using `Network.setNetworkManual()`.

3. **Packet Data Enablement**:
   - Once the network is attached, the packet data is enabled with `Network.enablePacketData(true)`.

4. **Networking Functions**:
   - **SMS**: The code includes functions to read and send SMS (commented out for optional use).
   - **MQTT**: Functions for creating an MQTT connection, publishing messages, and subscribing to topics (commented out for optional use).
   - **CoAP**: Functions to create and send CoAP data (commented out for optional use).
   - **TCP/UDP**: Examples of sending and receiving data over TCP and UDP (commented out for optional use).
   - **HTTP**: Example of HTTP POST, GET, and PUT requests (commented out for optional use).

5. **LED Blink**: A simple LED blink in the `loop()` function for visual feedback.

## Example Output

- **Modem Ready**: Indicates the modem has been successfully initialized.
- **eSIM: READY**: Confirms that the eSIM is initialized and ready.
- **Network Operator**: Displays the network operator once the device is connected to the network.
- **Packet Data Attached**: Shows the packet data status once the device is connected to the internet.
- **RF Strength**: Displays signal quality, RSSI, and BER values.

## Troubleshooting

- Ensure the modem is correctly connected and powered.
- Verify the **SIM card** is properly inserted and supports eSIM if required.
- Check the **network availability**; if no network is found, the system will attempt to set a manual network.
- If the firmware fails to upload, ensure the **upload speed** and **CPU frequency** are correctly set.

## License

This project is licensed under the terms of the license specified in the source code header. (Replace `****` with the actual license type).


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

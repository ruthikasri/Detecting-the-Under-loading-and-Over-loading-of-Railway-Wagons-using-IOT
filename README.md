

## Detecting the Underloading and Overloading of Railway Wagons using IOT 

## Introduction

This project implements a system to detect and monitor the loading conditions of railway wagons using IoT technology. The system uses load sensors interfaced with an ESP8266 microcontroller to measure and transmit weight data in real-time to an Adafruit IO dashboard. The system also includes a local LCD display for instant weight readings.

## Features

- **Real-Time Weight Monitoring**: Measures the weight of the load on the wagon using an HX711 load cell module.
- **IoT Integration**: Sends weight data to the Adafruit IO platform for remote monitoring.
- **Local Display**: Displays the measured weight on a 16x2 I2C LCD screen.
- **Calibration**: Adjustable calibration factor for precise weight measurements.
- **MQTT Communication**: Uses MQTT protocol to publish data to the cloud.

## System Components

### Hardware
- **ESP8266**: Microcontroller for data processing and communication.
- **HX711 Load Cell Module**: For weight measurement.
- **16x2 I2C LCD**: For local weight display.
- **Wi-Fi Module**: Built into the ESP8266 for IoT connectivity.

### Software
- **Arduino IDE**: For programming the ESP8266.
- **Adafruit IO**: Cloud platform for data visualization and storage.
- **MQTT Protocol**: For efficient data transmission.

## Prerequisites

- **Arduino IDE**: Install from [Arduino](https://www.arduino.cc/en/software).
- **Adafruit IO Account**: Create an account on [Adafruit IO](https://io.adafruit.com).
- **Libraries**: Install the following libraries via the Arduino Library Manager:
  - `HX711`
  - `LiquidCrystal_I2C`
  - `ESP8266WiFi`
  - `Adafruit_MQTT`

## Installation and Setup

1. **Hardware Connections**:
   - Connect the HX711 load cell module to the ESP8266 as follows:
     - DOUT → D6
     - SCK → D5
   - Connect the 16x2 I2C LCD to the ESP8266 using the appropriate SDA and SCL pins.
   - Power the system using a 5V power supply.

2. **Software Configuration**:
   - Open the code in the Arduino IDE.
   - Update the following fields with your credentials:
     ```cpp
     #define WLAN_SSID       "Your Wi-Fi SSID"
     #define WLAN_PASS       "Your Wi-Fi Password"
     #define AIO_USERNAME    "Your Adafruit IO Username"
     #define AIO_KEY         "Your Adafruit IO Key"
     ```
   - Adjust the `calibration_factor` to match your load cell setup.

3. **Upload the Code**:
   - Select the appropriate board and port in the Arduino IDE.
   - Upload the code to the ESP8266.

4. **Monitor Data**:
   - View weight readings locally on the LCD.
   - Log in to Adafruit IO to monitor data remotely.

## Usage

- The system continuously measures the load and displays the weight on the LCD.
- Weight data is published to the Adafruit IO dashboard every 2 seconds.
- Adjust the calibration factor in the code for precise measurements.

## Troubleshooting

- **No Wi-Fi Connection**: Ensure the SSID and password are correct.
- **Incorrect Weight**: Recalibrate the system using the calibration factor.
- **No Data on Adafruit IO**: Check MQTT connection status in the serial monitor.

## Future Enhancements

- Integrate additional sensors (e.g., temperature, vibration) for comprehensive monitoring.
- Implement predictive maintenance using AI/ML algorithms.
- Expand to support multiple wagons with centralized monitoring.


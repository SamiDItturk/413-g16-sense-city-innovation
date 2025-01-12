# 413-g16-sense-city-innovation

# Project Overview

This project combines multiple sensors and an Edge Impulse TinyML model to create an interactive system that detects specific events such as audio keywords, temperature thresholds, and proximity-based object detection. The system activates LEDs as visual indicators based on the sensor outputs, such as detecting the keyword "Help," specific temperature ranges, or nearby objects.

## Features
- **Audio Classification:** Detects the keyword "Help" using an Edge Impulse TinyML model and activates an LED for 5 seconds.
- **Temperature Monitoring:** Monitors ambient temperature and controls LEDs based on predefined thresholds.
- **Proximity Detection:** Detects objects within a specified range and triggers an LED.

---

# Hardware List

To replicate this project, you will need the following components:

1. **Arduino Nano 33 BLE Sense** (or compatible board with PDM microphone).
2. **HS300x Temperature and Humidity Sensor.**
3. **APDS9960 Proximity Sensor.**
4. **LEDs** (various colors for different functions).
5. **Resistors** (220Ω recommended for LEDs).
6. **Jumper Wires.**
7. **Breadboard.**

---

# Setup Instructions

### 1. Hardware Connections
#### Audio Detection
- The PDM microphone is built into the Arduino Nano 33 BLE Sense board.
- No additional connections are required for this feature.

#### Temperature Monitoring
- Connect the HS300x sensor to the Arduino board:
  - **VCC** to **3.3V**.
  - **GND** to **GND**.
  - **SCL** to **A5**.
  - **SDA** to **A4**.
- Connect a **yellow LED** to **D4** for temperatures 0°C to 29°C.
- Connect a **blue LED** to **D5** for temperatures above 30°C.

#### Proximity Detection
- Connect the APDS9960 sensor to the Arduino board:
  - **VCC** to **3.3V**.
  - **GND** to **GND**.
  - **SCL** to **A5**.
  - **SDA** to **A4**.
- Connect an LED to **D2** for proximity detection (adjust resistor value as necessary).

### 2. Software Setup
#### Prerequisites
1. Download and install the **Arduino IDE** from [Arduino's official site](https://www.arduino.cc/en/software).
2. Install the following libraries from the Arduino Library Manager:
   - **Edge Impulse Inferencing SDK.**
   - **PDM Library.**
   - **Arduino_HS300x.**
   - **Arduino_APDS9960.**

#### Configuration
1. Clone this repository or copy the provided source code.
2. Open the respective `.ino` files in the Arduino IDE for each feature.
3. Ensure the correct board and port are selected in the **Tools** menu.
4. Upload the code to your Arduino Nano 33 BLE Sense.

### 3. Testing the System
- **Audio Detection:** Speak the keyword "Help" and observe the LED connected to **D5** turning on for 5 seconds.
- **Temperature Monitoring:** Simulate temperature changes and check if the corresponding LEDs light up.
- **Proximity Detection:** Move an object near the proximity sensor and verify if the LED connected to **D2** turns on.

---

# Sensor Details

| **Sensor Name**       | **Type**              | **Category**   | **Functionality**                             |
|------------------------|-----------------------|----------------|-----------------------------------------------|
| PDM Microphone         | Audio Sensor         | Input Sensor   | Captures sound waves for keyword detection.  |
| HS300x Temperature Sensor | Environmental Sensor | Input Sensor   | Measures temperature in the surrounding area.|
| APDS9960 Proximity Sensor | Proximity Sensor     | Input Sensor   | Detects nearby objects using infrared light. |

---

# Additional Notes
- Ensure the Edge Impulse model is properly trained and deployed to the Arduino board for accurate keyword detection.
- Adjust thresholds in the code to customize LED activation for your application.
- Visit [Edge Impulse Documentation](https://docs.edgeimpulse.com) for more details on training and deploying TinyML models.

- Link for video demo:  https://drive.google.com/file/d/125qKZEDZ_3fa3YO8BTRBxnLc04Vd4d-w/view?pli=1


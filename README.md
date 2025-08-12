# IoT Smart Agriculture & Automatic Irrigation System (ESP8266)

## Overview
This project implements a **Smart Agriculture & Automatic Irrigation System** using the NodeMCU ESP8266 microcontroller and IoT technologies.  
It automates irrigation based on soil moisture levels and environmental conditions while allowing remote monitoring via the **ThingSpeak** cloud platform.


<p align="center">
   <img width="894" height="507" alt="image" src="https://github.com/user-attachments/assets/99cea169-e439-4806-a8a6-f82800dd5adc" />
</p>


**Key Features:**
- Automatic water pump control based on soil moisture.
- Air temperature and humidity monitoring.
- Remote monitoring via IoT dashboard (ThingSpeak).
- Low-cost and easy to assemble.
- Long-life corrosion-resistant soil moisture sensor.

---

## Components Used
| S.No | Component                              | Quantity |
|------|----------------------------------------|----------|
| 1    | NodeMCU ESP8266 Board                  | 1        |
| 2    | Capacitive Soil Moisture Sensor        | 1        |
| 3    | 0.96" I2C OLED Display                 | 1        |
| 4    | DHT11 Humidity & Temperature Sensor    | 1        |
| 5    | 1-Channel 5V Relay Module              | 1        |
| 6    | 5V DC Motor Pump                       | 1        |
| 7    | Connecting Wires                       | 10       |
| 8    | Breadboard                             | 1        |

---

## Sensors & Modules Details

### 1. Capacitive Soil Moisture Sensor
- Measures moisture levels via capacitive sensing (1.2V–3.0V output).
- Corrosion-resistant material for long life.
- Operating Voltage: 3.3–5.5V.

### 2. DHT11 Humidity & Temperature Sensor
- Measures air temperature & humidity.
- Digital signal output.
- Sampling rate: 1 reading every 2 seconds.

### 3. DC 3–6V Mini Submersible Pump
- Flow rate: 80–120 L/H.
- Low current consumption (130–220mA).
- Operates on 2.5–6V.

---

## Circuit Connection
- **Soil Moisture Sensor** → A0 (NodeMCU)
- **DHT11 Sensor** → D4
- **Relay Module** → D5
- **OLED Display** → I2C (SDA, SCL)
- **Water Pump** → Relay Output
- **Power** → 3.3V for sensors, 5V for motor/relay


<p align="center">
   <img width="882" height="407" alt="image" src="https://github.com/user-attachments/assets/75c70033-32ff-467d-9d76-a2151df775dc" />
</p>

---

## Working Principle
1. Soil moisture is continuously monitored.
2. If moisture falls below a threshold:
   - The pump is turned ON automatically via relay.
3. Once soil is sufficiently wet:
   - The pump is turned OFF.
4. Environmental data (soil moisture, temperature, humidity) is sent to **ThingSpeak** for remote monitoring.

<p align="center">
<img width="859" height="391" alt="image" src="https://github.com/user-attachments/assets/863b7f29-74cb-4013-8452-61c8d7cd8234" />
</p>
---

## IoT Integration (ThingSpeak Setup)
1. Create an account at [ThingSpeak](https://thingspeak.com/).
2. Create a new channel and note the **Write API Key**.
3. Replace the API key, Wi-Fi SSID, and password in the Arduino code.
4. Customize the dashboard under "Private View" for real-time monitoring.


<p align="center">
   ![Uploading image.png…]()

</p>
---

## PCB Option
You can design and order a PCB for a neater setup:
- Designed using **EasyEDA**.
- Gerber files are provided in the `PCB/` folder.
- Order from [ALLPCB](https://www.allpcb.com/) or similar services.

---

## Source Code
- The Arduino code is available in the `Code/` folder.
- Required Libraries:
  - [Adafruit GFX Library](https://github.com/adafruit/Adafruit-GFX-Library)
  - [SSD1306 OLED Library](https://github.com/adafruit/Adafruit_SSD1306)

**Important:**  
Calibrate the soil moisture sensor by determining `AirValue` and `WaterValue` before deploying.

---

## How to Run
1. Connect all components as per the circuit diagram.
2. Install Arduino IDE and required libraries.
3. Open the provided `.ino` file.
4. Update Wi-Fi credentials and ThingSpeak API key.
5. Upload the code to the NodeMCU.
6. Power the system and monitor data on ThingSpeak.

---

## Applications
- Precision agriculture.
- Home gardening automation.
- Greenhouse monitoring.
- Research and educational projects.

---


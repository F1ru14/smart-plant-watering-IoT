# Smart Plant Watering IoT System 🌱💧

A smart IoT-based plant watering system integrated with **Arduino IoT Cloud**. This project allows you to monitor soil moisture levels in real-time, view status updates (e.g., "Kering" or "Basah"), and control a water pump remotely.

It features a dedicated **Auto Mode** that automatically manages watering based on sensor data, ensuring your plants are never thirsty!

## 🌟 Features
- **Real-time Monitoring:** View moisture percentage (`kelembapan`) and textual status (e.g., "Kering").
- **Smart Automation:** Toggle **Auto Mode** remotely. When enabled, the system automatically waters the plant when the soil is dry.
- **Remote Control:** Manually control the water pump using the "Switch Pompa" widget.
- **Visual Feedback:** Dashboard indicators for pump status and historical moisture data.

## 🛠️ Hardware Requirements
- **Microcontroller:** Arduino Nano 33 IoT, ESP32, or ESP8266 (NodeMCU/Wemos).
- **Soil Moisture Sensor:** Capacitive (recommended) or Resistive sensor.
- **Water Pump:** 5V Submersible mini pump.
- **Relay Module:** To control the pump.
- **Power Supply:** USB cable or battery pack.
- **Tubing & Jumper Wires.**

## 💻 Software & Setup

### 1. Arduino IoT Cloud Variables
To run this project, create a **Thing** in the [Arduino IoT Cloud](https://create.arduino.cc/iot/) and add the following variables exactly as written:

| Variable Name | Type | Permission | Description |
| :--- | :--- | :--- | :--- |
| **`autoMode`** | `boolean` | Read & Write | Toggles automatic watering logic (ON/OFF). |
| **`kelembapan`** | `int` | Read Only | Soil moisture percentage (0-100%). |
| **`pompa`** | `boolean` | Read & Write | Controls the water pump manually. |
| **`rawvalue`** | `int` | Read Only | Raw analog reading from the sensor (for calibration). |
| **`soilstatus`** | `String` | Read Only | Text status indicating soil condition (e.g., "Kering"). |

### 2. Dashboard Configuration
Once your device is online, set up your Dashboard with the following widgets to match the screenshots:

1.  **Gauge:** Link to `kelembapan` (Name: "Kelembapan (%)", Min: 0, Max: 100).
2.  **Value Display:** Link to `soilstatus` (Name: "Status Tanah").
3.  **Switch:** Link to `autoMode` (Name: "Auto Mode").
4.  **Switch:** Link to `pompa` (Name: "Switch Pompa").
5.  **LED:** Link to `pompa` (Name: "Status Pompa") - *Visual indicator of pump activity.*
6.  **Chart:** Link to `kelembapan` - *To view moisture history over time.*

### 3. Installation
1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/F1ru14/smart-plant-watering-IoT.git](https://github.com/F1ru14/smart-plant-watering-IoT.git)
    ```
2.  **Open the Project:**
    -   Open `Var_Smart_Plant_Watering_nov10a.ino` in the Arduino IDE.
    -   Ensure `thingProperties.h` is in the same folder.
3.  **Configure Network:**
    -   Open `thingProperties.h`.
    -   Enter your Wi-Fi **SSID** and **PASSWORD**.
4.  **Upload:**
    -   Connect your board.
    -   Select the correct Board and Port in Arduino IDE.
    -   Upload the code.

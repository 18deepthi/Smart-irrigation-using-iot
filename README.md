🌱 Smart Irrigation System using IoT (Arduino + DHT11 + Soil Moisture + Relay)

This project is a **Smart Irrigation System** built using Arduino.  
It monitors **soil moisture**, **temperature**, and **humidity**, and automatically controls a **water pump (motor)** using a relay. The system displays live readings on a 16x2 LCD.

Although this version runs locally on Arduino, it can be extended to IoT by connecting an ESP8266/NodeMCU or any Wi-Fi module to send data to the cloud or a mobile app.

🎯 Features

- Reads **soil moisture level** using an analog soil moisture sensor.
- Reads **temperature and humidity** using a **DHT11** sensor.
- Displays:
  - Temperature (°C)
  - Humidity (%)
  - Soil moisture (%)
  - Motor status (ON/OFF)
- **Automatically turns ON the motor** when soil is dry (moisture < 30%).
- **Automatically turns OFF the motor** when soil moisture is sufficient.
- Easy to extend to IoT (Blynk, MQTT, Thingspeak, etc.).

🧰 Hardware Required

- Arduino Uno / Nano / Mega
- DHT11 Temperature & Humidity Sensor
- Soil Moisture Sensor (Analog)
- 16x2 LCD Display
- Relay Module (to control motor/pump)
- Water pump / DC motor (for demonstration)
- Jumper wires
- Breadboard
- Power supply

🔌 Pin Connections

### LCD (16x2) – using `LiquidCrystal` library

RS  -> 7  
E   -> 8  
D4  -> 9  
D5  -> 10  
D6  -> 11  
D7  -> 12

Sensors & Relay
DHT11 Sensor:
  Signal -> D5 (digital pin 5)

Soil Moisture Sensor:
  Analog output -> A0

Relay Module:
  IN  -> D6 (digital pin 6)
  VCC -> 5V
  GND -> GND

> ⚠ Be careful with relay and motor power connections if you are using AC loads. For safety, use only low-voltage DC pump in demos.
🧪 Working Logic

1. DHT11 reads:

   * DHT.temperature
   * DHT.humidity

2. Soil moisture is read from A0:
   cpp
   output_value = analogRead(sensor_pin);
   output_value = map(output_value, 550, 10, 0, 100);

   * The value is mapped to a **percentage** (0–100%).
   * You may adjust `550` and `10` based on your sensor calibration.

4. **Motor Control Logic**:
   if (output_value < 30) {
       digitalWrite(relayPin, LOW);   // Motor ON
       lcd.print("Motor ON");
   } else {
       digitalWrite(relayPin, HIGH);  // Motor OFF
       lcd.print("Motor OFF");
   }
5. LCD shows:

   * Line 1 → Temp: xx C
   * Line 2 → Humidity: xx%
   * Then it scrolls and shows Moisture: xx% and motor status.

📦 Required Libraries

Make sure you have these libraries installed in Arduino IDE:

* LiquidCrystal (built-in)
* dht.h – DHT11 sensor library
  (or the common DHT sensor library by Adafruit if you adapt code)


🌐 IoT Extension Ideas (Future Scope)

To truly make this an **IoT Smart Irrigation** project, you can extend this by:

* Adding **ESP8266 / NodeMCU** for Wi-Fi connectivity.
* Sending sensor data to:

  * Blynk App
  * Thingspeak
  * Firebase / MQTT
* Remote control of motor from mobile app.
* Data logging and analytics (e.g., daily moisture graph).

 📌 Notes / Customization

* Adjust moisture threshold (30) based on your plant/soil requirements.
* Calibrate the map() function using your own dry/wet readings.
* You can remove lcd.autoscroll() if you want static display.

- Or write a **short description** for your resume / LinkedIn.
```

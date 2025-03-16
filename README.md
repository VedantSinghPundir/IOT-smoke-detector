# 🚨 Smoke Detector using Arduino

This project implements a **Smoke Detector** using an **Arduino Uno**, a **MQ2 Smoke Sensor**, a **Buzzer**, and LEDs to alert users when smoke is detected. This system is designed to provide an early warning in case of fire or hazardous gas leaks, helping to ensure safety at home or in commercial buildings.

---

## 📌 **Project Overview**
This project is built using an Arduino Uno microcontroller and a MQ2 smoke sensor to detect smoke levels in the environment. When the smoke level exceeds a defined threshold:
- A **red LED** lights up to indicate danger.
- A **buzzer** sounds an alarm.
- A **yellow LED** signals safe conditions when the smoke level is below the threshold.

---

## 🛠️ **Components Used**
| Component | Description |
|-----------|-------------|
| **Arduino Uno** | Microcontroller used to control the circuit |
| **MQ2 Smoke Sensor** | Detects smoke, LPG, and other combustible gases |
| **Buzzer** | Produces an audible alarm when smoke is detected |
| **Red LED** | Lights up when smoke is detected |
| **Yellow LED** | Indicates normal conditions |

---

## 🧠 **How It Works**
1. The MQ2 sensor reads the smoke level.
2. If the sensor value exceeds the set threshold:
   - The red LED lights up.
   - The buzzer starts sounding.
   - The yellow LED turns off.
3. If the sensor value is below the threshold:
   - The red LED turns off.
   - The yellow LED turns on.
   - The buzzer remains off.

---

## 📂 **Code Explanation**
```cpp
#define smokesensor A1
#define buzzer 11
#define redled 3
#define yelloled 7
#define HIGH 200

void setup() {
  pinMode(smokesensor, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(redled, OUTPUT);
  pinMode(yelloled, OUTPUT);
}

void loop() {
  int sensorvalue = analogRead(A1);

  if(sensorvalue < HIGH) {
    digitalWrite(redled, HIGH);
    delay(1000);
    digitalWrite(yelloled, LOW);
    noTone(buzzer);
  } else {
    digitalWrite(redled, LOW);
    digitalWrite(yelloled, HIGH);
    delay(2000);
    tone(buzzer, 450);
    delay(1000);
  }
}
```

---

## 🚀 **Features**
✅ Early smoke detection and alert  
✅ Real-time monitoring using Arduino  
✅ Low cost and easy to implement  
✅ Audible and visual alerts for quick response  

---

## 📋 **Future Improvements**
🔹 Add an IoT feature to send alerts to a smartphone  
🔹 Integrate with other smart home devices (e.g., lights, thermostat)  
🔹 Enhance accuracy using machine learning to reduce false alarms  
🔹 Add support for detecting other gases like carbon monoxide  

---

## 🏆 **Why This Project is Important**
- Provides an early warning system to prevent fire hazards.
- Low-cost solution for improving home and office safety.
- Can be expanded to include IoT features for remote monitoring and control.

---

## 🏷️ **Author**
- **Vedant Singh Pundir**  
- **Graphic Era (Deemed to be University)**  

---

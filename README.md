<img width="1280" height="640" alt="image" src="https://github.com/user-attachments/assets/92dde91a-416a-4d36-8ff2-5c357466b0f1" />



# [LaundrySense] 🎯


## Basic Details
### Team Name: [LaundrySense]


### Team Members
- Member 1: [Adithya k] - [Jyothi engineering college cheruthuruthy]
- Member 2: [Megha k] - [Jyothi engineering college cheruthuruthy]

### Project Description

**LaundrySense** is a fun and intentionally unnecessary smart system designed to tell users when their laundry box is getting full. An **ultrasonic sensor** detects the level of clothes inside the box and sends the readings to an **Arduino UNO**. When the clothes reach a predefined level, an **LED lights up and a buzzer sounds**, dramatically informing the user that the laundry has reached its "critical level."

<img width="1280" height="853" alt="WhatsApp Image 2026-09-12 at 1 13 38 AM" src="https://github.com/user-attachments/assets/ddf14a48-d9ce-4afb-a847-5befc5c16d55" />


### The Problem (that doesn't exist)
[“People are unable to determine when their laundry box is full without physically looking at it, so we decided to solve this extremely serious crisis using an ultrasonic sensor, an Arduino and a buzzer.” 🧺🚨]

### The Solution (that nobody asked for)

> **“We eliminated the need for humans to perform the ancient ritual of looking inside the laundry box. An ultrasonic sensor measures the clothes level, an Arduino UNO takes charge, and when the box is full, an LED flashes and a buzzer screams for attention. Because apparently, even laundry needs a personal alarm system.”**
]

## Technical Details
### 🔧 Main Components

* **Arduino UNO**

  * Microcontroller board, 5V
  * ATmega328P
* **HC-SR04 Ultrasonic Sensor**

  * Operating voltage: 5V
  * Range: approximately 2–400 cm
  * Used to detect the level of clothes
* **LED**

  * 5 mm LED
  * Used as the visual alert
* **Passive Buzzer**

  * 5V
  * Produces the warning sound
* **220 Ω Resistor**

  * Used to limit current through the LED
* **Breadboard & Jumper Wires**

  * For circuit connections
* **Small Laundry Box** 

  * The highly sophisticated object requiring all this technology 💀

### 🛠️ Tools Required

* Arduino IDE
* USB cable
* Computer/laptop
* Breadboard
* Jumper wires
* Basic electronic components
For **LaundrySense**, Jellyfish 🧺🤖, you can list these technologies:

### 💻 Technologies Used

* **Embedded Systems**: Arduino UNO is used as the main controller.
* **Ultrasonic Sensing**: HC-SR04 measures the distance to the clothes.
* **Sensor-Based Automation**: The Arduino automatically detects when the laundry reaches the set threshold.
* **Arduino Programming**: C/C++ is used to program the Arduino.
* **Alert/Indication System**: LED and buzzer provide visual and audio alerts.
* **Basic Electronics**: Breadboard, resistors, and jumper wires are used to build the circuit.

  **ARDUINO CODE**
  const int trigPin = 9;
const int echoPin = 10;
const int ledPin = 7;
const int buzzerPin = 8;

const float threshold = 5.0;  // Change this after testing

void setup() {
  pinMode(trigPin, OUTPUT);
  pinMode(echoPin, INPUT);
  pinMode(ledPin, OUTPUT);
  pinMode(buzzerPin, OUTPUT);

  Serial.begin(9600);
}

void loop() {

  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);

  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);

  digitalWrite(trigPin, LOW);

  // Receive echo
  long duration = pulseIn(echoPin, HIGH);

  // Calculate distance
  float distance = duration * 0.0343 / 2;

  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");

  // Check laundry level
  if (distance <= threshold) {

   digitalWrite(ledPin, HIGH);
    tone(buzzerPin, 1000);

   Serial.println("LAUNDRY FULL!");

  } else {

   digitalWrite(ledPin, LOW);
    noTone(buzzerPin);

  }

  delay(500);
}
* 
  ****ALGORITHMIC FLOWCHART***
            <img width="853" height="1280" alt="WhatsApp Image 2026-09-12 at 5 01 22 AM" src="https://github.com/user-attachments/assets/b492bd31-0358-4053-98d1-3ef883e2724b" />

### Project Documentation

For Hardware:

# Schematic & Circuit
![Circuit Diagram]<img width="720" height="1280" alt="WhatsApp Image 2026-09-12 at 1 33 19 AM (1)" src="https://github.com/user-attachments/assets/138cbb65-1c1f-46cc-985b-1cdff7b6f872" />
[Circuit Diagram](https://github.com/user-attachments/assets/543fce77-afec-4a84-8ad5-f7b2660b982a)
(Ad your circuit diagram here)<img width="720" height="1280" alt="WhatsApp Image 2026-09-12 at 3 01 39 AM" src="https://github.com/user-attachments/assets/0b0ffc65-c384-4e51-b316-b167d4a47cb9" />

*Add caption explaining connections*
## Circuit Connection Explanation

The LaundrySense circuit is built using an Arduino UNO, an HC-SR04 ultrasonic sensor, an LED, a passive buzzer, and a 220Ω resistor.

### Ultrasonic Sensor (HC-SR04)
- VCC → Arduino 5V
- GND → Arduino GND
- TRIG → Arduino Digital Pin 9
- ECHO → Arduino Digital Pin 10

The HC-SR04 measures the distance between the sensor and the clothes inside the laundry box. The Arduino calculates this distance from the time taken by the ultrasonic pulse to return.

### LED
- LED Anode (+) → 220Ω resistor → Arduino Digital Pin 7
- LED Cathode (-) → Arduino GND

The LED acts as a visual warning indicator. It turns ON when the detected laundry level reaches the predefined threshold.

### Buzzer
- Buzzer Positive (+) → Arduino Digital Pin 8
- Buzzer Negative (-) → Arduino GND

The buzzer provides an audible warning when the laundry box reaches the threshold.

### Power Supply
The Arduino UNO is powered through a USB connection. The 5V and GND pins of the Arduino provide power and a common ground connection for the sensor and other components.

### Working
The HC-SR04 continuously measures the distance between the sensor and the clothes. When the measured distance becomes less than or equal to the predefined threshold, the Arduino considers the laundry box sufficiently full. It then turns ON the LED and activates the buzzer. When the distance is greater than the threshold, both the LED and buzzer remain OFF.


# Build Photos
![Component<img width="720" height="1280" alt="WhatsApp Image 2026-09-12 at 1 33 19 AM (1)" src="https://github.com/user-attachments/assets/ad6b1c3b-20b2-4712-95a5-f57aae1afd0b" />
s](Add photo of your components here)
*List out all components shown*
| Component                     | Function                                                             |
| ----------------------------- | -------------------------------------------------------------------- |
| **Arduino UNO**               | Controls the entire system and processes sensor readings.            |
| **HC-SR04 Ultrasonic Sensor** | Measures the distance between the sensor and the clothes.            |
| **LED**                       | Provides a visual indication when the laundry reaches the threshold. |
| **Passive Buzzer**            | Produces an alert sound when the laundry reaches the threshold.      |
| **1 kΩ Resistor**             | Limits current and protects the LED from excessive current.          |
| **Breadboard**                | Allows the components to be connected without soldering.             |
| **Jumper Wires**              | Provide electrical connections between the components.               |
| **Laundry Box**               | Holds the clothes whose level is being monitored.                    |


![Building Process]<img width="960" height="1280" alt="WhatsApp Image 2026-09-12 at 2 35 12 AM" src="https://github.com/user-attachments/assets/02bdec46-59cc-40bd-87b7-4af4f4cedc05" />
](Add photos of build process here)
*Explain the build steps*
## Build Steps

1. **Prepare the components**  
   Collect the Arduino UNO, HC-SR04 ultrasonic sensor, LED, passive buzzer, 1 kΩ resistor, breadboard and jumper wires.

2. **Connect the ultrasonic sensor**  
   Connect VCC to the Arduino 5V pin, GND to GND, TRIG to digital pin 9 and ECHO to digital pin 10.

3. **Connect the LED**  
   Connect the LED through the 1 kΩ resistor to digital pin 7. Connect the other terminal of the LED to GND.

4. **Connect the buzzer**  
   Connect the positive terminal of the passive buzzer to digital pin 8 and the negative terminal to GND.

5. **Place the sensor**  
   Fix the HC-SR04 at the top of the laundry box so that it faces downward towards the clothes.

6. **Upload the program**  
   Connect the Arduino UNO to a computer using a USB cable and upload the LaundrySense program using the Arduino IDE.

7. **Set the threshold**  
   Test the ultrasonic sensor and determine the distance at which the laundry should be considered "full." Set this value as the threshold in the program.

8. **Test the system**  
   Place clothes inside the box and observe the sensor readings. When the clothes reach the predefined threshold, the LED turns ON and the buzzer activates.

9. **Complete the prototype**  
   Secure the components and wires inside/on the laundry box to create the final LaundrySense prototype.

![Final Build]<img width="720" height="1280" alt="WhatsApp Image 2026-09-12 at 1 33 19 AM" src="https://github.com/user-attachments/assets/6aa94606-9039-4b2c-a263-d1ee4877f15c" />)
*Explain the final build*
## Final Build

The final LaundrySense prototype consists of a small laundry box fitted with an HC-SR04 ultrasonic sensor at the top. The sensor continuously measures the distance between itself and the clothes inside the box.

The HC-SR04 is connected to an Arduino UNO, which processes the distance readings. An LED and passive buzzer are connected to the Arduino to provide visual and audible alerts.

When the clothes reach the predefined distance threshold, the Arduino detects that the box is sufficiently full. The LED turns ON and the buzzer starts sounding, notifying the user that it is time to deal with the laundry.

The final prototype demonstrates a simple sensor-based automation system built using basic electronic components.

> **Final result:** A laundry box that has officially become smart enough to complain about being full. 🧺🚨

### Project Demo
# Video
[Add

<video src="https://github.com/user-attachments/assets/cf1ab2ac-0b08-464b-84d9-556c0097e6f5" controls width="700"></video>

 your demo video link here]
*Explain what the video demonstrates*
it demonstrate that ,when the cloth reach the predefined distance threshold ,the Arduino detects that the box is sufficiently full.the led turns on and the buzzer starts sounding. 

# Additional Demos
[Add any extra demo materials/links]

## Team Contributions

![Team Contributions](https://github.com/user-attachments/assets/03c2de1f-cd1f-466d-9867-618e9d2a86d6)



![Team Contributions](https://github.com/user-attachments/assets/670706e4-2af6-4eea-988f-d08b12ecf8bd)



![Team Contributions](https://github.com/user-attachments/assets/510b065b-c0ec-47ce-a875-49e53f6371b4)


![Team Contributions](https://github.com/user-attachments/assets/08866be4-182a-4051-b2e8-92af6567c9bb)


---
Made with ❤️ at TinkerHub Useless Projects 

![Static Badge](https://img.shields.io/badge/TinkerHub-24?color=%23000000&link=https%3A%2F%2Fwww.tinkerhub.org%2F)
![Static Badge](https://img.shields.io/badge/UselessProjects--26-26?link=https%3A%2F%2Ftinkerhub.org%2Fevents%2F1M8ORET9A1%2Fuseless-projects-3.0)




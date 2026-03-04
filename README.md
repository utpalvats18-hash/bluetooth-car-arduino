# 🚗 Bluetooth Controlled Car using Arduino

## 📌 Project Overview

This project is a **Bluetooth-controlled car** built using **Arduino Uno R3**.
The car can be controlled wirelessly through a mobile application using Bluetooth communication.

## 🛠 Components Used

* Arduino Uno R3
* HC-05 Bluetooth Module
* L298N Motor Driver
* DC Motors
* Car Chassis
* Jumper Wires
* 9V / 12V Battery

## ⚙️ Working Principle

* The mobile app sends commands via Bluetooth.
* HC-05 receives the signals.
* Arduino processes the commands.
* Motor driver controls the motors based on input.

## 📱 Control Commands

| Command | Function      |
| ------- | ------------- |
| F       | Move Forward  |
| B       | Move Backward |
| L       | Turn Left     |
| R       | Turn Right    |
| S       | Stop          |

## 💻 Arduino Code

```cpp
char command;

void setup() {
  Serial.begin(9600);
  pinMode(8, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(11, OUTPUT);
}

void loop() {
  if (Serial.available()) {
    command = Serial.read();
    
    if (command == 'F') {
      digitalWrite(8, HIGH);
      digitalWrite(9, LOW);
      digitalWrite(10, HIGH);
      digitalWrite(11, LOW);
    }
    else if (command == 'B') {
      digitalWrite(8, LOW);
      digitalWrite(9, HIGH);
      digitalWrite(10, LOW);
      digitalWrite(11, HIGH);
    }
    else if (command == 'L') {
      digitalWrite(8, LOW);
      digitalWrite(9, HIGH);
      digitalWrite(10, HIGH);
      digitalWrite(11, LOW);
    }
    else if (command == 'R') {
      digitalWrite(8, HIGH);
      digitalWrite(9, LOW);
      digitalWrite(10, LOW);
      digitalWrite(11, HIGH);
    }
    else if (command == 'S') {
      digitalWrite(8, LOW);
      digitalWrite(9, LOW);
      digitalWrite(10, LOW);
      digitalWrite(11, LOW);
    }
  }
}
```



* Serial Communication
* Bluetooth Module Interfacing
* Motor Driver Control
* Embedded System Programming

---

🔹 Developed as part of Diploma Project in Electronics & Communication Engineering.

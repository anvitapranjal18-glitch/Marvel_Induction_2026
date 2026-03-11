## **Task 9: Radar System Simulation via Tinkercad**

### **Description**

The core objective of this task was to design, wire, and simulate an **Ultrasonic Radar System** using the **Tinkercad** platform. This project involved interfacing an **HC-SR04 Ultrasonic Distance Sensor** with an **Arduino Uno** and a **Micro Servo Motor**. By mounting the sensor on the rotating servo, I implemented a sweep-scanning mechanism that mimics real-world radar technology. The task emphasizes the conversion of "Time-of-Flight" sound data into spatial distance measurements and synchronized hardware control.

### **Detailed Process**

- **Simulation Environment Setup:** I initiated the project by creating a virtual circuit in Tinkercad. This allowed for risk-free prototyping of the Arduino-based hardware, ensuring all power ($5V$) and ground ($GND$) rails were correctly distributed to multiple peripherals.
- **Ultrasonic Distance Logic:** I implemented the physics of sound to calculate distance. The sensor sends a 10µs pulse via the **Trig pin**, which bounces off an obstacle and returns to the **Echo pin**.
  - **The Formula:** $Distance = (Time \times 0.034) / 2$
  - _The division by 2 accounts for the sound traveling to the object and back._
- **Servo Integration & Sweep Scanning:** To cover a 180-degree field of view, I integrated a Servo motor using the `<Servo.h>` library. I coded a `for` loop to increment the servo angle from $0^{\circ}$ to $180^{\circ}$ (and back), triggering a distance reading at every $1^{\circ}$ step to create a continuous radar sweep.
- **Data Visualization via Serial Monitor:** I utilized the **Serial Monitor** to output real-time telemetry. Each line of data displayed the current angle of the servo and the corresponding distance of any detected obstacle, providing a numerical map of the surrounding environment.
  ```cpp
  // Sample Logic for Radar Output
  Serial.print(angle);
  Serial.print(",");
  Serial.println(distance);
  ```
- **Hardware Interfacing:** \* **Servo Control:** Connected to PWM Pin 9 for precise angle modulation.
  - **Ultrasonic Sensor:** Trig connected to Pin 10, Echo to Pin 11 for high-speed pulse timing.

### **Radar Logic Flow**

| Component          | Function             | Technical Role                                          |
| :----------------- | :------------------- | :------------------------------------------------------ |
| **Arduino Uno**    | Microcontroller      | Processes pulse timing and executes the rotation logic. |
| **HC-SR04**        | Acoustic Transceiver | Emits and receives 40kHz ultrasonic bursts.             |
| **SG90 Servo**     | Actuator             | Provides the mechanical 180° rotational sweep.          |
| **Serial Monitor** | Debugger/Display     | Visualizes distance data in centimeters.                |

### **Technical Skills Gained**

- **Time-of-Flight (ToF) Calculations:** Mastering the conversion of microsecond pulse durations into physical units of measurement (cm/inches).
- **Pulse Width Modulation (PWM):** Understanding how to control motor position by sending timed electrical pulses.
- **Circuit Prototyping:** Learning to use Tinkercad for schematic design and virtual troubleshooting before physical assembly.
- **Embedded C++ Programming:** Developing non-blocking logic to handle simultaneous motor movement and sensor polling.

---

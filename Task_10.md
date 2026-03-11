## **Task 10: Speed Control of DC Motor using L298N & Arduino**

### **Description**

The core objective of this task was to implement precise speed control for a **5V BO (Battery Operated) Motor** using an **Arduino Uno** and an **L298N H-Bridge Motor Driver**. The project involved understanding the mechanics of **Pulse Width Modulation (PWM)** to vary the effective voltage supplied to the motor without reducing the source voltage. This task bridges the gap between digital logic (Arduino) and high-current mechanical actuators (DC Motors), focusing on both virtual simulation and physical hardware implementation.

### **Detailed Process**

- **H-Bridge Architecture (L298N):** I utilized the L298N driver to decouple the Arduino's delicate logic circuitry from the high-current demands of the DC motor. The dual H-Bridge setup allowed for bidirectional control by toggling the `IN1` and `IN2` pins, while the `ENA` (Enable A) pin was used for speed regulation.
- **PWM Speed Modulation:** Instead of a steady DC signal, I programmed the Arduino to output a **PWM signal** via an analog-capable pin (e.g., Pin 9). By varying the **Duty Cycle** (the ratio of "on" time to "off" time), I controlled the RPM of the motor:
  - **0% Duty Cycle:** Motor is stationary.
  - **50% Duty Cycle:** Motor runs at approximately half speed.
  - **100% Duty Cycle:** Motor runs at maximum rated RPM.
  ```cpp
  // Sample Code for Speed Graduation
  analogWrite(ENA, 150); // Sets speed (0-255)
  digitalWrite(IN1, HIGH); // Direction A
  digitalWrite(IN2, LOW);
  ```
- **Virtual Prototyping (Tinkercad):** Before hardware assembly, I simulated the circuit in Tinkercad. This step was vital to verify the common ground between the external battery source and the Arduino, preventing potential back-EMF damage to the microcontroller.
- **Hardware Assembly & Testing:** I transitioned the design to physical hardware using a breadboard, jumper wires, and a 9V battery (regulated through the L298N). I recorded the motor's response to different code parameters, documenting the transition from low-torque starts to full-speed operation.

### **Control Logic Table**

| Pin (Arduino) | L298N Pin | Function          | Logic Type            |
| :------------ | :-------- | :---------------- | :-------------------- |
| **D9 (PWM)**  | ENA       | Speed Control     | Analog Output (0-255) |
| **D8**        | IN1       | Direction Input 1 | Digital (HIGH/LOW)    |
| **D7**        | IN2       | Direction Input 2 | Digital (LOW/HIGH)    |

### **Technical Skills Gained**

- **PWM Logic:** Mastered the concept of Duty Cycles to simulate variable analog voltage using digital pulses.
- **Power Isolation:** Understanding why motor drivers are necessary to protect microcontrollers from inductive loads and high current spikes.
- **H-Bridge Operation:** Learning how to manipulate current flow direction to achieve clockwise and counter-clockwise rotation.
- **Hardware Debugging:** Troubleshooting common physical issues such as loose connections, insufficient torque, and common-grounding errors.

---

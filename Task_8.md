# Task 8: Speed Control of DC Motor using L298N & Arduino

---

### 1. Objective
To interface a DC BO (Battery Operated) motor with an Arduino Uno via an L298N Dual H-Bridge driver and implement variable speed control using Pulse Width Modulation (PWM).

### 2. Hardware Components
* **Controller:** Arduino Uno (The "Brain")
* **Driver:** L298N H-Bridge (The "Muscle")
* **Actuator:** 5V-9V Yellow BO Motor
* **Power Source:** External DC Power Supply (Set to 12.0V)

---

### 3. Connection Mapping
To ensure the system works correctly, a **Common Ground** was established between the Power Supply, L298N, and Arduino.

| Component | Pin Label | Connected To | Function |
| :--- | :--- | :--- | :--- |
| **L298N** | 12V | Power Supply (+) | Main Power Input |
| **L298N** | GND | Power Supply (-) & Arduino GND | Common Reference |
| **L298N** | ENA | Arduino Pin 9 (PWM) | Speed Control (Throttle) |
| **L298N** | IN1 | Arduino Pin 8 | Direction Control (A) |
| **L298N** | IN2 | Arduino Pin 7 | Direction Control (B) |
| **Motor** | Terminal 1 & 2 | L298N OUT1 & OUT2 | Power Output to Motor |

---

### 4. Lab Setup Visualization
Below is the hardware implementation as captured during the lab session:

![Hardware Connections and Power Supply Setup](./lab_setup_1.jpg)
*Figure 1: Overall circuit connection with the 12V DC Power Supply.*



---

### 5. Technical Logic
* **Speed Control:** Accomplished via `analogWrite(9, value)`. The Arduino uses **PWM** to flicker the power on and off at high frequencies, simulating a variable analog voltage.
* **Direction Control:** Accomplished via `digitalWrite()`. 
    * **Forward:** IN1=HIGH, IN2=LOW.
    * **Backward:** IN1=LOW, IN2=HIGH.
* **H-Bridge Function:** The L298N uses internal switches to reverse the polarity of the voltage, allowing the motor to spin in both directions.

### 6. Observations & Results
The motor's speed was successfully varied from a minimum starting threshold (PWM ~70) to maximum velocity (PWM 255). The 12V power supply provided sufficient torque, and the L298N efficiently handled the current without excessive heating.

---
*Submitted by: Anvita Pranjal | UVCE ECE 2nd Sem*

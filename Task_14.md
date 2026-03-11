## **Task 14: Burglar Alarm System via K-Map & Logic Gates**

### **Description**

The core objective of this task was to design a functional **Burglar Alarm System** by applying Boolean algebra and **Karnaugh Map (K-Map)** optimization. The system logic was based on two inputs: a **Door Sensor** (Open/Closed) and a **Key Switch** (Pressed/Not Pressed). By deriving the minimal logical expression for the alarm condition, I implemented the circuit using standard **TTL logic gates** to trigger a buzzer or LED only when specific security breaches occurred. This task emphasizes the process of converting real-world conditions into a digital truth table and an optimized hardware gate layout.

### **Detailed Process**

- **Logic Mapping (Truth Table):** I defined two binary inputs: $D$ (Door: 0=Closed, 1=Open) and $K$ (Key: 0=Not Pressed, 1=Pressed). The Alarm ($A$) should only trigger if the door is opened _without_ the key being pressed.
  - **Case 1:** Door Closed (0), Key Not Pressed (0) $\rightarrow$ Alarm = 0
  - **Case 2:** Door Closed (0), Key Pressed (1) $\rightarrow$ Alarm = 0
  - **Case 3:** Door Open (1), Key Not Pressed (0) $\rightarrow$ **Alarm = 1**
  - **Case 4:** Door Open (1), Key Pressed (1) $\rightarrow$ Alarm = 0
- **K-Map Optimization:** I plotted the truth table values into a 2-variable K-Map. The simplified Boolean expression derived was:
  $$A = D \cdot \overline{K}$$
  _This indicates the alarm is active only when the Door is 1 AND the Key is NOT 1._
- **Circuit Implementation:** I rigged the circuit using a **NOT gate (7404)** and an **AND gate (7408)**.
  - I used push buttons with pull-down resistors to represent the sensors.
  - The Key signal was passed through the NOT gate to invert it.
  - The Door signal and the inverted Key signal were fed into the AND gate.
- **Hardware Validation:** I tested all four logic states. The buzzer successfully activated only when the "Door" button was pressed alone. If both buttons were pressed (simulating an authorized entry with a key), the alarm remained silent, confirming the logic was optimized and correct.

### **Truth Table & K-Map Representation**

| Door (D) | Key (K) | Alarm (A) |
| :------: | :-----: | :-------: |
|    0     |    0    |     0     |
|    0     |    1    |     0     |
|  **1**   |  **0**  |   **1**   |
|    1     |    1    |     0     |

### **Technical Skills Gained**

- **🧠 Boolean Logic:** Applying fundamental logic gates (AND, NOT) to solve real-world security scenarios.
- **📝 K-Map Optimization:** Learning to reduce digital expressions to their simplest form to minimize the number of physical ICs required.
- **🔌 Combinational Circuitry:** Building multi-gate systems on a breadboard with proper pull-up/pull-down resistor configurations.
- **💡 Security Systems Design:** Understanding the logic behind "Normally Open" and "Normally Closed" sensor configurations.

---

# Task 13: 555 Timer Astable Multivibrator Design

---

### 1. Objective
The goal of this task was to build a circuit that generates a continuous **Square Wave** signal automatically. Using the **NE555 Timer IC**, I targeted a **60% Duty Cycle** (where the signal is "ON" for 60% of the time and "OFF" for 40%).

---

### 2. How the Hardware Works (Main Idea)
This circuit is an **Astable Multivibrator**, meaning it "flips" between ON and OFF states by itself. It works like a self-filling and self-draining water tank:
* **The Capacitor ($10\mu F$):** Acts like the tank that stores electricity.
* **Resistors ($R_A, R_B$):** Act like valves that control how fast the tank fills and drains.
* **The Switch:** The 555 IC monitors the voltage. When the "tank" is 2/3 full, it starts draining. When it is 1/3 full, it starts filling again.



---

### 3. Circuit Implementation
I assembled the circuit on a breadboard with these key connections:
* **Auto-Triggering:** I shorted **Pin 2 (Trigger)** and **Pin 6 (Threshold)** together so the IC could watch the capacitor's voltage levels automatically.
* **The Drain:** **Pin 7 (Discharge)** was connected between the two resistors to create the path for electricity to leave the capacitor during the "OFF" cycle.
* **Output:** I connected **Pin 3** to the **Digital Storage Oscilloscope (DSO)** to see the waveform.

---

### 4. Observations & Measurements
I used the DSO to verify my mathematical design against the actual physical output.

| Parameter | Design Target | Measured Value (DSO) |
| :--- | :--- | :--- |
| **Duty Cycle** | 60% | **60.4%** |
| **Supply Voltage** | 5V | **4.98V** |
| **Waveform Type** | Square Wave | **Confirmed** |

---

### 5. Technical Skills Gained
* **RC Timing:** Understanding how Resistors and Capacitors control the speed (frequency) of a circuit.
* **DSO Proficiency:** Learning how to capture and measure high-speed signals on an oscilloscope.
* **Hardware Debugging:** Identifying that real components have "tolerances" (small errors), which required me to swap a resistor to get exactly 60%.

---

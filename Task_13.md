## **Task 13: Design and Analysis of a 555 Astable Multivibrator**

### **Description**

The core objective of this task was to design and implement an **Astable Multivibrator** using the **NE555 Timer IC** to generate a continuous square wave with a specific **60% Duty Cycle**. This involved calculating precise resistance and capacitance values based on the 555 timer's internal comparator thresholds. The project required rigging the circuit on a breadboard and utilizing a **Digital Storage Oscilloscope (DSO)** to verify the output frequency and signal integrity, bridging the gap between theoretical timing equations and real-world waveform analysis.

### **Detailed Process**

- **Theoretical Design & Component Calculation:** I targeted a 60% duty cycle ($D$). I utilized the standard timing equations for an astable 555 circuit:
  - **Charge Time ($T_{high}$):** $0.693 \times (R_A + R_B) \times C$
  - **Discharge Time ($T_{low}$):** $0.693 \times R_B \times C$
  - **Duty Cycle ($D$):** $(R_A + R_B) / (R_A + 2R_B)$
  - To achieve $D = 0.6$, I calculated the ratio of $R_A$ to $R_B$. Using a $10\mu F$ capacitor, I selected resistors that satisfied the ratio, ensuring the charging path $(R_A + R_B)$ was longer than the discharge path $(R_B)$.
- **Breadboard Rig-up:** I carefully assembled the circuit, ensuring the following critical connections:
  - **Pin 2 (Trigger) and Pin 6 (Threshold)** were shorted together to allow the capacitor to toggle between $1/3 V_{cc}$ and $2/3 V_{cc}$.
  - **Pin 7 (Discharge)** was connected between $R_A$ and $R_B$ to provide a path to ground during the "Low" cycle.
  - A $0.01\mu F$ decoupling capacitor was added to **Pin 5 (Control Voltage)** to filter out high-frequency noise.
- **DSO Observation & Verification:** I connected the DSO probes to **Pin 3 (Output)** and **GND**. I adjusted the time-base and voltage-scale knobs to capture a stable trace.
  - I utilized the DSO's **Measure Menu** to read the automated values for Duty Cycle and Frequency.
  - I observed the "exponential" charge-discharge curve on Pin 6 simultaneously to verify the switching points of the internal flip-flop.
- **Calibration:** Initial readings showed a slight deviation in duty cycle (approx 62%) due to resistor tolerances. I swapped $R_B$ with a slightly different value to bring the measured output closer to the 60% design target.

### **Component Values & Measurements**

| Parameter                     | Design Value | Measured Value (DSO)         |
| :---------------------------- | :----------- | :--------------------------- |
| **Duty Cycle (%)**            | 60%          | 60.4%                        |
| **Supply Voltage ($V_{cc}$)** | 5V           | 4.98V                        |
| **Output Peak Voltage**       | 5V           | 4.45V (Voltage Drop)         |
| **Waveform Type**             | Square Wave  | Rectangular (Slight Ringing) |

### **Technical Skills Gained**

- **⏱️ Timing Electronics:** Mastered the application of RC time constants in periodic signal generation.
- **📉 Oscilloscope Proficiency:** Learning to trigger, scale, and measure pulse-width parameters on a Digital Storage Oscilloscope.
- **⚡ Circuit Debugging:** Identifying noise issues in breadboard circuits and using decoupling capacitors for stabilization.
- **📐 Mathematical Modeling:** Translating desired hardware behavior (Duty Cycle) into specific component values using algebraic formulas.

---

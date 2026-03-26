# Task 13: 555 Timer Astable Multivibrator Design

---

### 1. The Main Gist (The "Water Tank" Idea)
The 555 Timer in **Astable Mode** acts like a self-filling and self-draining water tank. It has no "stable" state, so it constantly flips between ON and OFF.
* **The Capacitor ($10\mu F$):** This is the "tank" that stores electrical charge.
* **The Resistors ($R_A, R_B$):** These are the "valves." They control how fast the tank fills up and how fast it drains out.
* **The IC Brain:** The 555 monitors the voltage. When the tank hits **2/3 full**, it opens a drain. When it drops to **1/3 full**, it closes the drain to start refilling. This cycle creates the **Square Wave**.

---

### 2. Internal Components (The "555" Guts)
The chip is named "555" because of three internal **$5k\Omega$ resistors**. 
* **Voltage Divider:** These three resistors set the checkpoints at **$1/3 V_{CC}$** and **$2/3 V_{CC}$**.
* **Comparators:** Two "guards" inside the chip compare the capacitor's voltage to these checkpoints.
* **Flip-Flop:** This is the internal memory switch that remembers if the output should be HIGH (filling) or LOW (draining).
* **Discharge Transistor (Pin 7):** This is the actual "drain plug" that opens to let electricity out of the capacitor.



---

### 3. The Formulas (The Math)
To calculate the timing, we use the constant **0.693** (which is the natural log of 2). This represents the time the capacitor spends moving between the $1/3$ and $2/3$ marks.

* **Time HIGH ($T_{on}$):** The capacitor charges through **both** resistors.
  $$T_{on} = 0.693 \times (R_A + R_B) \times C$$
* **Time LOW ($T_{off}$):** The capacitor drains through **only** $R_B$.
  $$T_{off} = 0.693 \times R_B \times C$$
* **Total Period ($T$):** The time for one full blink (On + Off).
  $$T = T_{on} + T_{off} = 0.693 \times (R_A + 2R_B) \times C$$
* **Duty Cycle (%):** The percentage of time the signal is ON.
  $$Duty\ Cycle = \frac{R_A + R_B}{R_A + 2R_B} \times 100\%$$



---

### 4. Observations & Results
Using the formulas above, I chose $R_B \approx 2R_A$ to reach my **60% Duty Cycle** goal. I verified the results using a **Digital Storage Oscilloscope (DSO)**.

| Parameter | Design Target | Measured Value (DSO) |
| :--- | :--- | :--- |
| **Duty Cycle** | 60% | **60.4%** |
| **Supply Voltage** | 5V | **4.98V** |
| **Waveform** | Square Wave | **Confirmed** |

---

### 5. Technical Skills Gained
* **RC Timing:** Learned how resistors and capacitors work together to create specific time delays.
* **Logic Thresholds:** Understood how the $1/3$ and $2/3$ voltage levels control the state of a circuit.
* **DSO Measurement:** Mastered capturing real-time waveforms to prove the math works in the real world.

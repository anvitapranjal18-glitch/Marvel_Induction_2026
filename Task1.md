#  Task 1: 3D Printing & Thin-Film Geometry Calibration

---

### 1. 🎯 Objective
To master the **FDM (Fused Deposition Modeling)** workflow by printing a **Shark Bookmark** (`bookshark.stl`). This project serves as a critical test for the printer’s ability to handle very thin layers and maintain a perfectly flat profile without warping.

---

### 2. 📚 The Model: Shark Bookmark
* **Design:** A functional, low-profile bookmark featuring a shark silhouette. It requires a perfectly level bed because even a 0.1mm tilt would make one side of the bookmark thicker than the other.
* **Challenge:** Because the model is wide and thin, it is highly susceptible to **warping** (corners peeling up) as the plastic cools and shrinks.

---

### 3. ⚙️ Slicing Parameters (Golden Settings)
For a flat, thin object like a bookmark, these "Golden Settings" ensure the print is durable and perfectly flat.

| Parameter | Value | Reason |
| :--- | :--- | :--- |
| **Layer Height** | 0.2 mm | Standard balance; ensures the bookmark is thin but strong. |
| **Wall Line Count** | 3 | Strengthens the outer "skin" of the shark shape. |
| **Infill Density** | 100% | Since it is very thin, 100% infill makes it solid and durable. |
| **Print Speed** | 50 mm/s | Balanced speed for a smooth top-surface finish. |
| **Printing Temp** | 200°C | Optimal flow for PLA to ensure the layers bond perfectly. |
| **Build Plate Temp** | 60°C | Keeps the wide, flat base from peeling off the bed. |
| **Initial Layer Speed**| 15 mm/s | Extra slow start to guarantee the tail and fins stick perfectly. |

---

### 🛠️ 4. Technical Procedure & Hardware Mechanism

**A. The Hardware "Guts":**
The 3D printing process follows a specific mechanical path:
1.  **Extruder:** The motor and gear assembly that grips the filament and pushes it forward.
2.  **Hot End:** The heating element that melts the solid plastic into a liquid state (200°C).
3.  **Nozzle:** The 0.4mm tip that "draws" the melted plastic onto the bed.
4.  **Cooling Fan:** Instantly hardens the plastic so the next layer can sit on top.
5.  **Stepper Motors:** Move the nozzle along the **X, Y, and Z axes** based on the G-Code.



**B. Step-by-Step Workflow:**
* **📂 File Preparation:** Imported `bookshark.stl` into the Slicer. I used the **Rotate** tool to ensure it was laying completely flat on the virtual bed.
* **💾 G-Code Generation:** Processed the file to create layer-by-layer instructions and saved them to the microSD card.
* **🧼 Printer Setup:** Thoroughly cleaned the build plate with **IPA (Isopropyl Alcohol)**. For thin objects, removing finger oils is the primary way to **prevent warping**.
* **🚀 Execution:** Started the print and monitored the first layer. I ensured a "perfect squish"—where the plastic lines are flat and touching, creating a solid foundation.

---


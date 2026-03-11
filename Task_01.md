## Task 1: 3D Printing & Precision Calibration {#task-1}

### 1. Objective

To master the FDM (Fused Deposition Modeling) workflow by calibrating a 3D printer and producing a **20mm XYZ Calibration Cube** to verify dimensional accuracy.

### 2. The Model: XYZ Calibration Cube

- **Purpose:** To check if the printer's motors are moving the correct distance.
- **Dimensions:** 20mm x 20mm x 20mm.
- **Source:** Downloaded STL from Thingiverse/Printables.

### 3. Slicing Parameters (Using Ultimaker/Creality Slicer)

For this specific print, I used the following "Golden Settings" for PLA filament:

| Parameter            | Value     | Reason                                                      |
| :------------------- | :-------- | :---------------------------------------------------------- |
| **Layer Height**     | 0.2 mm    | Standard balance between speed and detail.                  |
| **Wall Line Count**  | 2 or 3    | Ensures the cube is sturdy enough to measure with calipers. |
| **Infill Density**   | 10% - 15% | Enough to support the top roof of the cube.                 |
| **Print Speed**      | 50 mm/s   | Prevents ghosting or vibrations on the letters.             |
| **Printing Temp**    | 200°C     | Ideal melting point for most PLA brands.                    |
| **Build Plate Temp** | 60°C      | Prevents "warping" (corners peeling up).                    |

### 4. Step-by-Step Workflow

1.  **File Preparation:** Imported the `XYZ_Cube.stl` into the Slicer.
2.  **G-Code Generation:** Clicked "Slice" to see the estimated print time (~30-45 mins) and saved the `.gcode` file to a microSD card.
3.  **Printer Setup:** Cleaned the glass bed with isopropyl alcohol and loaded the PLA filament.
4.  **Leveling:** Performed a manual bed leveling to ensure the nozzle was exactly the "paper-width" distance from the bed.
5.  **Execution:** Started the print and monitored the first layer closely.

---

### 5. Visual Evidence (Photos)

> **[INSERT PHOTO 1: Screenshot of the sliced cube in Cura showing the layers]**

> **[INSERT PHOTO 2: The finished 20mm cube sitting on the print bed]**

### 6. Post-Print Analysis

After the print finished, I used a digital caliper to measure the axes:

- **X-Axis:** [Measure it] mm
- **Y-Axis:** [Measure it] mm
- **Z-Axis:** [Measure it] mm
- **Observation:** (Example: "The Z-axis was perfect, but X was off by 0.1mm, indicating a belt might need tightening.")

---

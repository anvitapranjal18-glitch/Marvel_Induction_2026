# Task 1: 3D Printing & Articulated Motion Calibration

### 1. Objective
To master the FDM (Fused Deposition Modeling) workflow by printing a **Flexi-Rex** (Articulated T-Rex). This project serves as a test for the printer’s ability to handle small clearances, ensuring that moving segments do not fuse together during the extrusion process.

### 2. The Model: Flexi-Rex
* **Purpose:** To verify printer tolerances, bed adhesion for small footprints, and cooling efficiency.
* **Design:** A "Print-in-Place" model with interlocking joints that move freely immediately after printing.
* **Source:** Thingiverse / Printables.

### 3. Slicing Parameters (Ultimaker / Creality Slicer)
For an articulated print, the "Golden Settings" focus on strength and preventing joint fusion.

| Parameter | Value | Reason |
| :--- | :--- | :--- |
| **Layer Height** | 0.2 mm | Standard balance; keeps joint gaps clean. |
| **Wall Line Count** | 3 | Increases the structural integrity of the small joint links. |
| **Infill Density** | 15% | Provides enough internal support without excessive weight. |
| **Print Speed** | 45 mm/s | Reduced speed prevents vibration-induced errors on small parts. |
| **Printing Temp** | 200°C | Optimal flow for PLA to prevent stringing between joints. |
| **Build Plate Temp** | 60°C | Ensures the small segments (feet/tail) stay stuck to the bed. |
| **Initial Layer Speed**| 20 mm/s | Guarantees a strong "foundation" for the articulated parts. |

---

### 4. Step-by-Step Workflow

1. **File Preparation:** Imported `FlexiRex.stl` into the Slicer. Checked the "Slice Preview" to confirm that the gaps between the joints were visible.
2. **G-Code Generation:** Exported the `.gcode` to a microSD card.
3. **Printer Setup:** Thoroughly cleaned the bed with IPA (Isopropyl Alcohol). Since the Flexi-Rex has many small contact points, even a fingerprint can cause a part to peel off.
4. **Bed Leveling:** Verified the "Z-offset" was perfect to ensure the first layer squish was sufficient for the tiny leg segments.
5. **Execution:** Started the print and monitored the first 3 layers (the most critical phase for articulated models).

---





### 6. Post-Print Analysis

* **Articulation Check:** All segments (head, body, tail) move smoothly. The joints did not fuse.
* **Bed Adhesion:** No "warping" was observed, and even the smallest tail segments remained attached until the print was complete.
* **Tolerance:** The gaps between the joints are clean, indicating that the retraction settings and cooling fan are functioning correctly.

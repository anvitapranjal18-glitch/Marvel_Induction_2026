# Task 1: 3D Printing

---

### 1. 🎯 Objective
To master the **FDM (Fused Deposition Modeling)** workflow by printing a **Shark Bookmark** (`bookshark.stl`). This project serves as a test for the printer’s ability to handle very thin layers and maintain a perfectly flat profile without warping.

---

### 2. 📚 The Model: Shark Bookmark.
* **Design:** A functional, low-profile bookmark featuring a shark silhouette. It requires a perfectly level bed because even a 0.1mm tilt would make one side of the bookmark thicker than the other.
* **Challenge:** Because the model is wide and thin, it is highly susceptible to **warping** (corners peeling up) as the plastic cools.

---

### 3. ⚙️ Slicing Parameters (Golden Settings)
For a flat, thin object like a bookmark, these "Golden Settings" ensure the print is durable and perfectly flat.

| Parameter | Value | Reason |
| :--- | :--- | :--- |
| **Layer Height** | 0.2 mm | Standard balance; ensures the bookmark is thin but strong. |
| **Wall Line Count** | 3 | Strengthens the outer "skin" of the shark shape. |
| **Infill Density** | 100% | Since it is very thin, 100% infill makes it solid and less likely to snap. |
| **Print Speed** | 50 mm/s | Balanced speed for a smooth top-surface finish. |
| **Printing Temp** | 200°C | Optimal flow for PLA to ensure the layers bond perfectly. |
| **Build Plate Temp** | 60°C | Keeps the wide, flat base from peeling off the bed. |
| **Initial Layer Speed**| 15 mm/s | Extra slow start to guarantee the "tail" and "fins" stick perfectly. |

---

### 🛠️ 4. Step-by-Step Workflow
* **📂 File Preparation:** Imported `bookshark.stl` into the Slicer. I used the **"Rotate"** tool to ensure it was laying completely flat on the virtual bed.
* **💾 G-Code Generation:** Processed the file and saved the `.gcode` to the microSD card.
* **🧼 Printer Setup:** Cleaned the build plate with **IPA (Isopropyl Alcohol)**. For flat objects, any finger grease can cause the corners to lift (warp).
* **📐 Bed Leveling:** Performed a precise **4-point leveling** check. For a bookmark, the "Z-offset" must be perfect across the entire surface.
* **🚀 Execution:** Started the print and watched the first layer closely. If the first layer looks like "transparent tape," the nozzle is too close; if it looks like "round spaghetti," it is too high.

---




### 5. Post-Print Analysis

* **Articulation Check:** All segments (head, body, tail) move smoothly. The joints did not fuse.
* **Bed Adhesion:** No "warping" was observed, and even the smallest tail segments remained attached until the print was complete.
* **Tolerance:** The gaps between the joints are clean, indicating that the retraction settings and cooling fan are functioning correctly.

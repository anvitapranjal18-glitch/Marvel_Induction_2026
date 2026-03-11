## **Task 6: The Matrix Puzzle — Decoding with NumPy & Matplotlib**

### **Description**

The core objective of this task was to solve a visual cryptographic puzzle by manipulating a scrambled dataset using **NumPy** and **Matplotlib**. The challenge involved taking a raw, 1D encoded array and applying a series of mathematical transformations—including **dimensional reshaping**, **transposition**, and **axial flipping**—to reveal a hidden image. This task emphasizes the power of vectorized operations and the relationship between numerical matrices and digital image visualization.

### **Detailed Process**

- **Data Acquisition & Shape Analysis:** I began by loading the scrambled matrix. To determine the target dimensions, I calculated the total number of elements ($N$). Following the clue to "reshape into a square," I derived the side length ($s$) using $s = \sqrt{N}$.

  ```python
  import numpy as np
  import matplotlib.pyplot as plt

  # Loading the data
  data = np.load('scrambled_matrix.npy')
  size = int(np.sqrt(data.size))
  matrix = data.reshape((size, size))
  ```

- **Decoding via Matrix Manipulation:** Based on the cryptic clues provided, I applied a sequence of NumPy transformations to "de-scramble" the visual data:
  1. **Orientation Correction:** The clue _"data might be sideways"_ suggested a **Transpose** operation to swap rows and columns.
  2. **Positional Realignment:** The clue _"the end is actually the beginning"_ indicated a **Flip** operation, reversing the order of elements along a specific axis.
  ```python
  # Correcting orientation and mirroring
  decoded_matrix = np.transpose(matrix)
  decoded_matrix = np.flip(decoded_matrix, axis=1) # Horizontal flip
  ```
- **Visualization & Rendering:** Once the matrix was mathematically restored, I utilized `matplotlib.pyplot.imshow()` to render the numerical array as a grayscale/RGB image. I experimented with different colormaps (`cmap='gray'`) to ensure the hidden image was clearly visible.
  ```python
  plt.imshow(decoded_matrix, cmap='magma')
  plt.title("Revealed Secret Image")
  plt.axis('off') # Clean report presentation
  plt.show()
  ```

### **Decoding Logic (The Clues)**

| Clue                              | Technical Interpretation           | NumPy Function Used     |
| :-------------------------------- | :--------------------------------- | :---------------------- |
| _"Reshape into a square"_         | Convert 1D array to 2D $(s, s)$    | `np.reshape()`          |
| _"Data might be sideways"_        | Swap the X and Y axes              | `np.transpose()` / `.T` |
| _"End is actually the beginning"_ | Reverse the elements along an axis | `np.flip()`             |

### **Technical Skills Gained**

- **Dimensional Intelligence:** Mastering the transition between flat data arrays and multi-dimensional structures.
- **Vectorized Transformations:** Efficiently reorienting large datasets without using nested `for` loops, significantly reducing computational overhead.
- **Data Visualization:** Learning to interpret 2D arrays not just as numbers, but as spatial data that can be plotted and analyzed visually.
- **Algorithmic Debugging:** Applying logical deductions to solve "black box" data puzzles through trial, error, and mathematical properties.

---

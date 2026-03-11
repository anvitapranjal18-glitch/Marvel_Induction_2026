## **Task 5: Build Your Own Brain - Linear Regression from Scratch**

### **Description**

The core objective of this task was to demystify the "black box" of Machine Learning by implementing a **Univariate Linear Regression** model from the ground up using **NumPy**. This involved manually deriving the mathematics of **Gradient Descent**—the engine behind most modern AI—to minimize a defined **Cost Function**. The project required benchmarking a custom-built optimizer against the industry-standard `scikit-learn` implementation using the **California Housing Dataset**, emphasizing the critical role of feature engineering and hyperparameter tuning in predictive modeling.

### **Detailed Process**

- **Mathematical Foundation & Model Setup:** I initialized the linear hypothesis $y = wx + b$. Unlike high-level libraries that handle weight initialization automatically, I manually set the weight ($w$) and bias ($b$) to zero and implemented the **Mean Squared Error (MSE)** as my objective function to quantify the model's prediction error:
  $$J(w, b) = \frac{1}{2n} \sum_{i=1}^{n} (y_{pred}^{(i)} - y_{actual}^{(i)})^2$$

- **Optimization via Gradient Descent:** To minimize the cost function, I implemented the **Gradient Descent** algorithm. This involved calculating the partial derivatives (gradients) of the MSE with respect to $w$ and $b$ to determine the direction of steepest descent:

  - $\frac{\partial J}{\partial w} = \frac{1}{n} \sum (x_i \cdot (y_{pred} - y_{actual}))$
  - $\frac{\partial J}{\partial b} = \frac{1}{n} \sum (y_{pred} - y_{actual})$

  I then iteratively updated the parameters using a **Learning Rate ($\alpha$)**:

  ```python
  # Parameter Update Rule
  self.w -= self.lr * dw
  self.b -= self.lr * db
  ```

- **Feature Scaling (Standardization):** During initial testing, the model diverged due to the varying scales of the housing data. I resolved this by applying **Z-score Normalization**, ensuring the features had a mean of 0 and a standard deviation of 1. This allowed the gradient descent to converge much faster and more reliably.

- **Benchmarking & Validation:** After training the scratch model over 1000+ epochs, I compared its final weights and performance metrics (**MSE**, **MAE**, and **R²**) against `sklearn.linear_model.LinearRegression`. This verified that my manual implementation reached a near-identical "Global Minimum" as the optimized library.

- **Data Visualization:** Using **Matplotlib**, I generated a regression plot showing the "Line of Best Fit" cutting through the California Housing data points, providing visual proof of the model's convergence.

### **Model Comparison & Performance**

| Metric                        | Manual Scratch Model       | Scikit-Learn (Library)       |
| :---------------------------- | :------------------------- | :--------------------------- |
| **Mean Squared Error (MSE)**  | 0.524                      | 0.524                        |
| **Mean Absolute Error (MAE)** | 0.531                      | 0.531                        |
| **R² Score**                  | 0.601                      | 0.606                        |
| **Execution Logic**           | Iterative Gradient Descent | Ordinary Least Squares (OLS) |

### **Technical Skills Gained**

- **Vectorized Mathematics:** Optimized performance by using **NumPy** matrix dot products instead of slow Python `for` loops.
- **Hyperparameter Tuning:** Learned the sensitivity of the **Learning Rate ($\alpha$)**—finding the balance where the model converges without oscillating or diverging.
- **Cost Surface Analysis:** Gained an intuitive understanding of how optimization algorithms navigate a mathematical landscape to find the lowest error.
- **Metric Interpretation:** Mastered the use of **R² (Coefficient of Determination)** to evaluate how well the independent variables explain the variance in the target.

---

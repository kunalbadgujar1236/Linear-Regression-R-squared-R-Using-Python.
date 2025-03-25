# 📊 Linear Regression & R-squared (R²) Example

This project demonstrates **Linear Regression** and **R-squared (R²)** using Python. We predict **exam scores** based on **study hours** and evaluate how well the model fits the data.

---

## 🔹 Project Overview  
- Uses **Linear Regression** to find the relationship between **study hours** and **exam scores**.  
- Calculates **R-squared (R²)** to measure how well the model predicts exam scores.  
- Visualizes actual vs. predicted values using **Matplotlib**.  

---

## 🔹 Formula Used  
\[
\text{Score} = 5 \times \text{Study Hours} + 40
\]
- **5** → For every extra hour of study, the score increases by **5 points**.  
- **40** → The starting score if study hours = **0**.  

---

## 🔹 R-squared (R²) Interpretation  
- **R² = 1** → Perfect fit (model predicts scores exactly).  
- **R² close to 1** → Good fit (most score variations are explained).  
- **R² close to 0** → Bad fit (study hours don’t explain scores well).  

---

## 🔹 Python Code Snippet  
```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score

# Example Data
study_hours = np.array([2, 4, 6, 8, 10]).reshape(-1, 1)
exam_scores = np.array([50, 62, 68, 83, 88])

# Train Model
model = LinearRegression()
model.fit(study_hours, exam_scores)
predicted_scores = model.predict(study_hours)

# Calculate R²
r2 = r2_score(exam_scores, predicted_scores)
print(f"R-squared (R²): {r2:.2f}")

# Plot
plt.scatter(study_hours, exam_scores, color='blue', label="Actual Scores")
plt.plot(study_hours, predicted_scores, color='red', linestyle="--", label="Regression Line")
plt.xlabel("Study Hours")
plt.ylabel("Exam Score")
plt.title(f"Linear Regression (R² = {r2:.2f})")
plt.legend()
plt.show()

![Study Hours vs Exam Score]([R2-squred-4output.png](https://github.com/kunalbadgujar1236/Linear-Regression-R-squared-R-Using-Python./blob/main/R2-squred-4output.png) 

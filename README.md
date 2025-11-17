# Regularization_ANN
# 🧠 Regularization to Prevent Overfitting (ANN on Moons Dataset)  
**AI-Generated README.md**

---

## 📘 Overview  
This README explains how **L2 Regularization (Kernel Regularizer)** helps prevent overfitting in an ANN trained on the **Moons dataset**.  
You first trained a large network that overfit heavily, then added L2 regularization and observed clean improvement.

---

## 📂 1. Moons Dataset — Visualization
- Used `make_moons` dataset from sklearn.  
- Scatter plot (Image 1 attached) shows two moon-shaped semi-circular clusters.  
- Perfect for testing overfitting & regularization behavior.  

---

## 📂 2. Model 1 — ANN *Without Regularization* (Overfits)

### **Architecture**
- Dense(128, ReLU)  
- Dense(128, ReLU)  
- Dense(1, Sigmoid)  
- Optimizer: Adam  
- Metrics: Accuracy  
- Epochs: **2000**  

### **Results**
#### 🔴 Overfit Observed
- **Decision Boundary (Image 2 attached):**  
  - Highly wiggly, irregular  
  - Model tries to perfectly memorize noise  
- **Loss & Val Loss Plot (Image 3 attached):**  
  - Training loss → approaches **0**  
  - Validation loss → **increases**  
  - Classic overfitting curve  

#### 🔴 Weight Inspection
- **Box plot of weights (Image 5 attached):**  
  - Large spread  
  - Many extreme weights  
  - Indicates heavy memorization  

---

## 📂 3. Model 2 — ANN *With L2 Regularization*

### **Regularization Used**
- `kernel_regularizer=tf.keras.regularizers.l2(0.03)`  
- Applied to all hidden layers while keeping architecture same.  

### **Results**
#### 🟢 Overfitting Removed
- **Decision Boundary (Image 4 attached):**  
  - Smooth  
  - Generalized  
  - No noisy “jagged edges”  

#### 🟢 Stable Learning
- **Loss vs Val Loss (Image 5 attached):**  
  - Both decrease together  
  - No divergence  
  - Indicates regularization success  

#### 🟢 Weight Decay Effect
- **Box plot of weights (Image 6 attached):**  
  - Weights clustered close to zero  
  - No extreme values  
- **Distribution plot (Image 7 attached):**  
  - Weight distribution centered near zero  
  - Clean weight shrinkage due to regularizer  

---

## 🎯 Key Takeaways  

| Model | Decision Boundary | Loss Curve | Weights | Overfitting |
|-------|-------------------|------------|---------|-------------|
| Without Regularization | Noisy & complex | Diverging | Extreme, large | Yes |
| With L2 Regularization | Smooth & clean | Stable | Near zero | No |

### Why L2 Regularization Works:
- Penalizes large weights  
- Forces network to learn *simpler patterns*  
- Prevents memorization  
- Leads to better generalization  

---

## 📎 Attached Images Reference  

1. Moons dataset scatter plot
   <img width="559" height="413" alt="reg1" src="https://github.com/user-attachments/assets/ac13ac9e-42b7-43f9-9514-bdb1274b2cb4" />
  
3. Decision boundary (overfit model)
   <img width="563" height="418" alt="reg2" src="https://github.com/user-attachments/assets/e6d0d0a2-a364-4524-97fd-e0d50db1475f" />
 
5. Loss & Val loss (overfitting)
   <img width="547" height="413" alt="reg3" src="https://github.com/user-attachments/assets/79cb61fa-66aa-4b56-92d8-13bfc62d4f0d" />

7. Decision boundary (regularized model)
   <img width="563" height="418" alt="reg4" src="https://github.com/user-attachments/assets/67056a9e-4c98-4c29-b15b-ec0eacc3df96" />

9. Weight boxplot — model 1
    <img width="547" height="413" alt="reg5" src="https://github.com/user-attachments/assets/0f483b55-8fc6-4994-a515-d194eace025a" />

11. Weight boxplot — model 2
    <img width="546" height="394" alt="reg6" src="https://github.com/user-attachments/assets/ce8ddcac-b007-4bba-8650-dbecc8522e48" />

13. Weight distribution plot — model 2  
<img width="559" height="394" alt="reg7" src="https://github.com/user-attachments/assets/1953cbc3-7034-4106-af14-f7ca83fa33e9" />

<img width="562" height="413" alt="reg8" src="https://github.com/user-attachments/assets/0cdc2174-9f74-4e2d-9a9c-a8a1435ab965" />


---

## ✔️ Final Conclusion  
**Kernel Regularization (L2) is one of the most powerful methods to reduce overfitting.  
It keeps weights small, controls model complexity, and creates smooth decision boundaries.**

---

> ⚠️ *This README.md file is fully AI-generated based on your experiment description.*

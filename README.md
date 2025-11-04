# 🌲 Forest Cover Type Prediction — Machine Learning Project

## 🧭 Overview
This project aims to **predict the type of forest cover** for a 30×30 meter patch of land in the Roosevelt National Forest (Colorado, USA).  
Using topographic and environmental data, the model classifies land areas into one of seven forest cover types.

**Goal:** Build a high-accuracy classification model that can identify the forest type based on environmental and soil parameters.

---

## 🌍 Dataset Information
**Source:** Roosevelt National Forest, Colorado  
**Task:** Multiclass classification (7 cover types)

| Label | Forest Cover Type |
|:------|:------------------|
| 1 | Spruce/Fir |
| 2 | Lodgepole Pine |
| 3 | Ponderosa Pine |
| 4 | Cottonwood/Willow |
| 5 | Aspen |
| 6 | Douglas-fir |
| 7 | Krummholz |

### 🔹 Key Features
- **Elevation** — Elevation in meters  
- **Aspect** — Compass direction in degrees  
- **Slope** — Degree of slope  
- **Horizontal/Vertical Distance** — To hydrology, roads, and fire points  
- **Hillshade** — Shade index at 9am, noon, and 3pm  
- **Wilderness_Area** — 4 binary columns  
- **Soil_Type** — 40 binary columns  
- **Target:** `Cover_Type` (1–7)

---

## ⚙️ Project Workflow
1. **Data Loading & Cleaning** — Checked missing values, ensured class balance  
2. **Feature Analysis** — Visualized class distribution, correlation matrix  
3. **Preprocessing** —  
   - Standard scaling for numeric features  
   - Stratified train-test split  
   - Label encoding adjusted for XGBoost/LightGBM (0–6 indexing)  
4. **Modeling** — Compared multiple algorithms:
   - Logistic Regression  
   - Random Forest  
   - XGBoost  
   - LightGBM  
5. **Evaluation** — Accuracy, classification report, and confusion matrix  
6. **Model Export** — Best model saved with `joblib`  

---

## 📊 Model Performance

| Model | Accuracy |
|:------|----------:|
| **LightGBM** | **0.8853** |
| XGBoost | 0.8833 |
| Random Forest | 0.8674 |
| Logistic Regression | 0.6911 |

✅ **Best Model:** LightGBM (Accuracy ≈ 88.5%)  
Balanced performance, fast training, and efficient prediction.

---

## 🧠 Insights
- **Elevation, Hillshade, and Soil Type** are the strongest predictors of cover type.  
- **Tree-based models** (LightGBM, XGBoost) outperform linear models due to complex feature interactions.  
- **Regularization and feature sampling** in boosting prevent overfitting effectively.

---

🚀 Future Enhancements

Add SHAP or LIME for feature explainability

Hyperparameter tuning with Optuna or GridSearchCV

Deploy via Streamlit for real-time forest type predictions

Integration with geospatial APIs for interactive maps

---

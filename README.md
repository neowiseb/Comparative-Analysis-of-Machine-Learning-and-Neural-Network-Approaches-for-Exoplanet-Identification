# Comparative-Analysis-of-Machine-Learning-and-Neural-Network-Approaches-for-Exoplanet-Identification
MSc Research Project Artificial Intelligence
# Exoplanet Identification Using Machine Learning and Neural Networks

This project investigates the use of machine learning and deep learning techniques to detect **exoplanets** from stellar flux data collected by NASA’s **Kepler Space Telescope**.

The goal of the project is to compare traditional machine learning models and neural network architectures to determine which approach performs better when working with noisy astronomical datasets.

⚠️ **Note:**  
 The goal of the project was to explore different algorithms and understand how model performance changes depending on the characteristics of the dataset. Therefore, there are still many areas where the implementation could be improved.

---

## Project Goal

Exoplanets can be detected using the **transit method**, where a planet passing in front of a star causes small periodic drops in the star’s brightness. These drops can be observed in **stellar light curves (flux measurements over time)**.

Machine learning models can automatically learn patterns in these light curves to classify whether a star hosts an exoplanet or not.

This project compares several machine learning and deep learning methods to determine which performs best for this task.

---

## Dataset

The dataset used in this project comes from **NASA's Kepler Mission** and was obtained from Kaggle.

Dataset characteristics:

- **5087 stars (samples)**
- **3198 flux measurements per star (features)**
- Binary classification:
  - `1` → Non-exoplanet star
  - `0` → Exoplanet star

The dataset contains **noisy astronomical signals**, which makes exoplanet detection challenging.

---

## Project Pipeline

1. **Data preprocessing**
   - Data normalization
   - Dimensionality reduction using PCA
   - Handling class imbalance using SMOTE

2. **Model training**

Machine Learning models:
- K-Nearest Neighbors (KNN)
- Decision Tree
- Logistic Regression
- AdaBoost
- XGBoost

Neural Network models:
- Fully Connected Neural Network (SELU activation)
- Fully Connected Neural Network (Swish activation + Adam optimizer)
- 1D Convolutional Neural Network (CNN)
- Long Short-Term Memory (LSTM)

3. **Model evaluation**

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix
- ROC Curve

---

## Results

| Model | Accuracy | Precision | Recall | F1 Score |
|------|---------|---------|--------|---------|
| KNN | 0.98 | 0.98 | 0.98 | 0.98 |
| Decision Tree | 0.93 | 0.94 | 0.94 | 0.94 |
| Logistic Regression | 0.62 | 0.75 | 0.62 | 0.56 |
| AdaBoost | **0.98** | **0.99** | **0.99** | **0.99** |
| XGBoost | **0.98** | **0.99** | **0.99** | **0.99** |
| Fully Connected (SELU) | 0.63 | 0.50 | 0.52 | 0.60 |
| Fully Connected (Adam) | 0.88 | 0.50 | 0.50 | 0.50 |
| 1D CNN | 0.92 | 0.50 | 0.49 | 0.49 |
| LSTM | 0.87 | 0.88 | 0.87 | 0.87 |

**Key finding:**  
Ensemble models such as **AdaBoost and XGBoost** performed better than neural networks for this dataset. This is likely because the dataset is relatively small and contains significant noise, which can lead neural networks to overfit.

---

## Tech Stack

- Python
- Google Colab
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- Matplotlib
- Seaborn
- Imbalanced-learn (SMOTE)

---

## Limitations

- Dataset contains **significant noise**
- Neural networks may require **larger datasets**
- Limited hyperparameter tuning
- Potential overfitting in deep learning models

---

## Future Work

Possible improvements:

- Use larger astronomical datasets
- Apply more advanced neural network architectures
- Improve hyperparameter tuning
- Explore hybrid models combining ML and deep learning


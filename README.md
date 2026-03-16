# Climate Change Impact on Global Food Supply 🌍🌾

A machine learning study evaluating how climate change affects global food supply chains, using **XGBoost**, **Decision Tree Regressor**, and **LSTM** models to predict crop yields from historical climate and agricultural data.

---

## 📌 Problem Statement

Global food systems are under increasing strain from rising temperatures, erratic rainfall, and extreme weather events. Traditional models fail to capture the complex, non-linear relationships between climate variables and crop yields. This project applies machine learning to analyze these relationships and support adaptive strategies for food security.

---

## 🎯 Objectives

- Predict crop yields using climate variables (temperature, rainfall, pesticide use, population)
- Compare actual vs optimal model performance across three ML algorithms
- Identify the most influential climate features driving yield fluctuations
- Build a scalable, data-driven framework for food security analysis

---

## 📁 Project Structure
```
climate-food-supply-ml/
├── notebooks/
│   ├── Copy_of_AI_ML_Project.ipynb      # Main ML analysis notebook
│   └── Source_Code_Group_3.ipynb        # Source code notebook
├── data/
│   ├── YieldNew.csv                     # Crop yield data (hg/ha) – FAOSTAT
│   ├── PesticidesNew.csv                # Pesticide usage data – FAOSTAT
│   ├── RainfallNew.csv                  # Annual precipitation – World Data Bank
│   ├── temp.csv                         # Average annual temperature – World Data Bank
│   └── Population.csv                   # Population data – FAOSTAT
├── reports/
│   ├── ML_Final_Report_Group_3.pdf      # Full written report
│   └── ML_Project_ppt_Group_3.pdf       # Presentation slides
└── README.md
```

---

## 📊 Dataset

Data spans **1970–2023** across multiple countries, sourced from:

| Feature | Source | Description |
|--------|--------|-------------|
| `hg/ha_yield` | FAOSTAT | Crop productivity per hectare |
| `pesticides_tonnes` | FAOSTAT | Pesticide usage quantity |
| `population` | FAOSTAT | Country-level population |
| `average_precipitation_mm_per_year` | World Data Bank | Annual rainfall |
| `avg_temp` | World Data Bank | Average annual temperature |

---

## 🤖 Models

### 1. XGBoost ⭐ Best Performer
- Handles missing data and non-linear relationships
- L1/L2 regularization to prevent overfitting
- **R² = 0.982 | RMSE = 0.87**
- Key insight: Temperature variability and rainfall trends were the most influential features

### 2. Decision Tree Regressor
- Simple, interpretable tree-based splits
- Hyperparameters tuned: max depth, min samples per split/leaf
- **R² = 0.981 | RMSE = 1.45**
- Key insight: Transparent decision rules, easy to explain to non-technical stakeholders

### 3. LSTM (Long Short-Term Memory)
- Sequential neural network capturing temporal dependencies
- 2 LSTM layers (50 units each) + dropout + Adam optimizer
- Trained over 100 epochs with sliding window (past 5 years → next year)
- **R² = 0.774 | MSE = 1.12**
- Key insight: Best at modeling delayed, long-term climate effects on yield

---

## 📈 Model Comparison

| Model | R² Score | RMSE / MSE | Strength |
|-------|----------|------------|---------|
| XGBoost | **0.982** | RMSE: 0.87 | Accuracy, feature selection |
| Decision Tree | 0.981 | RMSE: 1.45 | Interpretability, speed |
| LSTM | 0.774 | MSE: 1.12 | Temporal & sequential patterns |

---

## ⚙️ Methodology

1. **Data Preprocessing** — Median imputation, one-hot encoding, MinMaxScaler normalization
2. **Feature Selection** — Correlation heatmap analysis across all climate/agricultural features
3. **Train-Test Split** — 80% training / 20% testing
4. **Model Training** — Hyperparameter tuning for each model
5. **Evaluation** — R², RMSE, MSE metrics + residual analysis + feature importance

---

## 🔧 Requirements
```bash
pip install numpy pandas scikit-learn xgboost tensorflow matplotlib seaborn
```

---

## 🚀 Getting Started
```python
# Clone the repo
git clone https://github.com/YOUR_USERNAME/climate-food-supply-ml.git
cd climate-food-supply-ml

# Install dependencies
pip install -r requirements.txt

# Open the main notebook
jupyter notebook notebooks/Copy_of_AI_ML_Project.ipynb
```

---

## 🔮 Future Work

- Integrate satellite imagery, soil quality, and pest activity data
- Apply CNNs for spatial pattern recognition
- Develop region-specific and crop-specific models
- Add socioeconomic factors (trade policies, labor availability)
- Build real-time IoT monitoring systems with predictive alerts

---

## 📚 References

1. Schlenker & Roberts (2009) — Nonlinear temperature effects on US crop yields. *PNAS*
2. Wheeler & von Braun (2013) — Climate change impacts on global food security. *Science*
3. Tubiello et al. (2007) — Crop and livestock response to climate change. *PNAS*
4. Rolnick et al. (2019) — Tackling Climate Change with Machine Learning
5. Rosenzweig & Parry (1994) — Potential impact of climate change on world food supply

---


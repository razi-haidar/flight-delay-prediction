# ✈️ Global Flight Delay Prediction and Optimization Dashboard

A scalable machine learning pipeline to predict flight delays using 11.6M+ records, optimized from 8 hours to 1.5 hours, with a Power BI dashboard recommending $10M+ in savings through 20% delay reduction. Built with PySpark, Python, and Power BI in Google Colab.

## 📖 Project Overview
This project predicts flight delays for global airlines, processing 11.6M+ flight records from `flights.csv`, `airlines.csv`, and `airports.csv`. Key features include:

- **PySpark ML Pipeline**: Random Forest and Logistic Regression (AUC 0.7, F1 ~0.8), optimized for Colab’s free tier (12GB RAM).
- **Class Imbalance Handling**: Dynamic weights (e.g., 5.71 for delays) improve precision from 0.85 to ~0.9.
- **Feature Engineering**: Includes `RouteFrequency`, `PrevDelay`, `IsWeekend`, `IsPeakHour`.
- **EDA**: SQL queries analyze delay patterns by airline, month, and route.
- **Power BI Dashboard**: Interactive maps, KPI cards, and slicers visualize predictions and insights.
- **Business Impact**: Recommends scheduling adjustments to save $10M+ annually by reducing delays 20%.

The pipeline is enterprise-ready, reducing runtime from 8 hours to 1.5 hours via sampling, checkpointing, and Spark tuning.

## 🎯 Key Features

- **Scalable ML**: Processes 11.6M+ rows with PySpark, achieving AUC ~0.7 and F1 ~0.8.
- **Optimized Runtime**: 10% sampling (~1.16M rows), 2-fold CV, and Spark configs (6g memory, 50 partitions).
- **Class Imbalance**: Dynamic weights reduce false positives, boosting precision.
- **Visualizations**: Feature importance, ROC curve, and confusion matrix (Plotly, HTML output).
- **Power BI**: Interactive dashboard for operational insights.
- **Robustness**: Checkpoints, logging (`pipeline.log`), and Parquet fallback.
- **Output**: Single `predictions.csv` with `delay_probability` for Power BI.

## 🛠️ Tech Stack

- **Languages**: Python 3.11
- **Big Data**: PySpark 3.5 (Spark ML, Spark SQL)
- **Data Science**: Pandas, Scikit-learn, Plotly
- **Visualization**: Power BI 2025
- **Environment**: Google Colab (free tier, ~12GB RAM)
- **Other**: Git, GitHub, Google Drive

## 📊 Results

### Model Performance

| Model              | AUC   | F1 Score | Precision | Recall |
|-------------------|-------|----------|-----------|--------|
| Random Forest     | ~0.70 | ~0.80    | ~0.90     | ~0.70  |
| Logistic Regression| ~0.70 | ~0.80    | ~0.90     | ~0.70  |

### Confusion Matrix (Test Set)

| IsDelayed \ Prediction | 0.0    | 1.0    |
|------------------------|--------|--------|
| 0 (No Delay)           | ~32,443| ~500   |
| 1 (Delay)              | ~1,000 | ~4,600 |

**Business Impact**: Recommendations (e.g., optimize peak-hour scheduling) could save $10M+ annually ($74/delay minute).

### Visualizations

- **Feature Importance**: `PrevDelay` and `RouteFrequency` are top predictors.
- **ROC Curve**: AUC ~0.7 for RF and LR.
- **Power BI Dashboard**: Interactive maps and KPIs.

## 📂 Repository Structure
```
flight-delay-prediction/
├── data/
│   ├── predictions.csv
│   └── README.md
├── notebooks/
│   └── Flight_Delay_Prediction.ipynb
├── visualizations/
│   ├── feature_importance.html
│   └── roc_curve.html
├── dashboard/
│   └── Flight_Delay_Dashboard.pbix
├── logs/
│   └── pipeline.log
├── screenshots/
│   ├── power_bi_dashboard.png
│   └── feature_importance.png
├── README.md
└── LICENSE
```

**Note**: Datasets not included due to size. Download from Kaggle and place in `/content/drive/MyDrive/flight_data/`.

## 🚀 Getting Started

### Prerequisites
- Google Colab account
- Google Drive
- Power BI Desktop (2025)
- Python packages: `pyspark`, `pandas`, `scikit-learn`, `plotly`, `powerbiclient`, `psutil`

### Setup
```bash
git clone https://github.com/razi-haidar/flight-delay-prediction.git
cd flight-delay-prediction
```

### Upload Datasets
- Download from Kaggle.
- Place in `/content/drive/MyDrive/flight_data/`.

### Open Colab Notebook
```python
from google.colab import drive
drive.mount('/content/drive')
```

### Running the Pipeline
- Execute notebook cells step-by-step.
- Runtime: ~1.5 hours on Colab free tier.
- Monitor logs: `pipeline.log`

### View Visualizations
- Open `feature_importance.html`, `roc_curve.html` in browser.

### Power BI Dashboard
- Download and open `Flight_Delay_Dashboard.pbix`.
- Import `predictions.csv`.
- Customize column `delay_probability` to "Delay Probability".

### GitHub Packaging
- Push updates with `Flight_Delay_Prediction.ipynb`, `predictions.csv`, visualizations/, and dashboard.

## 🔧 Pipeline Details

### Data Processing
- Input: 11.6M+ rows from CSVs
- Features: `DayOfWeek`, `DepHour`, `RouteFrequency`, `PrevDelay`, etc.

### Machine Learning
- Models: RF, LR
- Optimizations: sampling, simplified grid, checkpoints
- Output: `predictions.csv`

### Visualizations
- Feature Importance
- ROC Curve
- Power BI Dashboard

## 💡 Business Insights

- **Top Predictors**: `PrevDelay`, `RouteFrequency`
- **High-Risk Routes**: JFK-LAX, etc.
- **Recommendations**:
  - Optimize peak hours
  - Prioritize high-frequency routes
  - Estimated savings: $10M+

## 🔍 Troubleshooting README Rendering

- **Missing Images**: Place in `screenshots/`, use relative paths
- **Formatting**: Use GitHub "Preview" tab
- **Large Data**: Mention in `data/README.md`

## 🔧 Troubleshooting Pipeline

- **Memory**: Reduce sample or upgrade Colab
- **Slow Runtime**: Check logs
- **File Errors**: Verify paths
- **Schema**: Confirm printSchema()
- **Power BI**: Ensure number format for `delay_probability`

## 🤝 Contributing

1. Fork the repo
2. Create branch `feature/YourFeature`
3. Commit, push, and open PR

## 📜 License
MIT License

## 📨 Contact

**Author**: Razi Haidar  
**GitHub**: [razi-haidar](https://github.com/razi-haidar)  
**Email**: razi.haidar2002@gmail.com  
**LinkedIn**: [razi-haidar](https://linkedin.com/in/razi-haidar)

## 🌟 Acknowledgments
- Kaggle flight delay dataset
- PySpark & Power BI documentation
- Plotly, Scikit-learn, open-source community

**Star this repo if you found it useful!** 🌟


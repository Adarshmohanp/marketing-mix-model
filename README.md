
# Marketing Mix Modeling (MMM) Analysis

## 📋 Project Overview

This project implements a Marketing Mix Model (MMM) to analyze the effectiveness of various marketing channels. Using historical weekly data, the model quantifies the impact of different marketing activities on revenue and calculates Return on Investment (ROI) to inform budget allocation decisions.

## 📁 Repository Structure

```
MARKETING-MIX-MODEL/
│
├── data/
│   └── Weekly.csv              # Raw weekly data (marketing spend & revenue)
│
├── notebooks/
│   └── marketing_mix_model.ipynb  # Main Jupyter notebook with complete analysis
│
├── feature_importance.csv      # Generated: Feature importance rankings
├── marketing_roi.csv           # Generated: ROI calculations by channel
├── full_results.csv            # Generated: Dataset with predictions
├── requirements.txt            # Python dependencies
└── README.md                   # This file
```

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- pip (Python package manager)

### Installation & Setup

1. **Clone or download this repository**
   ```bash
   git clone <your-repository-url>
   cd MARKETING-MIX-MODEL
   ```

2. **Create a virtual environment (recommended)**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install required packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```

5. **Open and run the analysis**
   - Navigate to the `notebooks/` folder
   - Open `marketing_mix_model.ipynb`
   - Run all cells sequentially (Kernel > Restart & Run All)

## 📊 Data Requirements

Your `data/Weekly.csv` file should contain:

- **Required**: A `revenue` column (target variable)
- **Marketing channels**: Columns containing spend amounts (e.g., `tv_spend`, `digital_spend`, `social_media_spend`)
- **Optional**: Other potential drivers like `price`, `promotions`, `competitor_activity`

Example format:
```csv
week,revenue,tv_spend,digital_spend,social_spend
2023-01-01,150000,25000,18000,12000
2023-01-08,145000,23000,19000,11000
```

## 🔬 Methodology

The analysis uses:

1. **Adstock Transformation**: Models the carryover effect of marketing spend over time
2. **Diminishing Returns**: Applies logarithmic saturation to model realistic response curves
3. **ElasticNet Regression**: Regularized linear model that handles multicollinearity and identifies important features
4. **ROI Calculation**: Computes return on investment for each marketing channel

## 📈 Outputs

After running the notebook, the following files will be generated:

- `feature_importance.csv`: Ranking of marketing channels by impact on revenue
- `marketing_roi.csv`: ROI calculations for each marketing channel
- `full_results.csv`: Original data augmented with model predictions

## 🎯 Key Insights

The analysis provides:

- **Channel Effectiveness**: Which marketing channels drive the most revenue
- **ROI Rankings**: Which channels provide the best return on investment
- **Budget Optimization**: Data-driven recommendations for reallocating marketing spend
- **Performance Forecast**: Expected revenue based on current marketing mix

## ⚙️ Customization

To adapt this model to your specific needs:

1. **Add new channels**: Include additional spend columns in your CSV file
2. **Adjust parameters**: Modify the `adstock_decay` rate or saturation function
3. **Add covariates**: Include other factors that might influence revenue
4. **Change time period**: Adjust the weekly data to your business cycle

## 🐛 Troubleshooting

### Common Issues

1. **File not found error**
   - Ensure `Weekly.csv` is in the `data/` folder
   - Check the filename is exactly `Weekly.csv` (case-sensitive)

2. **Missing dependencies**
   ```bash
   pip install --upgrade -r requirements.txt
   ```

3. **Memory errors**
   - Reduce the number of marketing channels
   - Use fewer weeks of historical data

## 📝 License

This project is for analytical purposes. Please ensure you have the right to use any proprietary data included in the analysis.

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request






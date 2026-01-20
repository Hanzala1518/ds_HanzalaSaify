# Trader Behavior & Market Sentiment Analysis

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)
[![License](https://img.shields.io/badge/License-Internal-red.svg)]()

**Author:** Hanzala Saify  
**Date:** January 2026

---

## Project Overview

This research project analyzes **211,000+ cryptocurrency trade executions** to understand how trader behavior changes under different market sentiment regimes. By integrating the Fear & Greed Index with granular trading data, we extract actionable intelligence for:

- **Position sizing** based on sentiment
- **Entry/exit timing** optimization
- **Risk management** adjustments
- **Trader profiling** and behavioral clustering

The analysis reveals statistically significant differences in trader profitability between Fear and Greed periods, with contrarian strategies showing measurable edge over momentum-following behavior.

---

## Folder Structure

```
ds_hanzala_saify/
│
├── notebook_1.ipynb              # Data preparation & feature engineering
├── notebook_2.ipynb              # Sentiment analysis & behavioral insights
├── README.md                     # Project documentation (this file)
├── ds_report.md                  # Full research report (PDF-ready)
│
├── csv_files/                    # Data files
│   ├── historical_data.csv       # Raw trade executions (211K+ rows)
│   ├── fear_greed_index.csv      # Daily sentiment index (2018-present)
│   ├── trader_cleaned.csv        # [Generated] Cleaned trade data
│   ├── trader_daily_metrics.csv  # [Generated] Daily aggregations
│   ├── sentiment_cleaned.csv     # [Generated] Processed sentiment
│   └── merged_trader_sentiment.csv # [Generated] Integrated dataset
│
└── outputs/                      # Generated visualizations
    ├── 01_pnl_distribution.png
    ├── 02_trade_size_vs_leverage.png
    ├── 03_volume_concentration.png
    ├── 04_long_short_bias.png
    ├── 05_pnl_by_sentiment.png
    ├── 06_leverage_by_sentiment.png
    ├── 07_pnl_leverage_interaction.png
    ├── 08_contrarian_vs_momentum.png
    ├── 09_cluster_elbow.png
    └── 10_trader_clusters.png
```

---

## Execution Order

Execute notebooks sequentially. Each notebook depends on outputs from the previous.

### Step 1: Data Preparation (notebook_1.ipynb)

```
Runtime: ~2-3 minutes
```

| Task | Description |
|------|-------------|
| Data Loading | Load 211K+ trade executions |
| Cleaning | Timestamp conversion, normalization, outlier removal |
| Feature Engineering | Trade-level + daily aggregation features |
| EDA | 4 visualizations with behavioral insights |
| Output | `trader_cleaned.csv`, `trader_daily_metrics.csv` |

### Step 2: Sentiment Analysis (notebook_2.ipynb)

```
Runtime: ~3-4 minutes
```

| Task | Description |
|------|-------------|
| Sentiment Prep | Process Fear & Greed Index, create binary classification |
| Integration | Merge trader metrics with sentiment data |
| Analysis A | Profitability vs. Sentiment (Mann-Whitney U test) |
| Analysis B | Leverage & Risk amplification during Fear |
| Analysis C | Contrarian vs. Momentum trading performance |
| Analysis D | Trader clustering with PCA visualization |
| Output | `sentiment_cleaned.csv`, `merged_trader_sentiment.csv`, 6 plots |

---

## Google Colab Links

Run these notebooks directly in your browser:

| Notebook | Colab Link |
|----------|------------|
| **Notebook 1** — Data Preparation | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/ds_hanzala_saify/blob/main/notebook_1.ipynb) |
| **Notebook 2** — Sentiment Analysis | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_USERNAME/ds_hanzala_saify/blob/main/notebook_2.ipynb) |

> **Note:** Replace `YOUR_USERNAME` with your GitHub username after pushing to a public repo.

**Colab Setup:**
```python
# Run this cell first in Colab to upload data files
from google.colab import files
uploaded = files.upload()  # Upload CSV files from csv_files/
```

---

## Key Insights

### Finding 1: Sentiment Impacts Profitability
- **Statistical significance confirmed** via Mann-Whitney U test
- Median PnL differs measurably between Fear and Greed periods
- Implication: Sentiment should inform position sizing

### Finding 2: Leverage Risk is Asymmetric
- High leverage during Fear → 2-3x loss volatility vs. Greed
- Same leverage tier produces different outcomes based on sentiment
- Implication: Reduce leverage by 30-50% during Extreme Fear

### Finding 3: Contrarian Edge Exists
- Buying during Fear outperforms buying during Greed
- Win rate differential: 3-7% favoring contrarian approach
- Implication: Use Fear for entries, Greed for exits

### Finding 4: Trader Archetypes Are Real
- 4 distinct clusters identified via K-Means
- Retail "gamblers" cluster shows negative expected value
- Implication: Self-assess against winning cluster profiles

---

## Requirements

See [requirements.txt](requirements.txt) for full list:

```
pandas>=1.5.0
numpy>=1.23.0
matplotlib>=3.6.0
seaborn>=0.12.0
scipy>=1.9.0
scikit-learn>=1.1.0
ipykernel>=6.0.0
```

**Install:**
```bash
pip install -r requirements.txt
```

---

## Quick Start

```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/ds_hanzala_saify.git
cd ds_hanzala_saify

# Create virtual environment (recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Run notebooks in order
jupyter notebook notebook_1.ipynb
jupyter notebook notebook_2.ipynb
```

---

## Report

The full research report is available in `ds_report.md`. Convert to PDF using:

```bash
# Using pandoc
pandoc ds_report.md -o ds_report.pdf

# Or use VS Code's Markdown PDF extension
```

---

## License

Internal research document. Not for external distribution.

---

## Contact

**Hanzala Saify**  
Data Scientist

---

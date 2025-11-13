# Server Demand Forecasting for Video Game Research

## Project Overview

This project analyzes player session data from a MineCraft research server to forecast peak usage periods and optimize resource allocation. By understanding temporal patterns in player activity, we aim to predict server demand levels and provide actionable recommendations for resource provisioning.

## Research Question

**Can we accurately predict server demand peaks to optimize resource allocation for the MineCraft research server?**

Specifically, we:
1. Identify temporal patterns in player concurrency (hourly, daily, weekly)
2. Classify time periods into demand levels (low, medium, high)
3. Build a predictive model to forecast peak usage periods
4. Provide actionable recommendations for resource provisioning

## Dataset

The analysis uses two primary datasets:

### Players Dataset
- **Source**: `players.xlsx`
- **Description**: Player profiles and characteristics
- **Key Variables**: playerID, age, gender, country, experience_level, preferred_playstyle, account_creation_date

### Sessions Dataset
- **Source**: `sessions (2).xlsx`
- **Description**: Individual play sessions with timestamps
- **Key Variables**: sessionID, playerID, start_time, end_time, duration_minutes, server_region, game_mode, achievements_earned, disconnection_reason

## Methodology

### Data Processing
1. **Data Wrangling**: Parse timestamps, validate data integrity, engineer temporal features
2. **Feature Engineering**: Extract hour, day of week, weekend indicators, time periods
3. **Concurrent Player Calculation**: Compute hourly concurrent player counts as primary demand metric

### Exploratory Data Analysis
- Time series visualization of player demand
- Hourly and weekly pattern analysis
- Heatmap of demand by hour and day of week
- Distribution analysis for demand level classification

### Predictive Modeling
- **Algorithm**: K-Nearest Neighbors (K-NN) Classification
- **Target Variable**: Demand level (Low / Medium / High) based on tertile classification
- **Features**: Hour of day, day of week, weekend indicator
- **Evaluation**: Accuracy, precision, recall, F1-score, confusion matrix

## Key Findings

### Temporal Patterns
- **Peak Hours**: Server demand highest between 6 PM - 11 PM
- **Weekend Effect**: Distinct differences between weekend and weekday demand patterns
- **Cyclical Patterns**: Clear daily and weekly cycles in player activity

### Demand Distribution
- Right-skewed distribution with distinct demand tiers
- Tertile-based classification provides balanced demand categories
- High variability in peak demand periods

## Project Structure

```
LBYASM/
├── main.ipynb              # Complete analysis notebook with all sections
├── README.md               # This file - project documentation
├── players.xlsx            # Player profile data
├── sessions (2).xlsx       # Session activity data
├── players.csv             # Converted player data (generated)
├── sessions.csv            # Converted session data (generated)
└── commit_stages/          # Version control staging directory
    ├── stage1/             # Initial setup
    ├── stage2/             # Data loading and description
    ├── stage3/             # Data wrangling
    ├── stage4/             # Extended data wrangling
    ├── stage5/             # Question formulation and EDA
    └── stage6/             # Complete analysis with methods section
```

## Implementation Status

### Completed
- Data loading and quality assessment
- Data wrangling and feature engineering
- Exploratory data analysis with comprehensive visualizations
- Research question formulation
- Methodology design for K-NN classification
- Complete planning report with methods section

### Upcoming
- Feature preprocessing pipeline implementation
- K-NN model training and hyperparameter tuning
- Model evaluation on test set
- Prediction visualization and recommendations
- Final report and deployment guide

## Expected Impact

This forecasting model will enable the research group to:
- **Proactively allocate resources** during predicted high-demand periods
- **Schedule maintenance** during predicted low-demand windows
- **Optimize license costs** by understanding peak usage requirements
- **Improve player experience** by preventing server overload during peak times

## Requirements

### R Packages
```r
library(tidyverse)   # Data wrangling and visualization
library(readxl)      # Reading Excel files
library(lubridate)   # Date and time handling
library(class)       # K-NN implementation (upcoming)
library(caret)       # Model evaluation (upcoming)
```

## Usage

1. **Setup**: Ensure all required R packages are installed
2. **Data Preparation**: Place `players.xlsx` and `sessions (2).xlsx` in project root
3. **Run Analysis**: Execute `main.ipynb` sequentially from top to bottom
4. **Review Results**: Examine visualizations and statistical summaries

## Author

**Course**: Data Science Project
**Date**: November 2025
**Institution**: University Context (UBC Research Group)

## Repository

GitHub: https://github.com/ByronLi0207/DSI

## License

This project is for academic and research purposes.

## Acknowledgments

- UBC Research Group for providing the MineCraft server data
- PlaiCraft.ai platform for gameplay data collection

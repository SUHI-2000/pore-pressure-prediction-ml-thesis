# Comparative Analysis of Machine Learning-Driven Pore Pressure Prediction Models

![Status](https://img.shields.io/badge/status-research_complete-green)
![Language](https://img.shields.io/badge/language-Python-blue)
![Top Model](https://img.shields.io/badge/champion_model-XGBoost-brightgreen)

This repository contains the complete thesis and associated code for my final year research project at the University of Moratuwa, titled "Comparative Analysis of Machine Learning-Driven Pore Pressure Prediction Models."

The full research thesis is available in the `/report` directory.

## Abstract
Accurate pore pressure prediction is critical for maintaining a safe mud weight window during drilling operations. This research addresses the limitations of conventional methods by employing a data-driven machine learning approach. The core of this study is a systematic investigation into the interplay between data preprocessing strategies and the performance of various ML algorithms. By testing six models across four distinct preprocessing scenarios, this work moves beyond a simple model-to-model comparison to identify the optimal end-to-end pipeline for this geomechanical challenge. The results conclusively show that a **Tuned XGBoost model, trained on raw, unprocessed data, achieves the highest predictive accuracy (R² = 0.9789)**, challenging conventional assumptions about the universal necessity of extensive data preprocessing for advanced ensemble models.

## The Research Gap & Experimental Design
The existing literature often applies a fixed preprocessing pipeline without systematically testing its impact on different types of ML models. This research addresses that gap by implementing a rigorous **four-scenario experimental design** to isolate the effects of outlier treatment and feature selection.

The four scenarios analyzed were:
1.  **Scenario 1: Full Preprocessing** (Outlier Capping + Feature Selection)
2.  **Scenario 2: Feature Selection Only** (Models trained on raw data with multicollinear features removed)
3.  **Scenario 3: Outlier Capping Only** (Models trained on the full feature set after outliers were capped)
4.  **Scenario 4: Raw Data** (A "stress test" where models were trained on completely unprocessed data)

## Key Findings
1.  **Champion Algorithm:** A **Tuned XGBoost** model consistently outperformed other algorithms, demonstrating its robustness and power in capturing complex, non-linear relationships in petrophysical data.
2.  **Preprocessing is Context-Dependent:** The optimal data preparation strategy is not universal.
    - **Feature Selection:** Removing linearly correlated features was found to be **detrimental** to the performance of advanced models like XGBoost and Random Forest, which were capable of extracting unique non-linear information from the full feature set.
    - **Outlier Capping:** While critical for sensitive models like Support Vector Regression (SVR), it was unnecessary and even slightly harmful for robust ensemble models like XGBoost.
3.  **Optimal Pipeline:** The best-performing pipeline was the simplest: applying a **Tuned XGBoost model directly to the raw, complete dataset (Scenario 4)**.

## Repository Structure
```
├── code/
│   ├── Scenario_1_Full_Preprocessing.ipynb   # Jupyter Notebook for Scenario 1
│   ├── Scenario_2_Feature_Selection_Only.ipynb # Jupyter Notebook for Scenario 2
│   ├── Scenario_3_Outlier_Capping_Only.ipynb # Jupyter Notebook for Scenario 3
│   └── Scenario_4_Raw_Data.ipynb             # Jupyter Notebook for Scenario 4
├── report/
│   └── Thesis_Pore_Pressure_Prediction_ML.pdf # The full research thesis document
├── README.md
└── LICENSE.md
```

## How to Use This Repository
- **Read the Thesis:** For a full understanding of the literature review, methodology, and detailed discussion, please refer to the PDF in the `/report` folder.
- **Explore the Code:** The Jupyter Notebooks in the `/code` folder contain the complete Python implementation for each of the four experimental scenarios. They can be viewed directly on GitHub or downloaded and run in an environment like Google Colab, JupyterLab, or VS Code.

## License
Copyright (c) 2024 S. Suheerman, M.N.M. Naweed, S.M.D.K.R. Dilkushan. All Rights Reserved.

This work is protected by copyright. For permissions to use, copy, or distribute this material, please contact the authors. See the [LICENSE.md](LICENSE.md) file for more details.

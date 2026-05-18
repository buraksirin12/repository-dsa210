# Predicting Road Network Failure Probabilities for Post-Disaster Drone Routing

## Overview
This repository contains the complete data science pipeline (data collection, exploratory data analysis, hypothesis testing, and machine learning) for the DSA210 Introduction to Data Science course project. The goal of this project is to develop a data-driven model to predict the failure probabilities of road segments (arcs) in a transportation network following a disaster, specifically focusing on the Caferağa (Moda) neighborhood in the Kadıköy district of Istanbul.

## Repository Structure
* `data/`: Contains the `.geojson` files extracted from OpenStreetMap (edges, nodes, and building footprints).
* 'DSA210_Project_EDA.ipynb': The main Jupyter Notebook containing all Python code for data fetching, spatial joining, EDA, and statistical testing.
* `DSA210_Project_EDA_afterfeedback.ipynb`: The Jupyter Notebook containing data fetching, spatial joining, enhanced visualizations, and formal statistical Hypothesis Testing.
* `DSA210_Project_EDA_and_ML.ipynb`: The Jupyter Notebook containing the Machine Learning modeling (K-Means Clustering and Random Forest Regression).
* `requirements.txt`: List of Python dependencies required to run the analysis.
* `Project_proposal.pdf`: The initial project proposal document.
* `Final_Report.pdf` (or `.md`): The comprehensive final report detailing the methodology, results, and conclusions.

## How to Run the Code
1. Clone this repository to your local machine.
2. Install the required dependencies using:
   `pip install -r requirements.txt`
3. Open the Jupyter Notebooks in Google Colab or your local Jupyter environment. Run the cells sequentially. The data files will be loaded locally from the `data/` directory.

## Methodology & Results
**Data Collection & Enrichment:** Successfully fetched road network data and building footprints for Caferağa using `osmnx`. Performed a spatial join to calculate the `building_count` and `structural_density` for each road segment.
**Hypothesis Testing:** Conducted Pearson Correlation, Independent T-Tests, and One-Way ANOVA to statistically validate the relationship between road length, building count, and structural density.
**Machine Learning:** * Applied **K-Means Clustering** to segment the network into High, Medium, and Low-Risk profiles.
* Trained a **Random Forest Regressor** to predict continuous road vulnerability scores, achieving an $R^2$ score of ~0.72, proving that building count and structural density are strong predictors of potential debris blockage.

## Deviations from the Initial Proposal
1. **Dataset Size:** While the proposal targeted 1,000-5,000 segments, the final analysis focuses on the Caferağa (Moda) neighborhood, resulting in 332 road segments. This specific neighborhood was selected as a high-density "pilot area" to ensure high-quality spatial analysis and structural density calculations.
2. **External Data Integration:** The integration of seismic risk maps (PGA values) was initially planned. However, due to formatting challenges and API access limitations, the "enrichment" requirement was successfully fulfilled by extracting and spatially joining building footprints to the road network to create the `structural_density` metric.

## AI Usage Statement
**Mandatory Disclosure:** AI tools (Google Gemini) were used during the development of this project for educational and debugging purposes.
**Specific Prompts Used:** Prompts such as "How can I spatially join building polygons to road line strings using geopandas?", "Help me fix the AttributeError: module 'osmnx' has no attribute 'geometries_from_place'", and requests to translate code comments into English, format statistical hypothesis structures, and structure the final report.
**Outputs Generated:** The AI assisted in refactoring the `geopandas` buffer logic, fixing deprecated `osmnx` function names, generating boilerplate `matplotlib`/`seaborn` code, and drafting report outlines. All final code logic, methodology, statistical interpretations, and model architectures were reviewed, tested, assembled, and directed by me.

**Author:** Adil Burak Şirin
**Student ID:** 35561

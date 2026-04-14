# Predicting Road Network Failure Probabilities for Post-Disaster Drone Routing

## Overview
This repository contains the data collection, exploratory data analysis (EDA), and hypothesis testing phase for the DSA210 Introduction to Data Science course project. [cite_start]The goal of this project is to develop a data-driven model to predict the failure probabilities of road segments (arcs) in a transportation network following a disaster, specifically focusing on the Kadıköy district in Istanbul[cite: 56, 66].

## Repository Structure
* `data/`: Contains the `.geojson` files extracted from OpenStreetMap (edges, nodes, and building footprints).
* `DSA210_Project_EDA.ipynb`: The main Jupyter Notebook containing all Python code for data fetching, spatial joining, EDA, and statistical testing.
* `requirements.txt`: List of Python dependencies required to run the analysis.
* `Project proposal.pdf`: The initial project proposal document.

## How to Run the Code
1. Clone this repository to your local machine.
2. Install the required dependencies using:
   `pip install -r requirements.txt`
3. Open `DSA210_Project_EDA.ipynb` in Google Colab and run the cells sequentially. The data files will be loaded locally from the `data/` directory.

## Current Progress (Until April 14 Deadline)
* **Data Collection:** Successfully fetched road network data (drive network) and building footprints for Caferağa, Kadıköy using `osmnx`.
* **Enrichment:** Performed a spatial join (20-meter buffer) to calculate the "structural density" (building count per road segment) for each road.
* **EDA:** Visualized the distribution of building counts and the relationship between road length and building density.
* **Hypothesis Testing:** Conducted a Pearson correlation test showing a statistically significant relationship (p < 0.05) between road length and building count. 

## AI Usage Statement
**Mandatory Disclosure:** AI tools (Google Gemini) were used during the development of this project for educational and debugging purposes.
* **Specific Prompts Used:** Prompts such as "How can I spatially join building polygons to road line strings using geopandas?", "Help me fix the AttributeError: module 'osmnx' has no attribute 'geometries_from_place'", and requests to translate code comments into English were used.
* **Outputs Generated:** The AI assisted in refactoring the `geopandas` buffer logic, and fixing deprecated `osmnx` function names. All final code logic was reviewed, tested, and assembled by me.

---
**Author:** Adil Burak Şirin
**Student ID:** 35561

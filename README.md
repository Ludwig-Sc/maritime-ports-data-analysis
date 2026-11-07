# Global Maritime Ports & Vessel Traffic Analysis

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-150458?style=flat&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Folium](https://img.shields.io/badge/Folium-Geospatial_Mapping-77B829?style=flat&logo=leaflet&logoColor=white)](https://python-visualization.github.io/folium/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Institution: TechAcademy](https://img.shields.io/badge/TechAcademy-Goethe_University_Frankfurt-002B49?style=flat)](https://tech-academy.io/)

A data science case study analyzing global maritime shipping infrastructure, vessel traffic volume, commodity flows, and geospatial distribution. Completed as part of the **TechAcademy e.V. Data Science with Python** program at **Goethe University Frankfurt**.

---

## Executive Summary

Maritime ports serve as the critical nodes of global supply chains. This project investigates international port data to quantify vessel traffic, evaluate maritime import/export shares, identify domestically dominant shipping hubs, and visualize global maritime networks interactively.

### Key Objectives
- **Data Ingestion & Cleaning**: Process and sanitize irregular port records, strip unit artifacts, convert string percentage metrics into numeric features, and resolve coordinate discrepancies.
- **Data Integration**: Merge relational port attributes with geospatial coordinate tables based on standardized port identifiers.
- **Traffic & Capacity Analysis**: Rank top global ports by total vessel count and analyze cargo specializations across liquid bulk, dry bulk, container, and general cargo.
- **Domestic Significance**: Model and segment ports by domestic cargo dominance relative to their respective national maritime totals.
- **Geospatial Mapping**: Build interactive global maps mapping port coordinates, throughput categories, and primary industrial sectors.

---

## Project Structure

```text
maritime-ports-data-analysis/
├── data/
│   ├── Ports.csv                  # Global maritime port statistics & throughput
│   └── geographical_location.csv  # Port coordinate mappings (latitude & longitude)
├── notebooks/
│   └── maritime_ports_analysis.ipynb # End-to-end data analysis notebook
├── requirements.txt               # Dependency environment specification
├── .gitignore                     # Git ignore rules
├── LICENSE                        # MIT License
└── README.md
```

---

## Data Pipeline & Analysis Workflow

1. **Exploratory Data Inspection**: Initial inspection of feature schemas, missing values, and data type alignment across raw tables (`Ports.csv` and `geographical_location.csv`).
2. **Data Cleaning & Type Casting**:
   - Replaced irregular missing value placeholders (`nan`, whitespace).
   - Cleaned percentage strings (`share_country_maritime_import`, `share_country_maritime_export`) into floating-point ratios.
   - Standardized textual naming conventions.
3. **Reshaping & Merging**:
   - Reshaped multi-column cargo statistics into normalized long-form tables.
   - Parsed combined port and country name strings.
   - Executed inner joins on geographical coordinate tables.
4. **Traffic Analysis & Ranking**:
   - Filtered and ranked leading ports by annual vessel traffic.
   - Broken down vessel counts by vessel category (container vessels, tankers, bulk carriers).
5. **Domestic Significance Classification**:
   - Evaluated domestic maritime shares to classify ports into hub versus regional gateways.
6. **Geospatial Visualization**:
   - Mapped coordinates using interactive maps with scaled markers representing vessel counts and color-coded industrial sectors.

---

## Quickstart & Installation

### 1. Clone the Repository
```bash
git clone https://github.com/Ludwig-Sc/maritime-ports-data-analysis.git
cd maritime-ports-data-analysis
```

### 2. Set Up Virtual Environment
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Run the Jupyter Notebook
```bash
jupyter lab notebooks/maritime_ports_analysis.ipynb
```

---

## Technologies Used

- **Python 3.10+**: Core programming language.
- **Pandas & NumPy**: Data ingestion, cleaning, transformation, and numerical aggregation.
- **Matplotlib & Seaborn**: Statistical charting and distribution plots.
- **Folium & Plotly**: Geospatial visualization and interactive mapping.

---

## Author & Academic Context

Developed by **Ludwig Schmiedler** as part of the Data Science with Python curriculum at **TechAcademy e.V.** in collaboration with **Goethe University Frankfurt**.
- GitHub: [@Ludwig-Sc](https://github.com/Ludwig-Sc)
- Repository: [maritime-ports-data-analysis](https://github.com/Ludwig-Sc/maritime-ports-data-analysis)

# agriculture_in_federal_districts
Analysis of agriculture indicators among Russian Federal Districts
# Grain Sector of Russia (2016)

Analysis and comparative visualization of key grain crop metrics — sown areas, gross harvest volumes, and productivity across Russian federal districts using official Rosstat data.

---

## Overview

This project analyzes the territorial distribution and productivity of five major grain crops in the Russian Federation under the 2016 harvest. The analysis compares sown areas, production volumes, and calculated output per hectare across all eight federal districts.

### Studied Crops:
- **Wheat** (winter and spring combined)
- **Rye**
- **Oats**
- **Rice**
- **Barley**

---

## Data Sources & Methodology

The analysis combines two official datasets published by Rosstat:

1. **Sown Area (`sown_area_ha.xlsx`)**:
   - Source: All-Russian Agricultural Census 2016 (*VSXP-2016*, Vol. 4, Book 1).
   - Metric: Sown area under the 2016 harvest across all farm categories.
   - Unit: **Hectares (ha)**.

2. **Gross Harvest (`crop_production_thous_cwt.xlsx`)**:
   - Source: Rosstat annual crop production statistics (2016).
   - Metric: Gross harvest volume across all farm categories.
   - Unit: **Thousand centners (thous. cwt / тыс. ц)**.

### Productivity Calculation

Since $1 \text{ thousand centners} = 1{,}000 \text{ centners}$ (or $100 \text{ metric tons}$), the crop productivity (output per hectare) is computed as follows:

$$\text{Productivity (cwt/ha)} = \frac{\text{Harvest (thous. cwt)} \times 1{,}000}{\text{Sown Area (ha)}}$$

---

## Features & Visualizations

The core script in `MainCode.ipynb` generates:
- **Grouped Bar Charts**:
  - Comparison of sown areas across federal districts;
  - Comparison of gross harvest using a logarithmic scale (to handle order-of-magnitude differences between wheat and specialty crops like rice);
  - Comparison of calculated productivity ($cwt/ha$).
- **Readable Axis Labels**: District names are automatically stripped of the repetitive `"федеральный округ"` suffix to avoid label overlapping.

---

## Project Structure

```text
Grain-sector-of-Russia/
├── MainCode.ipynb                 # Main Jupyter Notebook with data processing and plots
├── sown_area_ha.xlsx              # Sown area by district and crop (ha)
├── crop_production_thous_cwt.xlsx # Gross harvest by district and crop (thous. cwt)
└── README.md                      # Project documentation
```

---

## Quickstart & Requirements

### Prerequisites
- Python 3.9+
- Jupyter Notebook / JupyterLab

### Dependencies
Install the required packages:
```bash
pip install pandas numpy matplotlib openpyxl
```

### Running the Notebook
Clone the repository and launch JupyterLab:
```bash
git clone [https://github.com/basil-shnol/Grain-sector-of-Russia.git](https://github.com/basil-shnol/Grain-sector-of-Russia.git)
cd Grain-sector-of-Russia
jupyter lab MainCode.ipynb
```

# plp-da-a2-rainfall-advisory
# Rainfall Analysis and Planting Advisory

**Author:** Rosalind Nduta Muturi
**Cohort:** 1 Million Devs, Advanced Data Analytics with Python

## Project summary

A farmer-support NGO sends SMS advice on planting windows in five counties (Nairobi, Nakuru, Kisumu, Mombasa and Machakos). This project cleans a hand-typed Machakos rainfall record (invalid values are caught with `except ValueError` and imputed with the rounded mean), combines all counties into a 5 × 12 NumPy array, and uses vectorised NumPy operations to find annual totals, monthly averages, the wettest month, dry months (below 50 mm) and the best two-month planting window for each county. Results are written to `rainfall_summary.csv` with the `csv` module.

## Files

| File | Purpose |
|---|---|
| `rainfall_analysis.ipynb` | Cleaning, NumPy analysis, CSV export, advisory and data quality notes |
| `rainfall_summary.csv` | One row per county: `county, annual_total_mm, wettest_month, dry_months, planting_window` |
| `requirements.txt` | Python libraries used (NumPy) |

## How to run the notebook

1. Install Python 3.9 or newer.
2. Install the dependencies and Jupyter:
   ```
   pip install -r requirements.txt
   pip install notebook
   ```
3. Start Jupyter and open the notebook:
   ```
   jupyter notebook rainfall_analysis.ipynb
   ```
4. Choose **Kernel → Restart & Run All**. The notebook regenerates `rainfall_summary.csv` in the same folder.

## Planting advisory

- In Nairobi, Nakuru, Kisumu and Mombasa, plant in **April–May**, which is the wettest two-month window in all four counties.
- In drier Machakos (six months below 50 mm), plant in **November–December** during the short rains.
- Machakos April and September readings were missing and had to be estimated (68 mm), so the Machakos advice should be confirmed against the station's original records.

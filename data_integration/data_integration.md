## Data Integration

The final dataset was created by integrating three cleaned sports datasets: one for the NFL, one for the NBA, and one for MLB.

### Input Files

The following cleaned CSV files were used as input:

| League | File Name |
|---|---|
| NFL | `nfl_cleaned.csv` |
| NBA | `nba_cleaned.csv` |
| MLB | `mlb_cleaned.csv` |

These files were cleaned before integration so that their column names and formats matched as closely as possible.

### Integration Script

The datasets were integrated using Python in a Jupyter Notebook / VSCode environment. The main Python package used for integration was `pandas`. The group_by for integrating the dataset was mentioned in the visualization, and you can find the code in data_visualizations/Visualizations.ipynb.

```python
import pandas as pd

nfl = pd.read_csv("nfl_cleaned.csv")
nba = pd.read_csv("nba_cleaned.csv")
mlb = pd.read_csv("mlb_cleaned.csv")

datasets_merged = pd.concat([nfl, nba, mlb], ignore_index=True)

datasets_merged.to_csv("city-sports-merged.csv", index=False)

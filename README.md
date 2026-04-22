# Missing Lightning Data EDA

This project explores missing geographic data in lightning strike datasets using Python. The analysis combines two datasets, identifies records with missing location attributes, and uses geospatial visualization to understand where those missing values occur.

## Project overview

The notebook investigates missing data related to lightning strikes by:

- loading and comparing two datasets
- merging them into a single DataFrame
- identifying rows with missing geographic information
- isolating records with missing state, city, and ZIP-related attributes
- grouping missing observations by latitude and longitude
- visualizing the locations of missing records on a map
- interpreting whether the missing values are expected or potentially problematic

## Key question

Why are so many rows missing state and ZIP code data after merging the datasets?

## Tools used

- Python
- Pandas
- NumPy
- Seaborn
- Matplotlib
- Plotly
- Jupyter Notebook

## Dataset structure

The project uses two datasets:

- `eda_missing_data_dataset1.csv`
- `eda_missing_data_dataset2.csv`

These datasets are joined using shared geographic and date fields in order to investigate missing values in the merged result.

## Analysis workflow

### 1. Load and inspect the datasets
Both datasets are loaded into pandas DataFrames and reviewed using methods such as `head()`, `shape`, and `describe()`.

### 2. Merge the data
The datasets are merged using a left join on:

- `date`
- `center_point_geom`

This keeps all rows from the first dataset and adds matching location-related fields from the second dataset when available.

### 3. Identify missing geographic data
Rows with missing `state_code` values are isolated to create a subset of records with incomplete geographic information.

### 4. Summarize missing locations
The missing rows are grouped by latitude and longitude, and the number of lightning strikes is aggregated for each location.

### 5. Visualize the missing data
Plotly is used to build a geographic scatter plot showing where the missing records are concentrated. The visualization is shown at both a broader geographic level and scaled to the United States.

## Key findings

The map-based analysis shows that many records with missing state and ZIP code data are not actually data-entry errors. A large share of these lightning strikes occurred over water or outside the United States, including areas such as:

- the Atlantic Ocean
- the Gulf of Mexico
- the Caribbean Sea
- the Great Lakes
- Mexico
- Cuba
- the Bahamas

Because these locations do not correspond to valid U.S. ZIP codes or state codes, the missing values are often expected. However, some missing records appear within the United States, which may justify further review with the data owner.

## Files

- `missing-lightning-data.ipynb` — main notebook with the analysis
- `eda_missing_data_dataset1.csv` — first dataset
- `eda_missing_data_dataset2.csv` — second dataset

## How to run

1. Clone the repository
2. Open the notebook in Jupyter Notebook or JupyterLab
3. Make sure both CSV files are in the same folder as the notebook
4. Install required packages if needed:
   - pandas
   - numpy
   - seaborn
   - matplotlib
   - plotly
5. Run the notebook cells in order

## Project goal

The goal of this project is to demonstrate practical exploratory data analysis and missing-data investigation in Python. It shows how merging, filtering, grouping, and geospatial visualization can help explain why missing values appear in a dataset and whether they represent real quality issues.

## Author

Evgeny

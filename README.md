# Coffee Shop Sales & Weather Analysis

This project combines transaction data from a fictional coffee shop, Maven Roasters, with historical NYC weather data to explore trends and patterns that may impact sales. The final dataset is saved in **Parquet format** for efficient downstream analysis and visualization.

---

## Project Structure
<pre><code class="lang-txt">
├── LICENSE
├── README.md
├── data
│ ├── Coffee Shop Sales.csv # Original sales transaction data
│ ├── NYC.csv # NYC weather data (from Mesonet)
│ └── sales_weather # Cleaned, merged dataset in Parquet format
│ ├── _SUCCESS
│ └── file.snappy.parquet
├── process.ipynb # PySpark notebook for processing the data
└── requirements.txt # Required Python packages
</code></pre>

---

## What the Notebook Does

The notebook `process.ipynb` performs the following tasks using PySpark:

1. **Load Data**  
   - Reads the coffee shop sales and weather data into PySpark DataFrames.

2. **Data Cleaning**  
   - Checks for and fills null values with `0`.
   - Drops irrelevant columns not needed for analysis.

3. **Data Merging**  
   - Joins the sales and weather data on a matching timestamp.

4. **Save Output**  
   - Writes the merged dataset to disk in **Parquet** format for efficient storage and processing.

---

## Data Sources

- **Coffee Sales**: Fictitious data from Maven Roasters (via [Kaggle Dataset](https://www.kaggle.com/datasets/ahmedabbas757/coffee-sales))
- **NYC Weather**: Downloaded via [Iowa State Mesonet](https://mesonet.agron.iastate.edu/request/download.phtml?network=NY_ASOS)

---

## Requirements

Ensure you have PySpark and supporting packages installed. You can install dependencies via:

```bash
pip install -r requirements.txt
```

---
## Output
The merged and cleaned dataset is saved in data/sales_weather/ as a .parquet file, which can be used for further analysis or loaded into BI tools like Apache Superset, Metabase, or Power BI.
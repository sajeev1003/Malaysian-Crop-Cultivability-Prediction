# Malaysian Crop Cultivability Prediction

An academic machine-learning project that combines Malaysian district-level crop production, planted-area, and weather data to explore crop production patterns and build a binary crop-classification model.

The complete analysis is contained in `Machine_Learning.ipynb`. It covers data cleaning, integration, exploratory analysis, feature engineering, preprocessing, model tuning, and model comparison.

## Project objectives

- Integrate crop production, planted-area, and district weather datasets.
- Explore the relationship between weather conditions and crop production.
- Compare production across crop types and species.
- Engineer a binary `Cultivable` label from recorded production.
- Train and tune several classification algorithms.
- Compare the models using AUC, accuracy, precision, recall, and F1 score.

## Included files

| File | Description |
| --- | --- |
| `Machine_Learning.ipynb` | Original Google Colab/Jupyter notebook containing the complete analysis and stored outputs. |
| `crops_district_production.csv` | District-level crop production records. |
| `crops_district_area.csv` | District-level planted-area records. |
| `Reordered_Weather_Data.csv` | District weather measurements used during data integration. |

## Analysis workflow

1. Inspect and clean the crop production data.
2. Merge production records with district weather data.
3. Merge the resulting table with planted-area data.
4. Treat missing values, duplicates, inconsistent labels, and numerical outliers.
5. Create average temperature and the binary `Cultivable` target.
6. Perform exploratory analysis of temperature, crop type, crop species, and production.
7. Split the data into training and testing sets.
8. Encode categorical variables, examine class imbalance, and perform feature selection.
9. Tune and compare Logistic Regression, KNN, Random Forest, LightGBM, CatBoost, and XGBoost.

The stored notebook output identifies the tuned Random Forest as the best model by AUC, with a reported AUC of **0.8794** for the original experimental setup.

## Running the notebook in Google Colab

The original notebook uses Google Drive paths. To run it without modifying the code:

1. Upload these three CSV files to the root of **My Drive**:
   - `crops_district_production.csv`
   - `Reordered_Weather_Data.csv`
   - `crops_district_area.csv`
2. Upload and open `Machine_Learning.ipynb` in Google Colab.
3. Select **Runtime → Run all**.
4. Approve Google Drive access when prompted.

The notebook creates intermediate merged files named `merged_crop_weather_data_final.csv` and `merged_df_with_planted_area.csv` in My Drive.

## Main Python libraries

- pandas and NumPy
- Matplotlib, Seaborn, and Plotly
- scikit-learn
- imbalanced-learn
- XGBoost
- LightGBM
- CatBoost
- statsmodels

If Colab reports that a package is missing, install it in a new cell using `!pip install package-name`, then rerun the affected cells.

## Important interpretation notes

- The notebook defines `Cultivable = 1` when recorded production is greater than zero. This represents an observed production outcome and should not be interpreted as proof of inherent soil or land suitability.
- The datasets represent a single reporting period, so the results do not establish performance across different years.
- The source files contain repeated district–crop keys. Any production deployment should validate aggregation and merge cardinality against the original data documentation.
- The notebook is preserved as the original academic workflow. Additional validation would be required before using its predictions for agricultural decisions.

## Author

Sajeev Jayaparagasam — personal academic machine-learning project.

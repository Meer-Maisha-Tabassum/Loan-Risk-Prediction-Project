# Loan Risk Prediction

## Project Overview

This project leverages various advanced techniques for loan risk prediction, focusing on data quality, causality, and explainability. Using ydata-profiling, comprehensive reports were generated to assess data quality and facilitate exploratory data analysis (EDA). Granger causality analysis identified significant predictors of loan status, informing feature selection. The DoWhy library was used to build causal models, distinguishing true causative effects from correlations and providing valuable insights for loan risk management. Explainable AI was integrated with a Decision Tree classifier to enhance transparency and trustworthiness in model decisions.

-----

## Project Content

1.  **Import Necessary Libraries**
2.  **Data Preparation and Exploration**
      * 2.1 Identifying Null Values
      * 2.2 Handle Null values
      * 2.3 Handle Date Columns
      * 2.4 Handle Boolean Features
      * 2.5 Target Variable Defining
      * 2.6 Handling Rest of the Missing Values Before Encoding
      * 2.7 Feature Importance
      * 2.8 Feature Selection
3.  **Data Visualization**
4.  **Granger Causality Matrix**
      * 4.1 Matrix
      * 4.2 Matrix Visualization
      * 4.3 Feature Significance from Granger Causality
5.  **Causal AI Analysis with DoWhy Library**
      * 5.1 Positive Causal Effect
      * 5.2 Negative Causal Effect
6.  **Data Splitting**
7.  **Sensible Model Training**
8.  **Model Visualization and Evidence**
9.  **Predicted Loan Risk on an Applicant**
10. **Explainable AI**
      * 10.1 Classification Report
      * 10.2 Tree Diagram
11. **Model Validation**

-----

## Installation

To run this notebook, you need to have Python and the following libraries installed. You can create a `requirements.txt` file with the following content:

```text
warnings
pandas
numpy
scikit-learn
scipy
ydata-profiling
matplotlib
seaborn
causallearn
dowhy
networkx
statsmodels
concurrent-futures
```

Then, install the dependencies by running the following command in your terminal:

```bash
pip install -r requirements.txt
```

-----

## Usage

1.  Clone the repository:
    ```bash
    git clone https://github.com/your-username/loan-risk-prediction.git
    cd loan-risk-prediction
    ```
2.  Place the datasets (`loan.csv`, `payment.csv`, `clarity_underwriting_variables.csv`) in the root directory.
3.  Launch Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
4.  Open `Loan Risk Prediction.ipynb` and run the cells.

-----

## Data

This project uses three datasets:

  * `loan.csv`: Contains information about the loan applications.
  * `payment.csv`: Contains payment history for the loans.
  * `clarity_underwriting_variables.csv`: Contains underwriting variables from Clarity.

These datasets are merged to create a comprehensive dataset for analysis.

-----

## Methodology

### Data Preparation and Exploration

The initial phase involves extensive data preparation and cleaning. This includes:

  * **Handling Null Values**: Columns with a high percentage of missing values (threshold \> 55%) are dropped. Remaining nulls in numerical columns are imputed with the mean, and categorical columns are filled with a 'missing' placeholder before being label encoded.
  * **Handling Date Columns**: Date columns are identified, converted to datetime objects, and then transformed into numerical timestamps.
  * **Handling Boolean Features**: Boolean values are converted to integers (0 and 1).
  * **Feature Importance & Selection**: A RandomForestClassifier is used to determine the importance of each feature. The top 20 most important features are selected for the final model to improve efficiency and accuracy.

### Data Visualization

ydata-profiling is used to generate a comprehensive EDA report, providing statistics, distributions, and correlations for all features. This helps in understanding the data and identifying potential issues.

### Granger Causality and Causal AI

  * **Granger Causality**: A Granger causality matrix is computed to identify predictive relationships between time series variables.
  * **Causal AI with DoWhy**: The DoWhy library is employed to build causal models to distinguish true causative effects from mere correlations, providing deeper insights for risk management.

### Modeling and Explainable AI

  * **Model Training**: A Decision Tree classifier is trained on the reduced dataset.
  * **Explainable AI (XAI)**: The model's decisions are made transparent and interpretable using techniques like classification reports and tree diagrams.

-----

## Results

The project culminates in a validated loan risk prediction model. The use of explainable AI ensures that the model's predictions are not only accurate but also understandable, which is crucial for making trustworthy financial decisions. The final model's performance is evaluated using various metrics and visualizations.

-----

## Contributing

Contributions are welcome\! Please feel free to submit a pull request.

-----

## License

This project is licensed under the MIT License.

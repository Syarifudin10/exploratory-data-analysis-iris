# Exploratory Data Analysis (EDA) for Iris Species Classification

## Executive Summary:

Building accurate classification models requires a deep understanding of feature importance. In this project, I performed a comprehensive Exploratory Data Analysis (EDA) on the Iris dataset using Python, Pandas, and Seaborn. The analysis revealed that **Petal dimensions (Length & Width)** are the strongest predictors for distinguishing species, while Sepal dimensions offer weak separability. Based on these findings, I recommend utilizing Petal features for future Machine Learning modeling and addressing the high multicollinearity detected between them to optimize model performance.

### Problem Statement: 

In data science classification tasks, using all available features without analysis can lead to model overfitting and inefficiency. We need to determine which biological features (Sepal vs. Petal) provide the distinct signal required to accurately classify the three Iris species (*Setosa, Versicolor, Virginica*). How can we identify the most impactful features and detect potential data quality issues before modeling?

![Dashboard/Main Visual](C:\Users\ahmad\OneDrive\Documents\Learn Data Analysis\Codveda)


### Methodology: 

1. **Data Ingestion & Cleaning:** Using **Pandas** to load the dataset, check for missing values, duplicates, and ensure data types were correct. Verified class balance to ensure no bias.

2. **Univariate Analysis:** Created histograms and boxplots using **Seaborn** to understand the distribution of each feature and detect outliers.

3. **Multivariate Analysis:** Developed scatter plots and pair plots to visualize relationships between features and identify clusters per species.

4. **Correlation Analysis:** Generated a heatmap to quantify the linear relationships between variables and detect multicollinearity.

### Skills:

**Python:** Pandas, NumPy (Data Manipulation)

**Data Visualization:** Matplotlib, Seaborn (Statistical Graphics)

**Statistical Analysis:** Correlation coefficients, Distribution analysis, Outlier detection

### Results & Insights: 

By visualizing the data distributions and relationships, I provided clear evidence on which features matter most. The analysis saved potential modeling time by identifying that Sepal Width is a poor predictor. Key findings include:

* **Distinct Separation:** *Iris Setosa* is linearly separable from the other two species using Petal Length alone.
* **The "Petal" Power:** Petal Length and Width showed the clearest distinction between clusters, whereas Sepal Width resulted in heavy overlap.
* **Multicollinearity:** A very high correlation (**0.96**) was found between Petal Length and Petal Width, suggesting redundancy.
* **Outliers:** Minor outliers were detected in Petal Length but deemed as natural biological variation.

![Correlation Heatmap](C:\Users\ahmad\OneDrive\Documents\Learn Data Analysis\Codveda)


### Recommendations: 

Based on the data insights, I recommend the following for the modeling phase:

1.  **Feature Selection:** Prioritize **Petal Length** and **Petal Width** as the primary input features.
2.  **Model Choice:** Since *Versicolor* and *Virginica* have some overlap, non-linear models like **Decision Trees** or **KNN** may perform better than simple linear models.
3.  **Dimensionality Reduction:** Due to the 0.96 correlation between petal features, consider dropping one if using linear regression to avoid instability, or keep both for tree-based models.

### Next Steps: 

1.  Build a **Decision Tree Classifier** to benchmark accuracy using only Petal features.
2.  Perform cross-validation to ensure the model generalizes well on the overlapping classes.
3.  Develop a simple interactive dashboard (Streamlit) to demonstrate the classification in real-time.

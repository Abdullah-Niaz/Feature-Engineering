## What is Feature Engineering?

Feature engineering is the process of extracting meaningful features from raw data. These features can significantly improve the performance of machine learning algorithms.
Features are the attributes or columns in a dataset.

![FeaturesEng](Images/FeaturesEng.png)
![FeaturesEng GeeksforGeeks](Images/FeatureEng1.png)

---

## Categorized Feature Engineering

* **Feature Transformer & Imputation**

  * Missing Value Imputation
  * Handling Categorical Features
  * Outlier Detection
  * Feature Scaling
* **Feature Construction**
* **Feature Selection**
* **Feature Extraction**

---

## Feature Transformer & Imputation

### Missing Value Imputation

Sometimes, while collecting data, there may be missing values due to errors or omissions by data collectors.
Libraries like `sklearn` do not work with missing values during model training, so it is important to handle them beforehand.

You can either remove the missing values or fill them using statistical methods like mean, median, or mode.
You can also use advanced techniques like `SimpleImputer` or `KNNImputer` for imputation.

---

### Handling Categorical Values

Categorical values are non-numeric values such as gender, color, etc.
Libraries like `sklearn` require numerical inputs for model training, so categorical features need to be converted.

You can convert categorical values into numerical form using techniques like:

* **Label Encoding**
* **One-Hot Encoding**

---

### Outlier Detection

Outliers are data points that differ significantly from other observations, such as a salary of 1000 in a dataset where most salaries are in the range of 10–100.

Some algorithms are sensitive to outliers, which can negatively impact model performance.
Hence, detecting and handling outliers is a crucial step in feature engineering.

---

### Feature Scaling

Feature scaling is the process of transforming features to lie within a specific range, usually between 0 and 1.

This step is important because some machine learning algorithms are sensitive to the scale of features.
For instance, a feature representing **age** might range from 20–60, while a **salary** feature might range from 10,000–100,000.
In such cases, the model may give undue importance to the larger-valued feature unless scaling is applied.


---

## Feature Construction

Feature construction is the process of creating new features from the existing ones in the dataset to improve model performance.

**Why it's important:**

* Raw data may not always provide all the useful patterns needed for a model to learn.
* Constructed features can capture hidden relationships or domain-specific insights.

**Examples:**

* Creating a **BMI** feature using `weight / height²` from existing `weight` and `height` columns.
* Extracting **day, month, year** from a single `date` column.
* Combining `first_name` and `last_name` to create a `full_name` feature.
* From a `timestamp`, creating features like `is_weekend`, `hour_of_day`, etc.

**Tools/Libraries:**
You can manually create features using Python or use tools like:

* `Feature-engine`
* `Featuretools` (for automated feature construction)

---

## Feature Selection

Feature selection is the process of selecting the most relevant features and removing irrelevant or redundant ones.

**Why it's important:**

* Reduces overfitting by removing noise.
* Improves model accuracy and reduces training time.
* Makes the model simpler and easier to interpret.

**Types of Feature Selection Methods:**

1. **Filter Methods**
   Use statistical techniques to score features:

   * Correlation matrix
   * Chi-square test
   * Mutual information

2. **Wrapper Methods**
   Use a machine learning model to test subsets of features:

   * Recursive Feature Elimination (RFE)
   * Forward/Backward Feature Selection

3. **Embedded Methods**
   Feature selection is part of the model training:

   * Lasso (L1 Regularization)
   * Decision Trees and Random Forests (feature importance)

---

## 📦 Feature Extraction

Feature extraction is the process of transforming raw data into a set of new features that can be used  for machine learning.
It’s especially useful when the original data is in an unstructured form (like text or images).

**Why it's important:**

* Helps in dimensionality reduction.
* Extracts the most informative components of data.
* Useful when dealing with high-dimensional data.

**Examples:**

* **From Text Data:**

  * Extracting word counts or TF-IDF values from documents.
  * Using NLP techniques like word embeddings (Word2Vec, GloVe).

* **From Images:**

  * Using Convolutional Neural Networks (CNNs) to extract features like edges, shapes, textures.

* **From Audio:**

  * Extracting Mel Frequency Cepstral Coefficients (MFCCs).

* **From Raw Numeric Data:**

  * Principal Component Analysis (PCA)
  * Linear Discriminant Analysis (LDA)

---

### Summary Table:

| Step                 | Purpose                                | Example                                |
| -------------------- | -------------------------------------- | -------------------------------------- |
| Feature Construction | Create new features from existing ones | `bmi = weight / height²`               |
| Feature Selection    | Pick the most important features       | Removing low-correlation features      |
| Feature Extraction   | Transform data into usable features    | Extracting keywords from a text column |

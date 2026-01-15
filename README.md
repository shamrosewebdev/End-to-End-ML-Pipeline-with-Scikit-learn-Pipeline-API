<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>End-to-End ML Pipeline - Customer Churn</title>
</head>
<body>

<h1>Task 2: End-to-End Machine Learning Pipeline using Scikit-learn</h1>

<h2>Objective</h2>
<p>
The objective of this task is to build a reusable and production-ready machine learning pipeline
for predicting customer churn using Scikit-learn’s Pipeline API. The focus is on clean data
preprocessing, model training, hyperparameter tuning, and exporting the final model for reuse.
</p>

<hr>

<h2>Dataset</h2>
<p><strong>Telco Customer Churn Dataset</strong></p>
<ul>
    <li>Source: OpenML (fetched programmatically)</li>
    <li>Description: Contains customer demographic details, service usage information, and churn status</li>
    <li>Target variable: <code>Churn</code> (Yes / No)</li>
</ul>

<hr>

<h2>Problem Type</h2>
<p><strong>Binary Classification</strong></p>
<ul>
    <li><strong>1</strong> → Customer churns</li>
    <li><strong>0</strong> → Customer does not churn</li>
</ul>

<hr>

<h2>Approach &amp; Methodology</h2>

<h3>1. Data Loading</h3>
<p>
The dataset was fetched directly from OpenML to ensure reproducibility and eliminate manual
file handling.
</p>

<h3>2. Data Preparation</h3>
<ul>
    <li>Target variable (<code>Churn</code>) encoded into binary format</li>
    <li>Features separated into numerical and categorical columns</li>
</ul>

<h3>3. Preprocessing Pipeline</h3>
<ul>
    <li><strong>Numerical features:</strong> Scaled using <code>StandardScaler</code></li>
    <li><strong>Categorical features:</strong> Encoded using <code>OneHotEncoder</code></li>
    <li><code>ColumnTransformer</code> used to apply transformations selectively</li>
</ul>

<h3>4. Model Pipelines</h3>
<p>
Two complete machine learning pipelines were constructed:
</p>
<ul>
    <li>Logistic Regression Pipeline</li>
    <li>Random Forest Pipeline</li>
</ul>
<p>
Each pipeline integrates preprocessing and model training into a single reusable workflow.
</p>

<h3>5. Hyperparameter Tuning</h3>
<ul>
    <li><code>GridSearchCV</code> used for hyperparameter optimization</li>
    <li>5-fold cross-validation applied</li>
    <li>Accuracy used as the evaluation metric</li>
</ul>

<h3>6. Model Selection</h3>
<p>
The best-performing model was selected based on cross-validation accuracy.
</p>

<h3>7. Model Export</h3>
<p>
The final trained pipeline was exported using <code>joblib</code>, allowing seamless reuse
without reapplying preprocessing steps.
</p>

<hr>

<h2>Models Used</h2>
<ul>
    <li>Logistic Regression</li>
    <li>Random Forest Classifier</li>
</ul>

<hr>

<h2>Key Results</h2>
<ul>
    <li>Successfully built an end-to-end ML pipeline</li>
    <li>Achieved reliable churn prediction performance</li>
    <li>Created a single reusable pipeline suitable for production use</li>
    <li>Ensured safe handling of unseen categories and feature scaling</li>
</ul>

<hr>

<h2>Tools &amp; Libraries</h2>
<ul>
    <li>Python</li>
    <li>Pandas</li>
    <li>Scikit-learn</li>
    <li>Joblib</li>
</ul>

<hr>

<h2>Using the Saved Model</h2>
<pre><code>
import joblib

model = joblib.load("churn_pipeline.pkl")
predictions = model.predict(new_data)
</code></pre>

<p>
No additional preprocessing is required, as all preprocessing steps are included within the pipeline.
</p>

<hr>

<h2>Skills Demonstrated</h2>
<ul>
    <li>Machine learning pipeline construction</li>
    <li>Feature preprocessing using Pipeline API</li>
    <li>Hyperparameter tuning with GridSearchCV</li>
    <li>Model export and reusability</li>
    <li>Production-ready ML practices</li>
</ul>

<hr>

<h2>Notes</h2>
<p>
This project emphasizes clean machine learning engineering practices and mirrors real-world
production ML workflows.
</p>

<hr>

<h2>Author</h2>
<p>
Internship Project – AI / Machine Learning
</p>

</body>
</html>

# Summer-Analytics-GFG-hackathon

NDVI-based Land Cover Classification — Summer Analytics Hackathon 2025
This project is a solution to a Kaggle hackathon challenge hosted by IIT Guwahati - E Cell. The goal is to classify land cover types using NDVI (Normalized Difference Vegetation Index) time series data.

Problem Statement
We are provided with NDVI data collected over time for different land regions. The task is to build a Logistic Regression model to classify each region into one of the following land cover types:
•	water
•	impervious
•	farm
•	forest
•	grass
•	orchard
📌 Constraints:
•	Only Logistic Regression (Multiclass) is allowed.
•	Feature engineering, denoising, and imputation are allowed.
•	Evaluation is based on accuracy.


Dataset Overview
•	Train file: hacktrain.csv
➤ Contains 8000 rows with:
o	ID: Unique sample ID
o	class: Target land cover type
o	27 NDVI values: Named by date like 20150720_N, 20150602_N, etc.
•	Test file: Provided separately for final prediction


Approach
1.	Missing Value Imputation:
o	NDVI columns are grouped by class, and missing values are filled using class-wise mean.
o	Further cleaned using row-wise interpolation (to preserve time series trends).
2.	Label Encoding:
o	The target column class is encoded using LabelEncoder.
3.	Model:
o	Multinomial Logistic Regression with lbfgs solver
o	Used class_weight='balanced' to handle class imbalance
o	Split data using train_test_split for evaluation
4.	Evaluation:
o	Report includes precision, recall, f1-score, and accuracy
o	classification_report from sklearn used to track performance per class


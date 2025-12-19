# E-commerce User Behavior Analysis
### Members: 
##### Mingjia Cai - mc5645 
##### Shuxin Liang - sl5611 
##### Weiyi Guo - wg2444 

#### E-Commerce User Behavior Analysis & Prediction System
A comprehensive Big Data analytics pipeline designed to optimize e-commerce operations. This system integrates RFM modeling, Logistic Regression for purchase prediction (AUC=0.96), and Z-score based user segmentation to transform raw clickstream data into actionable marketing insights.

#### Project Overview
In the era of Big Data, traditional mass-marketing strategies struggle to address individual user needs. This project leverages a large-scale e-commerce dataset (67.5M+ events) satisfying the 3V characteristics (Volume, Variety, Velocity) to build an end-to-end data mining pipeline.
##### Key Objectives

* **In-depth Behavior Analysis**: Identify key decision points in the user shopping journey (View $\to$ Cart $\to$ Purchase).
* **Customer Value Framework**: Quantify customer loyalty using the **RFM** (Recency, Frequency, Monetary) model.
* **Purchase Intent Prediction**: Develop a machine learning model to estimate future purchase likelihood.
* **Actionable Segmentation**: Categorize users into interpretable groups (e.g., *High Interest/High Risk*, *Churn Warning*) for precision marketing.

#### System Architecture
* The system utilizes a cloud-based architecture integrating Google Cloud Dataproc and Apache Spark for distributed processing.
* **Front-end**: Interactive web interface for report selection (HTML/CSS/JS).
* **Back-end**: PySpark pipeline running on Spark clusters.
* **Data Storage**: Google Cloud Storage (GCS).
  
#### Features & Methodologies

##### 1. Data Preprocessing & Feature Engineering
* **Data Cleaning**: Handling missing values and aggregating raw logs by `user_id`.
* **Log Transformation**: Applied $log(1 + x)$ transformation to handle extreme right-skewed distributions in spending data.
* **Feature Extraction**: Generated temporal features (Hour-of-day, Weekday) and session metrics.

##### 2. RFM Analysis
* Calculated **Recency**, **Frequency**, and **Monetary** scores to quantify historical user value.
* Used as a bridge between descriptive analytics and predictive modeling.

##### 3. Purchase Prediction Model
* **Algorithm**: Logistic Regression with L2 Regularization (chosen for interpretability and robustness).
* **Performance**: Achieved **AUC-ROC: 0.9657**.
* **Key Insights**: Cart-related actions are the strongest positive predictors, while high average view prices correlate negatively with conversion.

##### 4. Z-Score Segmentation
* Standardized behavioral features using Z-scores ($z = \frac{x-\mu}{\sigma}$).
* **Key Segments Identified**:
  * **High Interest / High Risk**: High cart activity but no purchase ($Z_{cart} > 1.0$). Strategy: Retargeting/Discounts.
  * **Churn Warning**: Frequent views but zero cart activity. Strategy: Simplify UX/Feedback.

#### Experimental Results
* **Funnel Analysis**: Validated a significant drop-off between view (94%) and cart (4%) events.
* **Temporal Patterns**: Identified peak activity hours (10 AM - 4 PM) and weekly trends.
* **Category Demand**: Confirmed a head-tail structure where top categories (e.g., construction.tools, sport.bicycle) drive majority sales.

#### Installation & Usage
##### Prerequisites
* Python 3.8+
* Apache Spark 3.0+
* Google Cloud 

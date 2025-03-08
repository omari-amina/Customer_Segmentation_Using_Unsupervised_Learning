# Customer_Segmentation_Using_Unsupervised_Learning
This project leverages unsupervised learning techniques to segment customers based on transactional and demographic data.By applying various clustering algorithms, the project aims to uncover hidden patterns that can inform targeted marketing strategies, improve customer engagement, and support data-driven decision-making.

Project Structure
Environment Setup and Library Imports
Data Collection & Preprocessing
Feature Engineering
Modeling and Clustering Techniques
Evaluation Metrics
Key Findings and Insights
How to Run the Project
Environment Setup and Library Imports
The project begins with setting up the Python environment and importing essential libraries. Key libraries include:

NumPy & Pandas: For numerical operations and data manipulation.
Matplotlib & Seaborn: For data visualization.
Scikit-Learn: For preprocessing, clustering algorithms, and evaluation metrics.
SciPy: For generating dendrograms in hierarchical clustering.
Example code snippet:


Data Collection & Preprocessing
Data Loading
The dataset is loaded from an Excel file containing multiple sheets. Each sheet represents a different aspect of the data:

customers
transactions
genders
cities
branches
merchants
Data is extracted by reading specific sheets and selecting relevant columns. For instance, customer data is filtered to include only customer_id, city_id, and gender_id.


Data Merging
Multiple datasets are merged using inner joins on common identifiers (e.g., customer_id, gender_id, and city_id) to create a unified dataset that includes both customer demographics and transactional details.


Data Cleaning and Overview
The merged data is examined for its dimensions, data types, and missing values. Basic statistical summaries are generated to understand the distribution of the features.


Additional Preprocessing Steps
To enrich the dataset, coupon usage frequency is calculated by grouping the transactions by customer_id. Unnecessary columns such as coupon_name and transaction_date are dropped once their information has been processed.

Feature Engineering
Encoding Categorical Variables
Categorical data must be transformed into a numerical format suitable for clustering. In this project:

Label Encoding is applied to the transaction_status column.
One-Hot Encoding (using pd.get_dummies) is applied to categorical features like gender_name and city_name obtained after merging.

Final Feature Set
The final dataset used for clustering is prepared by dropping non-feature columns (like customer_id) and ensuring all features are numeric and scaled appropriately if necessary.


Modeling and Clustering Techniques
Multiple clustering algorithms are applied to segment the customer base:

K-Means Clustering
K-Means is used to partition the data into clusters. The elbow method (plotting the Within-Cluster Sum of Squares, or WCSS) helps determine the optimal number of clusters. Evaluation is performed using both the Silhouette Score and the Davies-Bouldin Index.


DBSCAN (Density-Based Clustering)
DBSCAN is used to detect clusters of varying shapes based on density, which is useful for identifying outliers.


Hierarchical Clustering
Agglomerative Clustering is applied and visualized through a dendrogram to understand the hierarchical relationship between samples.


Evaluation Metrics
To assess the quality of the clusters, the following evaluation metrics are used:

Within-Cluster Sum of Squares (WCSS): Measures the compactness of clusters. A lower WCSS suggests tighter clusters.
Silhouette Score: Indicates how similar a point is to its own cluster compared to other clusters. Higher values suggest well-separated clusters.
Davies-Bouldin Index: Evaluates intra-cluster similarity and inter-cluster differences. Lower values indicate better clustering.
Key Findings and Insights
Distinct Customer Segments:
Clustering analysis reveals multiple segments within the customer base, each with distinct behaviors and demographic characteristics.

Optimal Clustering:
The elbow method and evaluation metrics (Silhouette Score and Davies-Bouldin Index) help in determining the optimal number of clusters, ensuring a balance between model complexity and interpretability.

Actionable Insights:
Detailed profiling of each cluster provides valuable insights into customer spending habits, coupon usage, and other key behaviors, enabling tailored marketing strategies.

Robustness Across Algorithms:
By comparing results from K-Means, DBSCAN, and Hierarchical Clustering, the analysis ensures that the identified segments are robust and meaningful across different clustering methodologies.

## How to Run the Project

### Clone the Repository

```
git clone <repository-url>
```
### Install Required Libraries

```
pip install -r requirements.txt
```
### Run the Notebook Launch the Jupyter Notebook:
```
jupyter notebook Customer_Segmentation_Using_Unsupervised_Learning.ipynb
```
Explore the Analysis Step through each section in the notebook to review data collection, preprocessing, feature engineering, and clustering analysis.
Conclusion
This project demonstrates the effective application of unsupervised learning to customer segmentation. By combining robust data preprocessing, thoughtful feature engineering, and multiple clustering algorithms, the analysis uncovers actionable insights that can drive targeted marketing efforts and strategic business decisions. Future work may explore additional clustering techniques or incorporate new data sources for even richer segmentation.

License
This project is licensed under the MIT License.

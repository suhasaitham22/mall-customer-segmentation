# Mall Customer Segmentation

Customer segmentation on the classic Mall Customers dataset using clustering. The goal is the standard marketing analytics exercise: group mall shoppers into distinct segments based on age, annual income, and spending score, so each segment can be understood and targeted differently.

## Dataset

`Mall_Customers.csv` — 200 rows with 5 columns: `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, `Spending Score (1-100)`. Mean age is about 39, mean income about $61k, and mean spending score about 50. No missing values.

## Approach

The notebook (`CUSTOMER SEGMENTATION.ipynb`) works through the analysis step by step:

1. **Exploration.** Load the data, check shapes, missing values, and summary statistics. Visualize the distributions of age, income, and spending score, the gender split, and income vs. spending score.
2. **Preprocessing.** Drop `CustomerID`, which carries no signal for segmentation.
3. **Choosing k.** Fit K-Means for k = 1..10 (k-means++ initialization) and plot the within-cluster sum of squares to find the elbow.
4. **Clustering.** Fit `KMeans(n_clusters=5)` on Age, Annual Income, and Spending Score, assign every customer a segment label, and visualize the clusters, including a 3D scatter of the three features.

## Results

Five customer segments, covering the usual patterns (e.g. high income / high spending shoppers versus low income / low spending ones). Since clustering is unsupervised, there are no accuracy metrics; the output is the labeled segments and the cluster visualizations.

## How to run

```bash
git clone https://github.com/suhasaitham22/mall-customer-segmentation.git
cd mall-customer-segmentation
pip install numpy pandas matplotlib seaborn scikit-learn jupyter
jupyter notebook "CUSTOMER SEGMENTATION.ipynb"
```

## Tech stack

Python, pandas, matplotlib, seaborn, scikit-learn (K-Means), Jupyter Notebook.

Task 1: Exploring and Visualizing the Iris Dataset


Difficulty: Beginner
Objective: Load and explore the Iris dataset, then create visualizations that reveal patterns across three flower species.
Dataset: Iris Dataset (built into seaborn — no download required)
Tools Used: pandas, numpy, matplotlib, seaborn


Visualizations Created:


Scatter plot: Sepal Length vs Sepal Width
Scatter plot: Petal Length vs Petal Width
Histograms: Distribution of all 4 features
Box plots: Feature spread by species (2×2 grid)
Correlation heatmap
Pair plot: All features vs all features


Key Findings:


Setosa is clearly separable from Versicolor and Virginica using petal measurements alone — its petals are significantly smaller.
Petal features carry more discriminative information than sepal features (bimodal histogram distribution confirms this).
Strong correlation exists between petal length and petal width (r = 0.96).
No missing values were found — the dataset is clean and ready for ML tasks.
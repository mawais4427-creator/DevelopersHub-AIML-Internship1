# Task 1: Exploring and Visualizing a Dataset

**Internship:** DevelopersHub Corporation — AI/ML Engineering  
**Intern Name:** Muhammad Awais  
**Due Date:** 26th June, 2026  
**Difficulty:** Beginner

---

## Objective

Load the famous Iris dataset, explore its structure using pandas, and create meaningful visualizations to reveal patterns across three flower species.

---

## Dataset

- **Name:** Iris Dataset
- **Source:** Built into the `seaborn` library — no download needed
- **Size:** 150 rows, 5 columns
- **Species:** Setosa, Versicolor, Virginica
- **Features:** sepal_length, sepal_width, petal_length, petal_width

---

## Libraries Used

| Library    | Purpose |
|----------- | --------------
| pandas     | Load and explore the dataset |
| numpy      | Numerical operations |
| matplotlib | Create charts and plots |
| seaborn    | Load dataset and create styled visualizations |

---

## Steps Performed

1. Imported all required libraries
2. Loaded the Iris dataset using `sns.load_dataset('iris')`
3. Explored the dataset — shape, columns, data types, and statistics
4. Checked species distribution using `value_counts()`
5. Created a scatter plot — Sepal Length vs Sepal Width (colored by species)
6. Created histograms — distribution of all 4 measurements
7. Created box plots — feature spread per species (2×2 grid)
8. Wrote a summary of findings in a Markdown cell

---

## Visualizations Created

- **Scatter Plot** — Sepal Length vs Sepal Width, colored by species
- **Histograms** — Distribution of sepal_length, sepal_width, petal_length, petal_width
- **Box Plots** — 2×2 grid showing spread and outliers per species for all 4 features

---

## Key Findings

- The dataset has 150 rows and 5 columns with no missing values
- Each species has exactly 50 samples
- **Setosa** is clearly separable from Versicolor and Virginica based on petal size
- Petal length and petal width are the most useful features for separating species
- No significant outliers were found in the box plots
- Versicolor and Virginica overlap slightly, making them harder to separate

---

## How to Run

1. Open `task1.ipynb` in VS Code or Google Colab
2. Run the first cell to import libraries
3. Run all cells top to bottom using **Shift + Enter**
4. All charts will appear below each code cell

> No dataset download needed — the Iris dataset loads automatically from seaborn.

---

## File Structure

```
Task1 developerhub/
└── task1.ipynb
```

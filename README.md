# 🍽️ Restaurant Data Analysis — Advanced Explorations Using Python

A data science mini-project that uses **Exploratory Data Analysis (EDA)** to uncover patterns in real-world restaurant data. The goal is to help food lovers discover the best-rated, most cost-effective, and cuisine-specific dining options in their area — driven by data, not just word-of-mouth.

---

## 📌 Problem Statement

In a fast-evolving food culture, diners often struggle to find quality restaurants that offer the best value for money. This project analyzes restaurant data to reveal patterns in:

- Pricing and cost for two
- User ratings and votes
- Cuisine variety
- Delivery and service availability
- Geographic distribution across Indian cities

---

## 🎯 Objectives

- Load and explore a large real-world restaurant dataset (~2 lakh entries)
- Clean and prepare data by handling missing values
- Visualize missing data patterns
- Study correlations between key variables (cost, rating, votes, etc.)
- Detect outliers using boxplots
- Engineer a new **`region`** feature from city names (e.g., North India, South India)

---

## 📂 Project Structure

```
├── food_dely.csv              # Raw dataset (restaurant data)
├── Mini-Project.ipynb         # Main Jupyter Notebook
└── README.md                  # Project documentation
```

---

## 📊 Dataset Overview

The dataset contains information about dining outlets across multiple Indian cities, with the following key columns:

| Column | Description |
|--------|-------------|
| `name` | Restaurant name |
| `city` | City where the restaurant is located |
| `locality` | Neighborhood within the city |
| `cuisines` | List of cuisines offered |
| `average_cost_for_two` | Estimated dining cost for two people |
| `price_range` | Tiered cost bracket (1 = low, 4 = premium) |
| `aggregate_rating` | Overall user rating |
| `votes` | Total user feedback count |
| `photo_count` | Number of photos uploaded |
| `delivery` | Whether delivery is available |
| `highlights` | Special features (e.g., Outdoor Seating, Live Music) |
| `region` | *(Engineered)* Geographic region based on city |

---

## 🛠️ Tech Stack

- **Python 3**
- **Pandas** — data loading, cleaning, and manipulation
- **NumPy** — numerical operations
- **Matplotlib** — custom visualizations
- **Seaborn** — statistical plots (heatmaps, boxplots)

---

## 🔍 Key Steps

### 1. Import Libraries & Set Options
Standard data science libraries are imported and display options are configured.

### 2. Load the Data
Dataset is read from `food_dely.csv` using `pandas.read_csv()`.

### 3. Understand the Data
- Shape: **211,944 rows × 26 columns**
- Dtypes, column names, and basic statistics are explored.

### 4. Handle Missing Values
Missing values are identified and filled intelligently:
- `establishment`, `address`, `cuisines` → filled with **mode**
- `zipcode` → filled with **median** (if numeric) or **mode** (if string)
- `timings` → filled with `"Not Available"`
- `highlights` → filled with `"No info given"`
- `opentable_support` → filled with `0` (assuming not supported)

### 5. Correlation Analysis
A correlation matrix and heatmap are generated for all numeric columns. Notable findings:
- `average_cost_for_two` and `price_range` are **strongly correlated** (~0.79)
- `votes` and `photo_count` show a **moderate positive correlation** (~0.65)

### 6. Outlier Detection
Boxplots are created for all numeric columns to visually identify outliers in:
- `average_cost_for_two`
- `votes`
- `aggregate_rating`
- `photo_count`, and more

### 7. Feature Engineering — `region` Column
A new column `region` is created by mapping city names to geographic regions:

| City | Region |
|------|--------|
| Delhi, Agra, Jaipur, Lucknow, Noida, Gurgaon | North India |
| Mumbai, Pune, Ahmedabad | West India |
| Bangalore, Hyderabad, Chennai | South India |
| Kolkata, Patna | East India |
| Others | Other |

---

## 📈 Sample Insights

- **Most restaurants** fall in the `price_range` 1–2 (budget-friendly)
- **Higher-rated restaurants** tend to have more votes and photos
- **Delivery availability** correlates positively with aggregate rating
- `zipcode` has the most missing values (~77% missing)

---

## 🚀 How to Run

1. Clone the repository or download the files.
2. Make sure you have Python 3 and the required libraries installed:
   ```bash
   pip install pandas numpy matplotlib seaborn tabulate
   ```
3. Place `food_dely.csv` in the same directory as the notebook.
4. Open and run `Mini-Project.ipynb` in Jupyter Notebook or JupyterLab.

---

## 👤 Author

**Rushabh Upadhye**
Data Science with GenAI — Python Mini Project

---

## 📝 License

This project is for educational purposes only.

# 🎬 MovieLens 100K — Movie Rating & User Behaviour Analysis

An exploratory data analysis of the classic **MovieLens 100K dataset**, covering user demographics, movie ratings, genre trends over the years, top-rated films, and gender-wise viewing preferences using Python.

---

## 📌 Project Overview

This project analyzes the MovieLens 100K dataset — one of the most widely used datasets in recommendation system research. It explores how different users rate movies, which genres have grown over the decades, what the top 25 movies are by average rating, and how viewing habits differ between male and female users.

---

## 📂 Dataset

- **Source:** [GroupLens — MovieLens 100K Dataset](https://grouplens.org/datasets/movielens/100k/)
- **Files used:**

| File | Description |
|---|---|
| `u_data.csv` | 100,000 ratings by users — `user_id`, `item_id`, `rating`, `timestamp` |
| `u_user.csv` | User demographics — `user_id`, `age`, `gender`, `occupation`, `zip_code` |
| `u_item.csv` | Movie details — `movie_id`, `movie_title`, `release_date`, 19 genre columns |

---

## 🧹 Data Cleaning

- Dropped irrelevant columns: `video_release_date`, `IMDb_URL`
- Converted `release_date` to datetime format
- Checked and confirmed no missing values in all three datasets
- Detected and removed **hidden duplicate movies** (same movie assigned to two different `movie_id`s) using index-level deduplication

---

## 🔍 Analysis Breakdown

### 📊 Univariate Analysis
- **Rating distribution** — count plot of ratings (1 to 5)
- **Age distribution** — histogram with KDE of user ages
- **Release date distribution** — histogram of movie release years
- **Gender distribution** — count plot (Male vs Female users)
- **Occupation distribution** — count plot of all user occupations

### 📈 Genre Trends Over the Years (Bivariate)
- Extracted release year from `release_date`
- Grouped all 19 genres by year and summed counts
- Scatter plot and line plot showing how each genre has evolved over decades

### 🏆 Top 25 Movies by Average Rating
- Filtered movies with more than **100 reviews** (to avoid rating bias)
- Ranked by **average rating** to find the most consistently well-rated films

### 👥 Gender-wise Viewing Comparison
- Merged all three datasets (`u_data`, `u_item`, `u_user`) using joins
- Compared **Drama**, **Romance**, and **Sci-Fi** genre preferences between Male and Female users
- Key findings from 943 total users:
  - All 943 users watched **Drama** and **Romance** — men lead in watch count for both
  - **Sci-Fi** is not watched by every user — men still lead here too

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3 | Core language |
| Pandas | Data loading, cleaning & joins |
| NumPy | Numerical operations |
| Matplotlib | Line plots & scatter plots |
| Seaborn | Count plots & histograms |
| Google Colab | Development environment |

---

## 🚀 How to Run

### Option 1 — Open in Google Colab
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

*(Replace with your actual Colab notebook link)*

### Option 2 — Run Locally
```bash
git clone https://github.com/anshu1516/MovieLens-100K-Analysis.git
cd MovieLens-100K-Analysis

pip install pandas numpy matplotlib seaborn

jupyter notebook Case_Study_ml100k.ipynb
```

> **Note:** Download `u_data.csv`, `u_user.csv`, and `u_item.csv` from [GroupLens](https://grouplens.org/datasets/movielens/100k/) and place them in the same directory before running.

---

## 💡 Key Insights

- **Drama and Action** genres have grown the most consistently over the decades
- Filtering movies with **100+ reviews** gives a much fairer top-rated list than raw averages
- **Men outnumber women** in viewership across Drama, Romance, and Sci-Fi — reflecting the dataset's user demographics
- Hidden duplicates in the `u_item` dataset can silently corrupt analysis if not caught early

---

## 👤 Author

**Anshu** — [GitHub](https://github.com/anshu1516)

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

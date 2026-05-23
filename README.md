# 🎬 Content-Based Movie Recommendation System

## 📌 Project Overview

CineMatch AI is a **Content-Based Movie Recommendation System** built using **Python** in **Google Colab**. It recommends movies by analyzing content similarities between films using features such as **overview**, **genres**, **keywords**, and **cast** from the TMDB 5000 Movie Dataset.

The system uses **Natural Language Processing (NLP)** techniques like **TF-IDF Vectorization** and **Cosine Similarity** to generate personalized movie recommendations.

---

## 🚀 Project Objective

To build an intelligent recommendation engine that suggests the **Top 5 most similar movies** based on a user's selected movie title.

---

## 📂 Dataset Used

Dataset: **TMDB 5000 Movie Dataset** from Kaggle
Files used:

* `tmdb_5000_movies.csv`
* `tmdb_5000_credits.csv`

### Key Features Used

From `tmdb_5000_movies.csv`:

* overview
* genres
* keywords
* title
* movie_id

From `tmdb_5000_credits.csv`:

* cast

---

## 🛠 Tech Stack

* **Python**
* **Google Colab**
* **Pandas** — data preprocessing
* **NumPy** — numerical operations
* **Scikit-learn** — TF-IDF & cosine similarity
* **Pickle** — model serialization
* **Requests** — poster API integration (TMDB)
* **Gradio** — interactive deployment/UI

---

## ⚙️ Workflow

### 1. Data Cleaning

* Merged movie and credits datasets.
* Selected relevant columns.
* Parsed JSON-like columns (`genres`, `keywords`, `cast`).
* Extracted top 3 cast members.
* Combined text features into a single `tags` column.
* Converted all text to lowercase.
* Removed spacing inconsistencies.

### 2. Feature Engineering

Created a unified `tags` column using:

* overview
* genres
* keywords
* cast

Example:

```
"space adventure alien samworthington zoesaldana sciencefiction"
```

### 3. Vectorization

Applied **TF-IDF Vectorizer**:

* max_features = 5000
* stop_words = 'english'

This converts movie tags into numerical vectors.

### 4. Similarity Calculation

Used **Cosine Similarity** to calculate similarity between all movie vectors.

### 5. Recommendation Engine

Implemented:

```python
recommend(movie_title)
```

Returns:

* Top 5 most similar movies.

### 6. Poster Integration

Integrated **TMDB API** to fetch movie posters dynamically.

### 7. Deployment

Created an interactive app using **Gradio** in Google Colab.

---

## 📸 Sample Output

Input:

```
Avatar
```

Output:

* Guardians of the Galaxy
* John Carter
* Star Trek
* Aliens vs Predator
* The Fifth Element

(with posters displayed in UI)

---

## 📁 Generated Files

* `movies.pkl`
* `similarity.pkl`
* `vectorizer.pkl`

These files allow quick loading without retraining.

---

## ▶️ How to Run

1. Open Google Colab.
2. Upload:

   * `tmdb_5000_movies.csv`
   * `tmdb_5000_credits.csv`
3. Run notebook cells in order.
4. Add your TMDB API key.
5. Launch Gradio app.
6. Enter a movie name and get recommendations.

---

## 🔮 Future Enhancements

* Add fuzzy search for misspelled titles.
* Build hybrid recommendation system.
* Add user login & watch history.
* Deploy permanently on cloud.
* Add genre-based filtering.

---


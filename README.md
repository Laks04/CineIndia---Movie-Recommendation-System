# 🎬 CineIndia — Movie Recommendation System

A content-based movie recommendation engine covering Indian cinema across multiple languages, complete with an interactive web interface served via Flask.

---

## 📖 Overview

CineIndia recommends Indian movies using **TF-IDF vectorization** and **cosine similarity** computed over a rich feature set: genre, language, director, cast, and plot description. Users can filter by language, genre, rating, and year range to get personalized recommendations through a polished dark-themed web UI.

---

## ✨ Features

- **Multi-language coverage** — Hindi, Tamil, Telugu, Malayalam, Kannada, Bengali, Marathi, Punjabi
- **Content-based filtering** — TF-IDF + cosine similarity on combined movie features
- **Flexible filtering** — language, genre, IMDb rating threshold, and year range
- **EDA dashboard** — six auto-generated charts: movies per language, rating distribution, release timeline, average rating by language, genre popularity, and rating vs. votes scatter
- **Flask web app** — interactive browser UI with live search and recommendations
- **60+ curated titles** — spanning classics (1955) to modern blockbusters (2022)

---

## 🗂️ Project Structure

```
CineIndia_Movie_Recommendation_System_.ipynb
│
├── Cell 1 — Install Dependencies
├── Cell 2 — Build Dataset (all Indian languages)
├── Cell 3 — Exploration & Visualisation  →  cineindia_eda.png
├── Cell 4 — Build Recommendation Engine  (TF-IDF + cosine similarity)
└── Cell 5 — Launch CineIndia Website     (Flask server)
```

---

## 🛠️ Tech Stack

| Component | Library / Tool |
|---|---|
| Data handling | `pandas`, `numpy` |
| ML / NLP | `scikit-learn` (TfidfVectorizer, cosine_similarity) |
| Visualisation | `matplotlib`, `seaborn` |
| Web server | `Flask`, `flask-cors` |
| Frontend | Vanilla HTML / CSS / JS (embedded in Flask) |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- Jupyter Notebook or Google Colab

### Installation

```bash
pip install pandas scikit-learn flask flask-cors matplotlib seaborn numpy
```

### Running the Notebook

1. Open `CineIndia_Movie_Recommendation_System_.ipynb` in Jupyter or Colab.
2. Run **Cell 1** to install dependencies.
3. Run **Cell 2** to load the dataset.
4. Run **Cell 3** to generate and save the EDA charts (`cineindia_eda.png`).
5. Run **Cell 4** to build the TF-IDF recommendation engine.
6. Run **Cell 5** to start the Flask server — a clickable URL will appear in the output.

---

## 🤖 How the Recommendation Engine Works

```
Movie features = genre + language + director + top-2 cast + description
       ↓
TF-IDF vectorization  (unigrams + bigrams, English stop-words removed)
       ↓
Cosine similarity between query movie and candidate pool
       ↓
Filter by: language | genre | min_rating | year range
       ↓
Top-N recommendations sorted by similarity score (or rating if no seed title)
```

### `get_recommendations()` parameters

| Parameter | Default | Description |
|---|---|---|
| `title` | `""` | Seed movie title (optional) |
| `language` | `"All"` | Filter by language |
| `genre` | `"All"` | Filter by genre |
| `min_rating` | `5.0` | Minimum IMDb rating |
| `year_from` | `1950` | Earliest release year |
| `year_to` | `2025` | Latest release year |
| `n` | `20` | Number of recommendations |

---

## 📊 Dataset

The built-in dataset contains **60+ hand-curated Indian films** with the following fields:

| Field | Description |
|---|---|
| `title` | Movie title |
| `language` | Original language |
| `year` | Release year |
| `genre` | Comma-separated genres |
| `director` | Director name(s) |
| `cast` | Lead cast members |
| `rating` | IMDb rating |
| `votes` | IMDb vote count |
| `description` | Plot summary |

**Languages covered:** Hindi · Tamil · Telugu · Malayalam · Kannada · Bengali · Marathi · Punjabi

---

## 🌐 Web Interface

Once the Flask server starts (Cell 5), navigate to the printed URL to access:

- **Search bar** — type a movie title to find similar films
- **Filter dropdowns** — language, genre
- **Sliders** — minimum rating, year range
- **Stats banner** — total movies, languages, average rating, year span
- **Marquee ticker** — scrolling movie titles

---

## 📸 Sample EDA Output

The notebook saves `cineindia_eda.png` containing:

1. Movies per language (horizontal bar chart)
2. IMDb rating distribution (histogram with mean line)
3. Movies released over years (line + area chart)
4. Average rating by language (bar chart)
5. Genre popularity (horizontal bar chart)
6. Rating vs. votes (scatter with year colour map)

---

## 🔮 Possible Improvements

- Integrate a live IMDb / TMDB API for a larger, always-current dataset
- Add collaborative filtering using user ratings
- Deploy to a cloud platform (Render, Railway, Heroku) for public access
- Include poster images via TMDB API
- Add multilingual search support

---

## 📄 License

This project is for educational and personal use. Movie metadata is sourced from publicly available information.

# Movie Recommendation System

A content-based movie recommender built with **Streamlit**, **pandas**, and **scikit-learn**. The app lets a user select a movie title and returns **5 similar movie recommendations** along with their poster images.

## Overview

This project uses a precomputed similarity matrix to find movies that are close to the selected title. The interface is simple: choose a movie from the dropdown, click **Recommend**, and the app displays recommended titles with posters fetched from **TMDB (The Movie Database)**.

## Features

- Select a movie from the available dataset
- Get top 5 recommended similar movies
- Fetch and display movie posters dynamically using the TMDB API
- Lightweight Streamlit-based UI
- Fast recommendations using precomputed similarity scores

## Tech Stack

- **Python**
- **Streamlit**
- **pandas**
- **NumPy**
- **scikit-learn**
- **requests**

## Project Structure

```text
Movie-Recommendation-System-main/
├── app.py
├── requirements.txt
├── movies.pkl
├── similarity.pkl
├── .gitattributes
└── .devcontainer/
    └── devcontainer.json
```

## How It Works

1. The app loads movie metadata from `movies.pkl`.
2. It loads a precomputed similarity matrix from `similarity.pkl`.
3. When the user selects a movie, the corresponding similarity scores are retrieved.
4. The top matching movies are selected.
5. Poster images are fetched using the movie IDs through the TMDB API.
6. Results are displayed in 5 columns using Streamlit.

## Installation

Clone the repository and install dependencies:

```bash
git clone <your-repo-link>
cd Movie-Recommendation-System-main
pip install -r requirements.txt
```

## Run the Project

```bash
streamlit run app.py
```

Then open the local Streamlit URL shown in the terminal.

## Requirements

From `requirements.txt`:

```txt
streamlit
pandas
requests
scikit-learn
numpy
```

## Important Notes

### 1. Git LFS files
This repository currently contains **Git LFS pointer files** for:

- `movies.pkl`
- `similarity.pkl`

That means the actual dataset/model files may not be present unless Git LFS objects are properly pulled.

If the app does not run and shows pickle-related errors, install Git LFS and pull the real files:

```bash
git lfs install
git lfs pull
```

### 2. TMDB API key
`app.py` currently contains a TMDB API key directly in the code. For a public repository, it is better to move that key into an environment variable or Streamlit secrets.

Example approach:

```python
import os
api_key = os.getenv("TMDB_API_KEY")
```

Then run with the key set in your environment.

## Possible Improvements

- Add a search bar with autocomplete
- Handle missing dataset/model files more gracefully
- Move the TMDB API key to environment variables
- Add movie overview, rating, genre, and release year
- Deploy the app on Streamlit Community Cloud
- Improve error handling for network/API failures
- Add a screenshot or live demo link in the README

## Learning Outcomes

This project demonstrates:

- recommendation system basics
- similarity-based retrieval
- model/data serialization with pickle
- API integration in Python
- building data apps with Streamlit

## Limitations

- Recommendations depend entirely on the quality of the precomputed similarity matrix
- No user-based or hybrid recommendation logic is implemented
- Poster fetching depends on TMDB API availability
- The repo, as uploaded, may not include the actual large `.pkl` files unless Git LFS is configured correctly

## Author

**Aayush Mehta**


<img width="451" height="693" alt="image" src="https://github.com/user-attachments/assets/1351f4b8-b3f6-4636-abf7-62870ef8902d" />

# Content-Based Music Recommendation System

This project is a full-stack web application that recommends Spotify tracks based on audio feature input using a K-Nearest Neighbors model. Users can select a genre and adjust audio parameters to find the closest matching track in the dataset.

## 🎯 Overview

The application matches user-defined audio preferences to the most similar track in a Spotify dataset. Users can:

- Select a music genre or let the system pick randomly
- Adjust audio parameters using interactive sliders
- Receive a track recommendation with matching audio features
- Open the recommended track directly in Spotify

## 🤖 Model

A **K-Nearest Neighbors (KNN)** model is used to find the track closest to the user's input:

- **With genre selected** – input is scaled and one-hot encoded, then matched against the full feature space including genre
- **Random genre** – only the numerical audio features are used for matching, ignoring genre

## 📊 Data

The model is trained on a curated Spotify dataset of high-popularity tracks.

**Audio features used:**

- `energy` – intensity and activity of the track
- `danceability` – how suitable the track is for dancing
- `valence` – musical positiveness (happy vs. sad)

**Preprocessing:**

- Numerical features scaled using `MinMaxScaler`
- Categorical genre feature encoded using `OneHotEncoder`

## 🏗️ System Architecture

The application consists of two main components:

- **Frontend (HTML / CSS / JS)** — Genre carousel, parameter sliders, and result display
- **Backend API (Python / Flask)** — Handles preprocessing and KNN inference

## 🔌 API Endpoints

| Endpoint | Method | Description |
|---|---|---|
| `/` | GET | Serves the main interface |
| `/get_genres` | POST | Returns list of available genres from the dataset |
| `/get_recommendation` | POST | Returns the nearest matching track for given parameters |

## 📈 Frontend Features

- Visual genre carousel with cover images fetched from the Pixabay API
- Sliders for energy, danceability, and valence with live value display
- Result card showing track name, artist, genre, and audio feature values
- "More Information" toggle to expand all track metadata
- Direct link to open the recommended track in Spotify

## 🚀 Possible Extensions

- Expand feature set (e.g. tempo, acousticness, instrumentalness)
- Return top-N recommendations instead of a single match
- Add user feedback loop to refine recommendations
- Integrate Spotify API directly for real-time data

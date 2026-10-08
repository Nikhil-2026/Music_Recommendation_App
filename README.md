# 🎵 Music Recommendation App

A simple **Music Recommendation System** built using Python and Streamlit.

This project recommends songs that are similar to a song selected by the user. The recommendation is based on the **lyrics of the songs** using **TF-IDF** and **Cosine Similarity**.

## Features

* Select a song from the available songs.
* Find songs with similar lyrics.
* Display the top 5 recommended songs.
* Simple web interface using Streamlit.

## Technologies Used

* **Python**
* **Pandas** – for handling the dataset
* **NLTK** – for text preprocessing
* **Scikit-learn** – for TF-IDF and Cosine Similarity
* **Joblib** – for saving and loading processed data
* **Streamlit** – for the web interface

## How the Project Works

The project has three main Python files.

### 1. `preprocess.py`

This file prepares the song data.

It:

* Loads the CSV dataset.
* Takes a sample of 10,000 songs.
* Removes unnecessary columns.
* Cleans the song lyrics.
* Converts the lyrics to lowercase.
* Removes special characters.
* Tokenizes the text.
* Removes English stopwords.
* Converts the cleaned lyrics into TF-IDF vectors.
* Calculates Cosine Similarity between the songs.
* Saves the processed data as `.pkl` files.

### 2. `recommend.py`

This file contains the recommendation logic.

It:

* Loads the processed data.
* Finds the song selected by the user.
* Gets the similarity scores for that song.
* Sorts the songs based on similarity.
* Removes the selected song from the results.
* Selects the top 5 similar songs.
* Returns the artist and song names.

### 3. `main.py`

This file creates the Streamlit application.

It:

* Loads the available songs.
* Displays a dropdown for selecting a song.
* Takes the selected song from the user.
* Calls the recommendation function.
* Displays the top 5 recommended songs.

## Recommendation Process

```text
Song Dataset
     ↓
Text Cleaning
     ↓
TF-IDF Vectorization
     ↓
Cosine Similarity
     ↓
Select a Song
     ↓
Find Similar Songs
     ↓
Top 5 Recommendations
```

## TF-IDF

**TF-IDF (Term Frequency-Inverse Document Frequency)** converts the song lyrics into numerical vectors.

It gives more importance to words that are useful for distinguishing one song from another.

## Cosine Similarity

**Cosine Similarity** measures how similar two song lyric vectors are.

A higher similarity score means that the lyrics are more similar.

The system uses these similarity scores to find the songs closest to the selected song.

## Dataset

The project uses the `spotify_millsongdata.csv` dataset.

During preprocessing, **10,000 songs are sampled** from the dataset to build the recommendation system.

## Project Structure

```text
Music_Recommendation_App/
│
├── src/
│   ├── main.py
│   ├── preprocess.py
│   ├── recommend.py
│   └── spotify_millsongdata.csv
│
├── requirements.txt
├── .gitignore
└── README.md
```

The preprocessing script also creates these files locally:

```text
df_cleaned.pkl
tfidf_matrix.pkl
cosine_sim.pkl
```

These files are excluded from GitHub using `.gitignore`.

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/Nikhil-2026/Music_Recommendation_App.git
```

### 2. Open the Project

```bash
cd Music_Recommendation_App
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

### 4. Activate the Virtual Environment

For Windows:

```powershell
.\venv\Scripts\activate
```

### 5. Install Required Packages

```bash
pip install -r requirements.txt
```

## Running the Project

Go to the `src` folder:

```bash
cd src
```

First run the preprocessing:

```bash
python preprocess.py
```

This creates the required `.pkl` files.

Then start the Streamlit application:

```bash
streamlit run main.py
```

The application will open in the browser.

## Example

After opening the application:

1. Select a song from the dropdown.
2. Click **Recommend Similar Songs**.
3. The application displays the top 5 similar songs along with their artists.

## Important Note

The recommendations are based on **lyrics similarity**.

This project does not use:

* User listening history
* User ratings
* Personal playlists
* Spotify account data

The recommendations are generated only from the song lyrics available in the dataset.

## Author

**Nikhil G.**

GitHub: https://github.com/Nikhil-2026

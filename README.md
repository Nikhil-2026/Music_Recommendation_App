Music Recommendation App 🎵

A simple music recommendation system built using Python. The application recommends songs that are similar to a selected song based on the similarity of their lyrics.

The project uses TF-IDF Vectorization to convert song lyrics into numerical features and Cosine Similarity to find songs with similar lyrics. A Streamlit interface is used to select a song and display the recommendations.

Technologies Used
Python
Pandas
NLTK
Scikit-learn
Joblib
Streamlit
How It Works

The project works in the following steps:

The song dataset is loaded using Pandas.
A sample of 10,000 songs is used for the application.
Song lyrics are cleaned by:
Removing special characters
Converting text to lowercase
Tokenizing the text
Removing English stopwords
TF-IDF is used to convert the cleaned lyrics into numerical vectors.
Cosine Similarity is calculated between the songs.
When a user selects a song, the system finds the most similar songs.
The top 5 similar songs are displayed using Streamlit.
Project Structure
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
Files
preprocess.py

This file handles the preprocessing part of the project.

It:

Loads the dataset
Cleans the lyrics
Removes stopwords
Creates TF-IDF vectors
Calculates cosine similarity
Saves the processed data using Joblib
recommend.py

This file contains the recommendation logic.

It:

Loads the processed data
Finds the selected song
Gets its similarity scores
Sorts the scores
Returns the top 5 similar songs
main.py

This file creates the Streamlit interface.

The user can:

Select a song from the dropdown
Click the recommendation button
View the recommended songs and artists
Setup

Clone the repository:

git clone https://github.com/Nikhil-2026/Music_Recommendation_App.git

Go into the project folder:

cd Music_Recommendation_App

Create a virtual environment:

python -m venv venv

Activate the virtual environment on Windows:

.\venv\Scripts\activate

Install the required packages:

pip install -r requirements.txt
Run the Project

Go to the src folder:

cd src

Run the preprocessing script:

python preprocess.py

This generates the required processed files locally.

Then run the Streamlit application:

streamlit run main.py

The application will open in the browser.

Recommendation Method

The recommendation is based on lyrics similarity.

For example, if a user selects a particular song, the system compares its TF-IDF representation with the representations of other songs and returns the songs with the highest cosine similarity.

This means the recommendations are based on the text of the lyrics, not on the user's listening history or personal preferences.

Dataset

The project uses the spotify_millsongdata.csv dataset.

For this project, 10,000 songs are sampled from the dataset during preprocessing.

Note

The generated .pkl files are not included in the repository because they are excluded through .gitignore. They are generated when preprocess.py is executed.

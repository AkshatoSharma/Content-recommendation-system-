# Content-recommendation-system
Multi-Domain Content Recommendation System

Overview

This project is a content recommendation system that suggests personalized items such as movies, anime, and books based on user preferences.
It applies machine learning techniques (collaborative filtering) to predict what a user might like, using past interactions and similarity-based inference.
The system is built with a focus on simplicity, performance, and user-friendly interaction.

Features

Multi-domain recommendation (Movies, Anime, Books)
AI-driven suggestions using collaborative filtering
User-selectable content type
Interactive web interface built with Streamlit
Easy deployment on Google Colab or local machine

Tech Stack

Component	Technology
Interface	Streamlit
Machine Learning	Scikit-learn, Surprise
Data Handling	Pandas, NumPy
Deployment	LocalTunnel / Ngrok (for Colab)
Datasets
Domain	Dataset	Source
Movies	MovieLens	               MovieLens Small Dataset
Books	  GoodBooks-10K	           GoodBooks-10K
Anime	  Anime Recommendation DB	 Kaggle Anime Dataset

Installation (Recommended: Google Colab)

Install required libraries

!pip install --upgrade --force-reinstall numpy pandas scikit-learn surprise streamlit pyngrok
Download datasets
import zipfile, requests, io
url = "https://files.grouplens.org/datasets/movielens/ml-latest-small.zip"
r = requests.get(url)
z = zipfile.ZipFile(io.BytesIO(r.content))
z.extractall()
Run the Streamlit app
!streamlit run app.py & npx localtunnel --port 8501
Open the generated public URL to interact with the system.

System Workflow

The user selects the content type (Movies, Anime, or Books) and enters their user ID.
The system retrieves the corresponding dataset and rating information.
The collaborative filtering model (KNN-based) is trained on the dataset.
Predictions are made for unseen items.
The top-N recommendations are displayed through a Streamlit interface.

Algorithm

The system uses Collaborative Filtering based on the KNNBasic algorithm from the surprise library.
It computes user-item similarity using cosine or Pearson correlation and predicts ratings for unrated items.
The highest predicted ratings are returned as recommendations.
Example Output
Top 5 Movie Recommendations for User 7:
1. The Shawshank Redemption
2. Inception
3. Pulp Fiction
4. The Dark Knight
5. Interstellar
   
Future Enhancements

Add content-based filtering using genre and metadata
Merge all domains into a unified hybrid recommender
Integrate login and preference-based profiles
Expand datasets to include songs and TV shows
Add analytics and visualization dashboard

Project Structure

📁 MultiDomain-Recommendation-System
│
├── app.py                 # Main Streamlit app
├── ml-latest-small/       # MovieLens dataset
├── anime.csv              # Anime dataset
├── anime_ratings.csv      # Anime ratings
├── books.csv              # Book details
├── book_ratings.csv       # Book ratings
├── requirements.txt       # Dependencies
└── README.md              # Documentation

Evaluation Highlights

Covers multiple recommendation domains
Uses real datasets and machine learning models
Fully interactive web interface
Simple and efficient deployment
Suitable for academic submission or portfolio demonstration

Author
Akshat Sharma
AI/ML Developer | Data Science Enthusiast

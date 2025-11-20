# Vibelytics
A music recommendation engine using clustering and streamlit.

Vibelytics: The Mood-Based Music Recommender

> **"Music is the language of the spirit." – But sometimes, you need an algorithm to translate it.**

## Overview

Welcome to **Vibelytics**, a data science project that looks beyond genre and artist names to understand the "DNA" of a song. 

Most recommendation engines rely on what other people are listening to. **Vibelytics** relies on the audio features of the music itself. By analyzing data points like *danceability, energy, acousticness,* and *valence*, this application groups songs into distinct "Mood Clusters" and allows users to discover music that mathematically matches their current vibe.

## 🚀 Key Features

* **🔍 Search by Song:** Enter a track you love (e.g., "Blinding Lights"), see its audio visualization via a Radar Chart, and get 20 mathematically similar song recommendations.
* **🎛️ "Vibe Dialing":** Don't have a song in mind? No problem. Use the interactive sliders to set your desired Energy, Mood (Valence), and Danceability to generate a custom playlist from scratch.
* **📊 Data Visualization:** Interactive 3D PCA plots and Radar Charts to visualize how songs group together in a multi-dimensional space.
* **🤖 Unsupervised Learning:** Powered by K-Means Clustering to automatically detect and categorize songs into mood groups.

## 🧠 How It Works

This project utilizes **Unsupervised Machine Learning** to find patterns in a dataset of over 32,000 Spotify songs.

1.  **Data Preprocessing:** * Raw audio features (loudness, tempo, etc.) are normalized using `MinMaxScaler` to a 0-1 range to ensure no single feature dominates the model.
2.  **The Elbow Method:** * I used the Elbow Method to determine the optimal number of clusters, resulting in **$k=6$** distinct musical moods.
3.  **K-Means Clustering:**
    * The algorithm grouped songs into 6 clusters, which I interpreted and labeled as:
        * *Chill/Relaxed* 🍃
        * *High Energy/Party* ⚡
        * *Sad/Melancholic* 🌧️
        * *Aggressive/Intense* 🔥
        * *Happy/Pop* 😄
        * *Danceable/Groovy* 💃
4.  **Recommendation Engine:**
    * When you select a song or adjust the sliders, the engine calculates the **Euclidean Distance** between your input and the dataset vectors to find the nearest neighbors (the most similar songs).

## 🛠️ Tech Stack

* **Language:** Python 3.x
* **Web Framework:** Streamlit
* **Data Manipulation:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn (K-Means, PCA, MinMaxScaler)
* **Visualization:** Plotly (Interactive charts), Matplotlib, Seaborn
* **Deployment:** PyNgrok (for tunneling)

## 📸 Screenshots

### 1. The Dashboard & Search
<img width="1919" height="862" alt="image" src="https://github.com/user-attachments/assets/196e180e-8b04-4c4f-bdf1-f48071f214c4" />
<img width="1919" height="854" alt="image" src="https://github.com/user-attachments/assets/7bed12ed-865e-4447-87aa-2ab21d82f3d7" />



### 2. Visualizing Song DNA (Radar Chart)
<img width="1919" height="962" alt="image" src="https://github.com/user-attachments/assets/0b9c788e-d98a-45a8-bf88-519b36ee8914" />


## 💻 How to Run Locally

Follow these steps to get Vibelytics running on your machine:

1.  **Clone the repository**
    ```bash
    git clone [https://github.com/your-username/vibelytics.git](https://github.com/your-username/vibelytics.git)
    cd vibelytics
    ```

2.  **Install dependencies**
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: Ensure pandas, numpy, scikit-learn, matplotlib, seaborn, plotly, streamlit, and pyngrok are installed)*

3.  **Run the Application**
    ```bash
    streamlit run app.py
    ```

4.  **Access the App**
    * The app will open in your default browser at `http://localhost:8501`.

## 🔮 Future Improvements

* **Spotify API Integration:** To allow users to save the generated playlists directly to their Spotify account.
* **Lyrics Analysis:** incorporating NLP (Natural Language Processing) to analyze the sentiment of the lyrics, adding another layer of accuracy to the mood detection.
* **Hybrid Filtering:** Combining audio features with collaborative filtering (user ratings) for even better recommendations.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/your-username/vibelytics/issues).

---

*Built with 🎧 and 🐍 Python by GVS KOUSHIK*

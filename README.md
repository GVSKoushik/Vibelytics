# Vibelytics
A deep learning music classifier and recommendation engine using CNNs and Streamlit.

**Vibelytics: The AI That "Sees" Music**

> **"Talking about music is like dancing about architecture." – Frank Zappa. So, we taught an AI to look at the 'architecture' of sound instead.**

## Overview

Welcome to **Vibelytics**, an end-to-end Deep Learning project that bridges Computer Vision and Audio Analysis.

Traditional music taggers rely on metadata (artist names, year, album). **Vibelytics** listens to the raw audio. By converting sound waves into **Mel Spectrograms** (visual representations of sound), this application treats music genre classification as an image recognition problem. It uses a Convolutional Neural Network (CNN) to predict the genre of an uploaded track and immediately connects to **Spotify** to recommend trending hits that match that vibe.

## 🚀 Key Features

* **🎧 Audio-to-Visual Analysis:** Upload any MP3/WAV file and watch the app generate a real-time Mel Spectrogram, visualizing the "texture" of the sound (bass, treble, tempo) as a heatmap.
* **🧠 Deep Learning Classifier:** Powered by a custom-trained CNN (Convolutional Neural Network) that analyzes the spectrogram to predict the genre with a confidence score.
* **🎵 Smart Recommendations:** Once the genre is identified (e.g., "Jazz" or "Metal"), the app uses the **Spotify API** to fetch and display 5 top-trending tracks in that specific genre.
* **⚡ Instant Deployment:** Built with **Streamlit** and tunneled via **Ngrok**, allowing the app to be accessed from a public URL instantly.

## 🧠 How It Works

This project utilizes **Supervised Deep Learning** trained on the famous **GTZAN Dataset** (1,000 audio tracks across 10 genres).

1.  **Signal Processing (Librosa):**
    * The app loads the audio and extracts a 3-second window.
    * It computes the **Mel Spectrogram**, mapping frequencies to the human hearing scale (Mel scale).
    * Amplitudes are converted to Decibels (dB) to create a high-contrast "image" of the sound.
2.  **The "Eye" of the Model (CNN):**
    * The spectrogram ($128 \times 128$ pixels) is fed into a Sequential CNN model.
    * **Conv2D Layers** scan for features (rhythmic patterns, harmonic lines).
    * **MaxPooling** reduces dimensionality.
    * **Dense Layers** classify the features into one of 10 genres.
3.  **The Recommendation Engine:**
    * The predicted genre tag is sent as a query to the Spotify Web API.
    * Metadata (Album art, Artist, Link) is retrieved and rendered in the UI.

## 🛠️ Tech Stack

* **Language:** Python 3.x
* **Web Framework:** Streamlit
* **Deep Learning:** TensorFlow, Keras (CNN, Conv2D, MaxPool)
* **Audio Processing:** Librosa, NumPy
* **APIs:** Spotipy (Spotify Web API), Kaggle API (Data fetching)
* **Deployment:** PyNgrok (Secure tunneling)

## 📸 Screenshots

### 1. The Upload & Analysis Interface
<img width="1917" height="943" alt="image" src="https://github.com/user-attachments/assets/c6a8f4f7-1085-4310-b6af-7a57ced94721" />

### 2. Spectral Visualization & Results
<img width="1055" height="500" alt="image" src="https://github.com/user-attachments/assets/d532ce7a-3718-4031-8501-16dbd68d2e60" />

## 💻 How to Run (Google Colab)

This project is optimized for Google Colab to leverage GPU acceleration for training.

1.  **Prerequisites**
    * A `kaggle.json` file (for downloading the GTZAN dataset).
    * Spotify Developer Credentials (Client ID & Secret).
    * An Ngrok Auth Token.

2.  **Open the Notebook**
    * Upload the provided `.ipynb` notebook to Google Colab.

3.  **Configure Credentials**
    * Run the first cell to upload `kaggle.json`.
    * In the `%%writefile app.py` cell, replace the placeholders:
        ```python
        CLIENT_ID="YOUR_SPOTIFY_ID"
        CLIENT_SECRET="YOUR_SPOTIFY_SECRET"
        ```
    * In the final cell, replace the Ngrok token:
        ```python
        NGROK_TOKEN="YOUR_NGROK_TOKEN"
        ```

4.  **Run All Cells**
    * The notebook will install dependencies, train the CNN model (approx 15 epochs), and save the model.
    * Finally, it will launch Streamlit in the background.

5.  **Access the App**
    * Click the `public_url` link (ending in `.ngrok-free.app`) generated in the output of the last cell.

## 🔮 Future Improvements

* **Microphone Support:** Implement real-time audio capture so users can hum or play a song directly into the browser.
* **Model Expansion:** Train on a larger dataset (like FMA) to support sub-genres (e.g., "Lo-Fi Beats" instead of just "Pop").
* **Sliding Window Prediction:** Instead of analyzing just one 3-second slice, analyze the whole song and average the predictions for higher accuracy.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check.
---

*Built with 🎧, TensorFlow, and 🐍 Python by GVS KOUSHIK*

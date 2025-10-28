# AI News Summarizer 📰🤖

A simple web application built with Flask and Hugging Face Transformers that summarizes news articles from a URL or from user-provided text.


## Features

* **Summarize by URL:** Enter the URL of any news article, and the app will scrape the text and generate a concise summary.
* **Summarize by Text:** Paste any block of text directly into the text area to get a summary.
* **Simple Web Interface:** A clean and straightforward UI built with Flask and basic HTML/CSS.
* **State-of-the-Art NLP:** Powered by the Hugging Face `transformers` library using the `facebook/bart-large-cnn` model for high-quality summarization.

## 🛠️ Tech Stack

* **Backend:** Python, Flask
* **Machine Learning:** Hugging Face `transformers` (for the `summarization` pipeline)
* **Web Scraping:** `newspaper3k` (to extract article text from URLs)
* **Frontend:** HTML & CSS (served by Flask)
* **Deployment (from Colab):** `pyngrok` (to expose the local Flask app to the internet)

## How It Works

1.  **User Input:** The Flask app presents a web form where the user can paste a text or a news article URL.
2.  **Article Scraping:** If a URL is provided, the `newspaper3k` library is used to download, parse, and extract the full text of the article.
3.  **Summarization:** The extracted (or user-provided) text is fed into the Hugging Face `summarization` pipeline.
4.  **Display:** The generated summary is passed back to the HTML template and displayed to the user.

## 🚀 How to Run (from Google Colab)

This project is designed to be easily run from a Google Colab notebook.

1.  **Install Dependencies:**
    ```python
    !pip install transformers newspaper3k flask pyngrok
    ```

2.  **Create the Flask App (`app.py`):**
    You will need to write the Flask application code into a file. In Colab, you can do this using the `%%writefile app.py` magic command (as seen in the video).

3.  **Create the HTML Template (`templates/index.html`):**
    Similarly, create the `index.html` file in a `templates` directory.
    ```python
    !mkdir templates
    ```
    ```python
    %%writefile templates/index.html
    ```

4.  **Run the App with `ngrok`:**
    Execute the Python script that runs the Flask app and `pyngrok` to create a public URL.
    ```python
    !python app.py
    ```

5.  **Access the App:**
    `pyngrok` will output a public URL (e.g., `http://<hash>.ngrok.io`). Click this link to access your live web application.

## Project Files

* `newssummarizer.ipynb`: The Google Colab notebook containing all the code.
* `app.py`: (Optional, if extracting from notebook) The main Flask application script.
* `templates/index.html`: (Optional, if extracting from notebook) The HTML template for the web UI.
* `README.md`: This file.

# Punjabi-News-Sentiment-Analysis
1. Introduction 
This project focuses on Sentiment Analysis of news articles written in the Punjabi language. In today’s digital era, there is an overwhelming volume of news being published online. Understanding the public sentiment embedded in this content is critical for a variety of domains:
Public Opinion Monitoring: Gauging people’s sentiment toward political events, government actions, or societal issues.
Market Research: Understanding consumer sentiment towards brands, products, or services featured in news articles.
Content Recommendation Systems: Enhancing user experience by promoting articles that align with reader sentiment preferences.
While sentiment analysis has matured significantly for high-resource languages like English, regional languages such as Punjabi face several challenges:
Limited Resources: Lack of pre-trained NLP models and language-specific tools.
Scarcity of Annotated Datasets: Very few publicly available labeled corpora for Punjabi.


Linguistic Complexity: Punjabi has unique grammar, script (Gurmukhi), idioms, and cultural context.
Project Objective
The primary objective is to build a robust system that can:
Read and process Punjabi news articles or headlines.
Extract textual features using language preprocessing techniques.
Classify sentiment into Positive, Negative, or Neutral categories.
Handle nuances of the Punjabi language, including word ordering and vocabulary.
Key Contributions
Manual Dataset Creation: The team manually curated and labeled a dataset from real-world Punjabi news sources.
Machine Learning Pipeline: Text vectorization using TF-IDF and model training using classifiers like Logistic Regression.
Evaluation Metrics: Comprehensive analysis using accuracy, precision, recall, F1-score, and confusion matrix.
Scalability Potential: The system lays the foundation for future use with deep learning models or transformer-based architectures for Punjabi.
This project not only explores technical implementation but also contributes toward inclusive NLP, ensuring lesser-resourced languages like Punjabi are represented in modern AI tools.
# Punjabi News Sentiment Analysis Project

This project contains a full pipeline to scrape news articles, train a sentiment analysis model, and use it in an interactive application.

## Setup

1.  **Create a Project Directory:** Create a folder named `punjabi_news_project` and place all the files from this breakdown inside it.

2.  **Install Dependencies:** Open your terminal or command prompt, navigate to the `punjabi_news_project` directory, and install the required packages using the `requirements.txt` file.
    ```bash
    pip install -r requirements.txt
    ```

3.  **Edit Configuration:** Open `config.py` and carefully fill in the required values, especially:
    * `GOOGLE_API_KEY`
    * `LABELED_DATA_CSV` (the path to your manually labeled dataset)
    * Review other paths and settings to ensure they match your environment.

## How to Run the Pipeline

Execute the scripts in numerical order.

1.  **Scrape Data (Optional):** If you need to scrape new data.
    ```bash
    python 1_scraper.py
    ```
    This will create or append to `punjabi_tribune_nation_selenium_updated.csv`.

2.  **Split Labeled Data:** To create training, validation, and test sets.
    ```bash
    python 2_split_data.py
    ```
    This requires your `punjabi_news_sentiment_labelled_dataset_finall_3june.csv` file (or whatever you named it in `config.py`).

3.  **Tokenize Data:** To prepare the data for the model.
    ```bash
    python 3_tokenize_data.py
    ```
    This creates a `tokenized_dataset` directory.

4.  **Fine-Tune the Model:** To train the XLM-RoBERTa model.
    ```bash
    python 4_fine_tune_model.py
    ```
    This will create the final model in the `punjabi-news-sentiment-xlm-roberta_final` directory.

5.  **Run the Interactive App:** To use your trained model and the Gemini API.
    ```bash
    python main_interactive_app.py
    ```

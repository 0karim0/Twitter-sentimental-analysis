# Twitter Sentiment Analysis

## Overview
This project is an end-to-end Twitter Sentiment Analysis system built using Natural Language Processing (NLP) techniques. The goal is to classify tweets into different sentiment categories (e.g., positive, negative, neutral) using machine learning models.

## Features
- Data collection and preprocessing
- Tokenization and text vectorization (BOW, TF-IDF, Word Embeddings)
- Sentiment classification using SVM
- Model fine-tuning and evaluation
- REST API for real-time predictions using FastAPI
- Deployment-ready setup

## Technologies Used
- **Programming Language:** Python
- **NLP Libraries:** NLTK, spaCy
- **Machine Learning:** Scikit-learn, joblib
- **Web Framework:** FastAPI, Uvicorn
- **Data Handling:** Pandas, NumPy
- **Deployment:** Docker (optional)

## Project Structure
```
Twitter-sentimental-analysis/
│-- data/                      # Dataset files
│-- src/
│   │-- models/                # ML models and inference scripts
│   │-- preprocessing/         # Data cleaning and text processing
│   │-- config.py              # Model configuration
│   │-- app.py                 # FastAPI server
│-- artifacts/                 # Saved models and vectorizers
│-- requirements.txt           # Required dependencies
│-- README.md                  # Project documentation
```

## Installation
1. Clone the repository:
   ```sh
   git clone https://github.com/yourusername/Twitter-sentimental-analysis.git
   cd Twitter-sentimental-analysis
   ```
2. Create a virtual environment and activate it:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```
3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```
4. Download necessary NLP models:
   ```python
   import nltk
   nltk.download('stopwords')
   ```

## Usage
### Train the Model
Run the training script to preprocess data and train the SVM model:
```sh
python src/train.py
```

### Start the API Server
To launch the FastAPI server for real-time predictions:
```sh
uvicorn src.app:app --reload
```

### Make a Prediction
Use an API client like Postman or `curl`:
```sh
curl -X POST "http://127.0.0.1:8000/predict" -H "Content-Type: application/json" -d '{"text": "I love this movie!"}'
```

## Model Fine-Tuning
GridSearchCV is used to fine-tune hyperparameters for optimal model performance.

## Deployment (Optional)
To containerize the application using Docker:
```sh
docker build -t twitter-sentiment .
docker run -p 8000:8000 twitter-sentiment
```

## Contributing
Feel free to open issues or submit pull requests for improvements!

## License
This project is licensed under the MIT License.

## Contact
For any questions, reach out at [your email or GitHub handle].


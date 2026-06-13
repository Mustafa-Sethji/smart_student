# 📚 Smart Student Assistant

Smart Student Assistant is a Streamlit web app that helps students get more out of their study material. Upload a PDF textbook or a photo of a question, and the app extracts the text, processes it through a full machine learning pipeline, and helps you find relevant content, understand difficulty levels, and explore topics automatically.

## ✨ Features

- **PDF & Image Input** — Extract text from PDFs (`pdfplumber`) or scanned question images using OCR (`pytesseract`)
- **Text Preprocessing** — Cleans, tokenizes, and removes stopwords from extracted text
- **Chunking** — Splits book content into overlapping sentence chunks for better context retention
- **TF-IDF Vectorization** — Converts text chunks into numerical feature vectors
- **PCA (Dimensionality Reduction)** — Reduces high-dimensional vectors for faster, more accurate search
- **KNN Similarity Search** — Finds the most relevant chunks/pages for a given question
- **K-Means Clustering** — Automatically groups content into topics/chapters
- **Classification Models** — Logistic Regression, Naive Bayes, SVM, Random Forest, and XGBoost to classify difficulty and subject
- **Exploratory Data Analysis (EDA)** — Visualizes dataset statistics with Matplotlib & Seaborn
- **Model Evaluation** — Accuracy and F1-score reporting for trained classifiers

## 🛠️ Tech Stack

- **Frontend/App:** Streamlit
- **PDF Processing:** pdfplumber
- **OCR:** Tesseract (pytesseract), Pillow
- **ML/Data:** scikit-learn, XGBoost, NumPy, pandas, SciPy
- **Visualization:** Matplotlib, Seaborn

## 📂 Project Structure

```
smart_student/
├── app.py                  # Main Streamlit application
├── core/
│   ├── pdf_reader.py       # Extract text from PDFs
│   ├── ocr.py               # Extract text from images via OCR
│   ├── preprocessor.py      # Text cleaning & tokenization
│   └── chunker.py           # Split text into overlapping chunks
├── models/
│   ├── vectorizer.py        # TF-IDF + PCA
│   ├── similarity.py        # KNN similarity search
│   ├── clustering.py        # K-Means topic clustering
│   └── classifiers.py       # Logistic Regression, Naive Bayes, SVM, Random Forest, XGBoost
├── utils/
│   ├── eda.py                # Exploratory data analysis & plots
│   └── store.py              # Save/load processed data
├── .streamlit/config.toml   # App theme configuration
└── requirements.txt
```

## 🚀 Getting Started

### Prerequisites
- Python 3.9+
- Tesseract OCR installed on your system ([installation guide](https://github.com/tesseract-ocr/tesseract))

### Installation

```bash
git clone https://github.com/<your-username>/smart_student.git
cd smart_student
pip install -r requirements.txt
```

### Run the App

```bash
streamlit run app.py
```

The app will open in your browser at `http://localhost:8501`.

## 📖 How It Works

1. Upload a PDF textbook or an image of a question.
2. The app extracts and preprocesses the text.
3. Text is chunked, vectorized with TF-IDF, and dimensionality-reduced with PCA.
4. KNN finds the most relevant chunks for your query.
5. K-Means clusters content into topics for easier navigation.
6. Classifiers predict difficulty level and subject for extracted content.
7. EDA visualizations summarize the dataset.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

# Daraz Review Analyzer

## Roman Urdu Aspect-Based Sentiment Analysis for Daraz Reviews

Daraz Review Analyzer is a Python-based machine learning project that analyzes Daraz-style customer reviews and predicts sentiment for specific product aspects. It supports **Roman Urdu**, **English**, and **code-mixed text**, which are commonly used in Pakistani online shopping reviews.

The project performs **Aspect-Based Sentiment Analysis (ABSA)**. Instead of giving one sentiment label to the whole review, it identifies different product aspects and predicts sentiment for each aspect separately.

Example:

```text
mobile kharab h lekin cover zabardast hy
```

Expected result:

| Aspect | Sentiment |
|---|---|
| Mobile | Negative |
| Cover | Positive |

This makes the system more useful because one review can contain both positive and negative opinions.

---

## Project Objective

The main objective of this project is to analyze customer feedback in a more detailed way by detecting product aspects and predicting their sentiment.

The system can:

- Read Roman Urdu, English, and code-mixed reviews.
- Clean and normalize review text.
- Detect aspects such as `battery`, `screen`, `delivery`, `quality`, `cover`, `camera`, and `packing`.
- Handle contrast words such as `lekin`, `magar`, `but`, and `however`.
- Predict aspect-wise sentiment as Positive or Negative.
- Display results through a Streamlit web interface.
- Show model performance reports for comparison.

---

## What is Aspect-Based Sentiment Analysis?

Normal sentiment analysis gives one label to the full sentence.

Example:

```text
screen zabardast hai magar battery bekar hai
```

A simple sentiment model may get confused because the sentence contains both positive and negative words.

Aspect-Based Sentiment Analysis handles it like this:

| Aspect | Opinion Word | Sentiment |
|---|---|---|
| Screen | zabardast | Positive |
| Battery | bekar | Negative |

So, the system understands which opinion belongs to which product feature.

---

## Main Features

- Streamlit-based web application.
- Roman Urdu and code-mixed review support.
- Text cleaning and spelling normalization.
- Custom CRF-based aspect extraction.
- Clause-aware context extraction.
- Custom Logistic Regression sentiment classifier.
- Custom Naive Bayes model.
- Custom Feed Forward Neural Network model.
- Custom LSTM model.
- Model performance report.
- Code-mixed stress testing using an additional dataset.

---

## Technologies Used

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Streamlit | Web application interface |
| CSV | Dataset storage |
| Custom CRF | Aspect extraction |
| Custom TF-IDF | Feature extraction |
| Custom Logistic Regression | Sentiment classification |
| Custom Naive Bayes | Model comparison |
| Custom FFNN | Neural model comparison |
| Custom LSTM | Sequential model comparison |
| GitHub | Code hosting |
| Streamlit Cloud | Deployment |



---

## Project Structure

```text
daraz-review-analyzer/
│
├── app.py
├── main.py
├── main_debug.py
│
├── data/
│   └── raw/
│       ├── daraz-dataset1.csv
│       └── daraz-dataset2.csv
│
├── src/
│   ├── corpus.py
│   ├── evaluation.py
│   ├── extraction.py
│   ├── features.py
│   ├── gui.py
│   ├── models_classical.py
│   ├── models_deep.py
│   ├── pos_ner.py
│   ├── preprocessing.py
│   └── test_pos.py
│
├── requirements.txt
├── .gitignore
└── README.md
```

---

## File Explanation

| File/Folder | Description |
|---|---|
| `app.py` | Main Streamlit web app for review analysis and model report |
| `main.py` | Console-based project runner |
| `main_debug.py` | Debug version for testing |
| `data/raw/` | Contains Daraz review datasets |
| `src/preprocessing.py` | Text cleaning, normalization, tokenization, and dataset loading |
| `src/pos_ner.py` | POS tagging, NER, and CRF-based aspect extraction |
| `src/extraction.py` | Clause-aware aspect context extraction |
| `src/features.py` | Custom TF-IDF and sentiment lexicon features |
| `src/models_classical.py` | Custom Naive Bayes and Logistic Regression |
| `src/models_deep.py` | Custom FFNN and LSTM models |
| `src/evaluation.py` | Accuracy, precision, recall, F1-score, and confusion matrix |
| `src/gui.py` | Optional Tkinter desktop GUI |

---

## How the System Works

The system follows this pipeline:

```text
Customer Review
      ↓
Text Cleaning
      ↓
Roman Urdu Normalization
      ↓
Tokenization
      ↓
Aspect Extraction using CRF
      ↓
Clause Splitting
      ↓
Context Extraction
      ↓
Sentiment Prediction
      ↓
Aspect-wise Result
```

Example:

```text
quality achi hai lekin delivery late thi
```

Output:

| Aspect | Sentiment |
|---|---|
| Quality | Positive |
| Delivery | Negative |

The system uses words like `lekin`, `magar`, and `but` to separate different opinions in the same review.

---

## Dataset

The project uses two datasets stored in:

```text
data/raw/
```

### Dataset 1

```text
daraz-dataset1.csv
```

This is the main dataset and may contain:

- Product ID
- Customer Name
- Customer ID
- Date
- Rating
- Spam label
- Reviews
- Sentiment
- Features/aspects

### Dataset 2

```text
daraz-dataset2.csv
```

This dataset is used as an additional code-mixed stress test dataset.

---

## Example Inputs and Outputs

### Example 1

```text
glass khrab h
```

| Aspect | Sentiment |
|---|---|
| Glass | Negative |

### Example 2

```text
delivery late thi product acha tha
```

| Aspect | Sentiment |
|---|---|
| Delivery | Negative |
| Product | Positive |

### Example 3

```text
battery weak hai lekin camera zabardast hai
```

| Aspect | Sentiment |
|---|---|
| Battery | Negative |
| Camera | Positive |

### Example 4

```text
packing achi thi lekin charger kaam nahi kar raha
```

| Aspect | Sentiment |
|---|---|
| Packing | Positive |
| Charger | Negative |

---

## Installation

Clone the repository:

```bash
git clone https://github.com/AliZaidiSyed/daraz-review-analyzer.git
```

Open the project folder:

```bash
cd daraz-review-analyzer
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install requirements:

```bash
pip install -r requirements.txt
```

---

## Run the Streamlit App

Use this command:

```bash
streamlit run app.py
```

The app will open in the browser.

Local URL is usually:

```text
http://localhost:8501
```

---

## Run Other Files

Run console version:

```bash
python main.py
```

Run debug version:

```bash
python main_debug.py
```

Run POS/NER test:

```bash
python -m src.test_pos
```

---




## Requirements

The main requirement is:

```text
streamlit>=1.30.0
```

The project also uses standard Python libraries such as:

- csv
- re
- math
- random
- collections
- difflib
- os
- tkinter
- threading

---



---




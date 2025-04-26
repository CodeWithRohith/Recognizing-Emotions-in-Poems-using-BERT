# Recognizing Emotions in Poems using BERT

## Live Demo  
Run the project directly in Google Colab:  
[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/197I8ut041obXMl5r3UUKK9EmqI69mW2D?usp=sharing)


## Overview
Poetry is often rich in figurative language, metaphors, and abstract ideas, making emotion detection a challenging task. This project addresses this complexity by leveraging **BERT** (Bidirectional Encoder Representations from Transformers) to classify emotions in **450 complex poems**, including Shakespeare-level works, into seven categories:
- **Anger**
- **Disgust**
- **Fear**
- **Joy**
- **Neutral**
- **Surprise**
- **Sadness**

We compared BERT’s performance with simpler baseline models like **Naive Bayes** and **Logistic Regression**, highlighting the challenges and opportunities in applying NLP to literary texts.

---

## Dataset
The project uses the **Kaggle Poem Dataset** ([link](https://www.kaggle.com/datasets/mexwell/poem-dataset)):
- **450 poems** labeled with one of the seven emotions.
- **Imbalance**: Sadness and Fear dominate 60% of the dataset.

### Dataset Split
- **Training Set**: 80%
- **Validation Set**: 10%
- **Test Set**: 10%

---

## Methodology
### Data Preprocessing
Steps to clean and standardize the text:
- Convert text to lowercase.
- Remove punctuation, digits, and extra whitespace.

### Models Used
1. **Baseline Models**:
   - Most Frequent Classifier
   - Logistic Regression (Bag of Words)
   - Multinomial Naive Bayes
2. **Transformer Models**:
   - BERT (Fine-Tuned)
   - DistilBERT (Fine-Tuned)

---

## Results
| **Model**                | **Accuracy (%)** | **Precision (%)** | **Recall (%)** | **F1-Score (%)** |
|--------------------------|------------------|-------------------|----------------|------------------|
| Most Frequent Baseline   | 27.78           | 8.00             | 28.00         | 12.00           |
| Logistic Regression (BoW)| 37.04           | 38.00            | 37.00         | 31.00           |
| Multinomial Naive Bayes  | 41.48           | 23.00            | 41.00         | 30.00           |
| **BERT (Fine-Tuned)**    | **44.44**       | -                | -             | -               |
| DistilBERT (Fine-Tuned)  | 33.33           | -                | -             | -               |

### Analysis
- Fine-tuned BERT achieved the **best accuracy (44.44%)**, slightly outperforming Naive Bayes.
- The contextual complexity of poetry proved challenging even for state-of-the-art models like BERT.

---

## Challenges
1. **Complex Language**: Poetry’s figurative expressions are difficult for models to interpret.
2. **Class Imbalance**: Sadness and Fear dominate the dataset, affecting model performance on other classes.
3. **Fine-Tuning BERT**: Computationally intensive, requiring careful hyperparameter tuning.

---

## Project Structure
Recognizing-Emotions-in-Poems-using-BERT/ │ 

├── data/ # Dataset files (e.g., Kaggle Poem Dataset) 

├── notebooks/ # Jupyter notebooks for data exploration and modeling 

├── src/ # Scripts for preprocessing, training, and evaluation 

├── models/ # Saved BERT model checkpoints 

├── requirements.txt # Python dependencies 

├── README.md # Project documentation (this file) 

└── LICENSE # License file (e.g., MIT License)


---

## Getting Started
### Prerequisites
- Python 3.7+
- Install dependencies:
  ```bash
  pip install -r requirements.txt

## Usage
1. Place the Kaggle Poem Dataset in the data/ folder.
2. Preprocess the dataset:
   python src/preprocess.py
3. Fine-tune BERT:
   python src/train.py
4. Evaluate the model:
   python src/evaluate.py

## Conclusion
This project demonstrates the challenges of applying NLP models like BERT to complex poetic texts. While BERT outperforms baseline models, the intricacies of poetic language reveal limitations in current models, paving the way for future research.




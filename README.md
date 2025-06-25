# Fake_News_Detection_Case_Study
Fake News Detection using Semantic Processing

## 1. Introduction
This project presents a comprehensive solution for fake news detection using Natural Language Processing (NLP) and machine learning. The goal is to classify news articles as either **fake** or **true** based on their semantic structure and linguistic patterns.

## 2. Data Preparation
- Added a `news_label` column: `1` for true news, `0` for fake news.
- Merged true and fake datasets into a single DataFrame (44,940 rows).
- Replaced null values with empty strings.
- Merged `title`, `text`, and `date` into a single `news_text` column.

## 3. Text Preprocessing
- Cleaned text: lowercased, removed punctuation, brackets, and numbers.
- Performed POS tagging and retained only nouns (NN, NNS).
- Lemmatized filtered words.
- Saved cleaned data as `clean_df.csv`.

## 4. Train-Validation Split
- Used `train_test_split` (70% training, 30% validation).
- Training samples: 31,458
- Validation samples: 13,482

## 5. Exploratory Data Analysis (EDA)
- Visualized character lengths of `cleaned_text` and `lemmatized_text`.
- Created word clouds and extracted top 40 words for both true and fake news.
- Identified top unigrams, bigrams, and trigrams.
- Found clear linguistic differences between true (structured) and fake (emotional) content.

## 6. Feature Extraction
- Used **Word2Vec (Google News 300)** embeddings to convert text into 300D vectors.
- Captured semantic relationships between words.

## 7. Model Training and Evaluation

| Model               | Accuracy (%) | Precision (%) | Recall (%) | F1-Score (%) |
|--------------------|--------------|----------------|-------------|---------------|
| Logistic Regression| **95.99**     | 95.16          | **96.48**   | **95.82**     |
| Decision Tree      | 89.23         | 90.29          | 86.71       | 88.46         |
| Random Forest      | 95.54         | **95.55**      | 95.06       | 95.31         |

## 8. Conclusion ✅
Both Logistic Regression and Random Forest performed well, with Logistic Regression slightly outperforming in **F1-score** and **recall**, making it the top model. We prioritized F1-score due to the need to minimize both false positives and false negatives.

### 🔍 Final Verdict
**Logistic Regression + Word2Vec** embeddings provided the best trade-off between accuracy, simplicity, and generalization — making it ideal for real-world deployment.

---

## 👤 Author
**Shashidhar Pattar**  
[GitHub: shashidharpattar007](https://github.com/shashidharpattar007)

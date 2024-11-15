# CS539-Social-Media-Mining-Project
# Identification and Classification of False News

## Overview
This repository contains the code and resources for the study **"Identification and Classification of False News"**. This project explores identifying fake news using textual features and network-based metrics derived from the **PolitiFact dataset**.

## Dataset
The study leverages the **PolitiFact dataset** from Arizona State University, which includes:
- **News Content**: Real and fake news articles with metadata.
- **User Interactions**: Engagement patterns between users and news articles.
- **Social Network Data**: Relationships between users in the form of a graph.

### Dataset Components:
1. **News Content**:
   - JSON files: `FakeNewsContent` and `RealNewsContent`.
   - Fields: `headline`, `body_text`, `top_img`, `publish_date`, `source`, `authors`.

2. **Identifiers**:
   - `News.txt`: Maps news IDs to articles.
   - `User.txt`: Lists anonymized user IDs.

3. **Interactions**:
   - `PolitiFactNewsUser.txt`: User-news interactions (news_id, user_id, num_shares).
   - `PolitiFactUserUser.txt`: Follower-followee relationships.

## Features
### Textual Features
- Word counts in titles and body.
- Sentiment analysis scores (positive, neutral, negative).
- Number of authors listed.
- Unique user shares for real and fake news.

### Network Features
- **Average Clustering Coefficient**: Measures the likelihood of users forming tightly connected communities.
- **Average Eigenvector Centrality**: Captures user influence in the network.

## Methodology
1. **Data Preprocessing**:
   - Text cleaning: Removal of HTML tags, special characters, and stopwords.
   - Tokenization and lemmatization.
   - Handling missing data via imputation or exclusion.

2. **Feature Engineering**:
   - Extracted both textual and network-based features.
   - Consolidated data into structured CSV files for easier manipulation:
     - `News_User.csv`
     - `User_User.csv`
     - `JSON_News.csv`

3. **Machine Learning Models implemented**:
   - Random Forest
   - Logistic Regression
   - Support Vector Machine (SVM)
   - Decision Tree
   - Naive Bayes

4. **Evaluation Metrics**:
   - Accuracy, Precision, Recall, and F1 Score.

## Results
- **Best Performing Models**:
  - Random Forest: Accuracy = 77.9%, F1 Score = 0.756.
  - Logistic Regression: Accuracy = 75.0%, F1 Score = 0.739.
- Random Forest demonstrated the best balance between precision and recall, followed closely by Logistic Regression.

## Project Structure
├── data/
│   ├── FakeNewsContent/          # JSON files for fake news
│   ├── RealNewsContent/          # JSON files for real news
│   ├── News.txt                  # News ID mapping
│   ├── User.txt                  # User ID mapping
│   ├── PolitiFactNewsUser.txt    # User-news interactions
│   ├── PolitiFactUserUser.txt    # User-user relationships
│   └── FinalFeatures.csv         # Consolidated features for ML models
├── src/
│   ├── data_preprocessing.py     # Script for data cleaning and preprocessing
│   ├── feature_engineering.py    # Script for extracting features
│   ├── model_training.py         # Script for model training and evaluation
│   ├── utils.py                  # Utility functions
│   └── visualization.py          # Visualization of results
├── notebooks/
│   └── exploratory_analysis.ipynb # EDA notebook
├── results/
│   ├── stratified_kfold_results.csv # Results of Stratified K-Fold Cross Validation
│   ├── hyperparameter_tuning.csv   # Results of Hyperparameter Tuning
│   └── model_comparison.png        # Comparison chart of model performance
├── requirements.txt              # Required Python libraries
├── README.md                     # Project documentation
└── LICENSE                       # License file


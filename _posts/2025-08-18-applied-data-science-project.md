---
layout: post
author: Siti Denielle 
title: "Applied Data Science Project Documentation"
categories: ITD214
---
## Project Background
This project focuses on analyzing Sephora customer product reviews to understand insights on product sentiment and customer satisfaction. This analysis aims to uncover key drivers of positive and negative reviews.

## Work Accomplished
Data Cleaning & Preparation



### Data Preparation
Combined multiple datasets of Sephora reviews from 2021–2022 into a single dataset.
Selected only relevant columns: stars, text, pid, uid, product_name, brand_name.
Removed neutral reviews and kept only positive and negative labels for binary classification.
Standardized text:
Lowercased all text.
Removed stopwords and common product-related words (custom stopwords).
Removed punctuation and special characters to reduce noise.
### Modelling
Feature Engineering
Converted review text into TF-IDF features with unigrams, bigrams, and trigrams.
Added domain-specific stopwords to remove uninformative words like “product”, “face”, “makeup”.
Combined text and numeric features for a richer representation of review sentiment.
Baseline model: Logistic Regression using only TF-IDF features.
Addressed class imbalance with SMOTE oversampling to focus on negative reviews.
Explored advanced modeling (DistilBERT embeddings)

### Evaluation
Evaluated using precision, recall, F1-score, and confusion matrix.
Metrics for final Logistic Regression with TF-IDF + SMOTE:
Negative class (0): F1-score ~0.81, Recall ~0.90
Positive class (1): F1-score ~0.97, Recall ~0.96
Achieved balanced performance, with improved detection of negative reviews for business objective insights.
Compared with DistilBERT embeddings: selected TF-IDF + LR with SMOTE for full prediction due to faster training and decent accuracy.

## Recommendation and Analysis
Predicted sentiment for all reviews in the dataset using the selected model.
Aggregated results per product to calculate:
Identified low-performing products (high number of reviews but low positive ratio).
Extracted top negative phrases per product (after removing product names and stopwords) for actionable insights.

## AI Ethics
Discuss the potential data science ethics issues (privacy, fairness, accuracy, accountability, transparency) in your project. 

Privacy: Customer reviews are anonymized, but care must be taken not to expose personally identifiable information. Fairness: Models must avoid bias against certain product categories or customer groups. Accuracy: Sentiment models can misinterpret sarcasm or context; continuous validation is needed. Accountability: Sephora must ensure decisions are not solely based on AI outputs. Transparency: Clearly communicate to stakeholders how sentiment insights are derived from reviews.
## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
https://github.com/SitiDenielle/itd214_proj

# DS605 Lab 6 — Image and Text Feature Extraction and Classification

## Course

DS605: Fundamentals of Machine Learning

## Objective

This project converts raw image and text data into numerical feature
representations and applies traditional machine-learning models for
classification.

The project contains:

- Part A: Asphalt crack image feature extraction and classification
- Part B: Email spam text vectorization and classification
- Part C: Representation improvement and comparison

---

## Datasets

### Image Dataset

Asphalt Crack Dataset containing:

- 200 crack images
- 200 non-crack images
- 400 images in total

### Text Dataset

Email Spam Classification Dataset containing 5,172 email records.

The supplied CSV contains an email identifier, a binary `Prediction`
column, and a 3,000-word frequency representation.

---

# Part A — Image Feature Extraction and Classification

## Preprocessing

The image pipeline performs:

1. Image loading using OpenCV
2. Dimension and channel inspection
3. Resizing to 128 × 128
4. Grayscale conversion

## Extracted Features

Numerical features include:

- Mean brightness
- Brightness standard deviation
- Median brightness
- Contrast
- Minimum intensity
- Maximum intensity
- Dark-pixel ratio
- Bright-pixel ratio
- Intensity percentiles
- Canny edge count
- Canny edge density

## Machine-Learning Models

The following traditional classifiers were evaluated:

- Logistic Regression
- Random Forest
- Support Vector Machine (SVM)

## Evaluation Metrics

- Accuracy
- Precision
- Recall
- F1-score
- Confusion matrix
- Training time
- Prediction time

---

# Part B — Email Spam Classification

## Preprocessing

Basic text cleaning was applied before vectorization.

The supplied email dataset uses the `Prediction` column as the
binary target.

Because the supplied file contains a 3,000-word frequency matrix
rather than raw email message text, text-like documents were
reconstructed from the supplied word-frequency representation before
applying the required vectorization experiments.

## Text Representations

Two representations were compared:

### CountVectorizer

Converts email documents into word-count vectors.

### TF-IDF

Converts email documents into TF-IDF weighted vectors.

## Classifier

Logistic Regression was trained using both representations.

## Comparison

The representations were compared using:

- Number of generated features
- Accuracy
- Precision
- Recall
- F1-score
- Training time
- Prediction time

---

# Part C — Representation Improvement

Two representation improvements were investigated.

## Image Improvement

Canny edge thresholds were changed from:

Original:

`100, 200`

Improved:

`50, 150`

The original and modified feature representations were evaluated
using the same traditional classifiers.

## Text Improvement

The TF-IDF representation was modified using:

- Unigrams and bigrams
- `min_df=2`
- `max_df=0.95`
- English stop-word handling

The original and improved representations were compared using
classification performance, feature dimensionality, and computation
time.

---

# Project Workflow

```text
Raw Image/Text
      ↓
Preprocessing
      ↓
Feature Extraction / Vectorization
      ↓
Train-Test Split
      ↓
Traditional ML Model
      ↓
Evaluation
      ↓
Representation Improvement
      ↓
Comparison
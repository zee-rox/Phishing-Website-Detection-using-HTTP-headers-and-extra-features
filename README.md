# Phishing-Website-Detection-using-HTTP-headers-and-extra-features

This project aims to develop a machine learning model to detect phishing websites based on HTTP headers and other features. Phishing websites are malicious websites designed to mimic legitimate ones to steal user data like passwords or credit card information. Detecting such websites is crucial for online security.

## Data
The code utilizes various features extracted from website headers and additional data to identify phishing attempts. Here's a breakdown of the features:

HTTP Headers: These headers contain information about the website's server, security settings, and content type. Examples include Content-Security-Policy, Strict-Transport-Security, and X-Frame-Options.
Extra Features: The code also considers features like website traffic, URL length, presence of anchor tags, and redirection presence. These features can provide clues about the website's legitimacy.
The target variable is labeled as 'label', indicating whether a website is phishing (-1) or legitimate (1).

## Method
The code employs a machine learning approach called Random Forest. This algorithm works by creating multiple decision trees, each making predictions based on a random subset of features.

For evaluation, the code uses several metrics:

Accuracy: Ratio of correctly classified websites (phishing and legitimate)
F1 Score: Harmonic mean of precision and recall, accounting for both metrics.
Precision: Proportion of correctly predicted phishing websites among all predicted phishes.
Recall: Proportion of correctly identified phishing websites out of all actual phishing websites.
The code performs stratified K-fold cross-validation to assess the model's generalizability. This technique splits the data into multiple folds, trains the model on each fold with different data combinations, and evaluates its performance on the remaining unseen fold.

## Results

Performance on Dataset A:
```
              precision    recall  f1-score   support

          -1       0.99      0.99      0.99      8992
           1       0.99      0.99      0.99      9060
    accuracy                           0.99     18052
   macro avg       0.99      0.99      0.99     18052   
weighted avg       0.99      0.99      0.99     18052
```

Performance on Dataset B:
```
              precision    recall  f1-score   support
          -1       1.00      1.00      1.00      9785

    accuracy                           1.00      9785
   macro avg       1.00      1.00      1.00      9785   
weighted avg       1.00      1.00      1.00      9785
```

The code reports the model's performance on both the training and testing sets from Dataset A. It then evaluates the model's effectiveness on unseen data from Dataset B.

Training and Testing Performance: The code calculates Accuracy, F1 Score, Precision, and Recall for both the training and testing datasets. This helps understand how well the model learns from the training data and generalizes to unseen data.

Unseen Data Performance: The model is applied to Dataset B, which it hasn't encountered during training. This demonstrates the model's ability to detect phishing websites in real-world scenarios with potentially different characteristics.

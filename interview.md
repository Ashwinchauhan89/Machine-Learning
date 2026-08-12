# 💼 Machine Learning & Deep Learning Interview Questions


> A curated collection of the most frequently asked **Machine Learning**, **Deep Learning**, **Data Science**, and **AI** interview questions with concise answers.

---

# 📑 Table of Contents

* Machine Learning Basics
* Supervised & Unsupervised Learning
* Regression
* Classification
* Model Evaluation
* Deep Learning
* Neural Networks
* CNN
* RNN & LSTM
* Transformers
* Scikit-learn
* TensorFlow & PyTorch
* Coding & Practical Questions

---

# 🤖 Machine Learning Basics

## 1. What is Machine Learning?

Machine Learning is a subset of Artificial Intelligence that enables computers to learn patterns from data and make predictions without being explicitly programmed.

---

## 2. What are the types of Machine Learning?

* Supervised Learning
* Unsupervised Learning
* Semi-Supervised Learning
* Reinforcement Learning

---

## 3. Difference between AI, ML, and DL?

| AI                  | ML               | DL                        |
| ------------------- | ---------------- | ------------------------- |
| Broad field         | Subset of AI     | Subset of ML              |
| Mimics intelligence | Learns from data | Uses deep neural networks |

---

## 4. What is Overfitting?

Overfitting occurs when a model memorizes the training data and performs poorly on unseen data.

**Solution**

* More data
* Regularization
* Dropout
* Cross Validation

---

## 5. What is Underfitting?

Underfitting happens when a model is too simple to capture the underlying patterns in the data.

---

## 6. What is Bias and Variance?

* **Bias:** Error due to overly simple assumptions.
* **Variance:** Error due to excessive sensitivity to training data.

---

## 7. What is Feature Engineering?

The process of creating, selecting, or transforming input variables to improve model performance.

---

## 8. What is Feature Scaling?

Scaling numerical features to a common range using methods like StandardScaler or MinMaxScaler.

---

## 9. Why is Train-Test Split important?

It evaluates how well a model generalizes to unseen data and helps prevent overfitting.

---

## 10. What is Cross Validation?

Cross Validation divides the dataset into multiple folds to obtain a more reliable estimate of model performance.

---

# 📈 Regression

## 11. What is Linear Regression?

A supervised learning algorithm used to predict continuous numerical values.

---

## 12. What is Logistic Regression?

Despite its name, Logistic Regression is a classification algorithm used for binary classification problems.

---

## 13. Difference between Regression and Classification?

| Regression                 | Classification          |
| -------------------------- | ----------------------- |
| Predicts continuous values | Predicts categories     |
| Example: House Price       | Example: Spam Detection |

---

# 🌳 Decision Trees & Ensemble Learning

## 14. What is a Decision Tree?

A tree-based model that splits data into branches based on feature values.

---

## 15. What is Random Forest?

An ensemble of multiple Decision Trees that improves accuracy and reduces overfitting.

---

## 16. What is Bagging?

Bagging trains multiple models independently and combines their predictions.

---

## 17. What is Boosting?

Boosting trains models sequentially, with each new model correcting previous errors.

---

# 🎯 Model Evaluation

## 18. What is Accuracy?

Accuracy is the percentage of correctly classified samples.

```
Accuracy = Correct Predictions / Total Predictions
```

---

## 19. What is Precision?

Precision measures how many predicted positive cases are actually positive.

```
Precision = TP / (TP + FP)
```

---

## 20. What is Recall?

Recall measures how many actual positive cases are correctly identified.

```
Recall = TP / (TP + FN)
```

---

## 21. What is F1 Score?

The harmonic mean of Precision and Recall.

---

## 22. What is a Confusion Matrix?

A table that summarizes True Positives, False Positives, True Negatives, and False Negatives.

---

## 23. What is ROC-AUC?

ROC-AUC evaluates how well a classifier distinguishes between classes across different thresholds.

---

# 🧠 Deep Learning

## 24. What is Deep Learning?

Deep Learning is a subset of Machine Learning that uses multi-layer neural networks to learn complex patterns from data.

---

## 25. What is an Artificial Neural Network (ANN)?

An ANN consists of interconnected neurons organized into input, hidden, and output layers.

---

## 26. What are Activation Functions?

Functions that introduce non-linearity into neural networks.

Examples:

* ReLU
* Sigmoid
* Tanh
* Softmax

---

## 27. What is Backpropagation?

An algorithm that computes gradients and updates weights to minimize the loss function.

---

## 28. What is Gradient Descent?

An optimization algorithm that minimizes the loss function by updating model parameters iteratively.

---

# 📸 CNN

## 29. Why are CNNs used?

CNNs automatically extract spatial features from images, making them ideal for computer vision tasks.

---

## 30. What is Pooling?

Pooling reduces feature map dimensions while retaining important information.

---

## 31. Difference between CNN and ANN?

| ANN                   | CNN                |
| --------------------- | ------------------ |
| Fully Connected       | Convolution Layers |
| Best for Tabular Data | Best for Images    |

---

# 🔄 RNN & LSTM

## 32. What is an RNN?

A Recurrent Neural Network processes sequential data by maintaining information from previous inputs.

---

## 33. Why is LSTM better than RNN?

LSTM solves the vanishing gradient problem using memory cells and gating mechanisms, allowing it to learn long-term dependencies.

---

# 🤖 Transformers

## 34. What is Attention?

Attention allows a model to focus on the most relevant parts of the input when making predictions.

---

## 35. What is a Transformer?

A neural network architecture that relies entirely on attention mechanisms, making it highly effective for NLP and vision tasks.

---

## 36. What is GPT?

GPT (Generative Pre-trained Transformer) is a Transformer-based Large Language Model designed for text generation.

---

# 🔥 TensorFlow & PyTorch

## 37. Difference between TensorFlow and PyTorch?

| TensorFlow              | PyTorch           |
| ----------------------- | ----------------- |
| Static & Dynamic Graphs | Dynamic Graph     |
| Production Ready        | Research Friendly |
| Keras Integration       | Pythonic API      |

---

## 38. What is a Tensor?

A multi-dimensional array used to store and process data in deep learning frameworks.

---

## 39. What is a DataLoader?

A utility that loads datasets efficiently in mini-batches during training.

---

## 40. What is an Epoch?

One complete pass through the entire training dataset.

---

## 41. What is Batch Size?

The number of training samples processed before updating the model weights.

---

## 42. What is Learning Rate?

A hyperparameter that controls the step size during optimization.

---

# 🧪 Practical Questions

## 43. Why normalize data?

Normalization helps algorithms converge faster and improves model performance.

---

## 44. Why shuffle data?

Shuffling prevents the model from learning the order of the data and reduces bias.

---

## 45. How do you handle missing values?

* Remove rows/columns
* Mean or median imputation
* Most frequent value
* Predictive imputation

---

## 46. How do you prevent overfitting?

* More data
* Cross Validation
* Regularization
* Early Stopping
* Dropout
* Data Augmentation

---

## 47. What is Hyperparameter Tuning?

The process of finding the best model configuration using techniques like Grid Search or Random Search.

---

## 48. What is Transfer Learning?

Reusing a pre-trained model on a new task to reduce training time and improve performance.

---

## 49. What is Data Augmentation?

Generating additional training samples by applying transformations such as flipping, rotating, or cropping images.

---

## 50. What is the Machine Learning Pipeline?

```text
Collect Data
      ↓
Clean Data
      ↓
EDA
      ↓
Feature Engineering
      ↓
Train/Test Split
      ↓
Model Training
      ↓
Evaluation
      ↓
Hyperparameter Tuning
      ↓
Deployment
```

---

# 🚀 Bonus Interview Tips

* Understand the intuition behind algorithms, not just their APIs.
* Be prepared to discuss trade-offs between models.
* Explain evaluation metrics and when to use them.
* Practice implementing algorithms in Python.
* Build end-to-end ML projects and showcase them on GitHub.

---

## ⭐ If you found this interview guide helpful, consider starring the repository! - Ashwin Chauhan

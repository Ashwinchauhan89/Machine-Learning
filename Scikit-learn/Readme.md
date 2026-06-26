# 🤖 Scikit-learn Cheat Sheet

<p align="center">
  <img src="https://scikit-learn.org/stable/_static/scikit-learn-logo-small.png" width="280">
</p>

> A quick reference guide for Machine Learning using **Scikit-learn**.

---

# 📦 Installation

```bash
pip install scikit-learn
```

Check Version

```python
import sklearn

print(sklearn.__version__)
```

---

# 📌 Import Libraries

```python
import numpy as np
import pandas as pd

from sklearn.model_selection import train_test_split
from sklearn.preprocessing import StandardScaler
from sklearn.preprocessing import MinMaxScaler
from sklearn.preprocessing import LabelEncoder
from sklearn.preprocessing import OneHotEncoder

from sklearn.metrics import accuracy_score
from sklearn.metrics import confusion_matrix
from sklearn.metrics import classification_report

from sklearn.pipeline import Pipeline
```

---

# 📂 Load Dataset

```python
import pandas as pd

df = pd.read_csv("data.csv")

X = df.drop("target", axis=1)

y = df["target"]
```

---

# ✂️ Train Test Split

```python
X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)
```

---

# 🔄 Feature Scaling

### StandardScaler

```python
scaler = StandardScaler()

X_train = scaler.fit_transform(X_train)

X_test = scaler.transform(X_test)
```

### MinMaxScaler

```python
scaler = MinMaxScaler()

X_train = scaler.fit_transform(X_train)

X_test = scaler.transform(X_test)
```

---

# 🏷 Label Encoding

```python
encoder = LabelEncoder()

y = encoder.fit_transform(y)
```

---

# 🔥 One Hot Encoding

```python
encoder = OneHotEncoder()

encoded = encoder.fit_transform(df[["Gender"]])
```

---

# 📈 Linear Regression

```python
from sklearn.linear_model import LinearRegression

model = LinearRegression()

model.fit(X_train, y_train)

pred = model.predict(X_test)
```

---

# 📉 Logistic Regression

```python
from sklearn.linear_model import LogisticRegression

model = LogisticRegression()

model.fit(X_train, y_train)

pred = model.predict(X_test)
```

---

# 🌳 Decision Tree

```python
from sklearn.tree import DecisionTreeClassifier

model = DecisionTreeClassifier()

model.fit(X_train, y_train)
```

---

# 🌲 Random Forest

```python
from sklearn.ensemble import RandomForestClassifier

model = RandomForestClassifier()

model.fit(X_train, y_train)
```

---

# 🚀 Support Vector Machine

```python
from sklearn.svm import SVC

model = SVC()

model.fit(X_train, y_train)
```

---

# 👨‍👩‍👧 K-Nearest Neighbors

```python
from sklearn.neighbors import KNeighborsClassifier

model = KNeighborsClassifier(n_neighbors=5)

model.fit(X_train, y_train)
```

---

# 🧠 Naive Bayes

```python
from sklearn.naive_bayes import GaussianNB

model = GaussianNB()

model.fit(X_train, y_train)
```

---

# ⚡ Gradient Boosting

```python
from sklearn.ensemble import GradientBoostingClassifier

model = GradientBoostingClassifier()

model.fit(X_train, y_train)
```

---

# 🚀 AdaBoost

```python
from sklearn.ensemble import AdaBoostClassifier

model = AdaBoostClassifier()

model.fit(X_train, y_train)
```

---

# 🌟 XGBoost (External)

```python
from xgboost import XGBClassifier

model = XGBClassifier()

model.fit(X_train, y_train)
```

---

# 📊 Clustering

## KMeans

```python
from sklearn.cluster import KMeans

model = KMeans(n_clusters=3)

model.fit(X)
```

---

## DBSCAN

```python
from sklearn.cluster import DBSCAN

model = DBSCAN()

labels = model.fit_predict(X)
```

---

## Agglomerative Clustering

```python
from sklearn.cluster import AgglomerativeClustering

model = AgglomerativeClustering()

labels = model.fit_predict(X)
```

---

# 📉 Dimensionality Reduction

## PCA

```python
from sklearn.decomposition import PCA

pca = PCA(n_components=2)

X_new = pca.fit_transform(X)
```

---

# 🔍 Feature Selection

```python
from sklearn.feature_selection import SelectKBest
from sklearn.feature_selection import chi2

selector = SelectKBest(score_func=chi2, k=5)

X_new = selector.fit_transform(X, y)
```

---

# 🎯 Cross Validation

```python
from sklearn.model_selection import cross_val_score

scores = cross_val_score(
    model,
    X,
    y,
    cv=5
)

print(scores.mean())
```

---

# 🔎 Grid Search

```python
from sklearn.model_selection import GridSearchCV

params = {
    "max_depth":[3,5,7],
    "criterion":["gini","entropy"]
}

grid = GridSearchCV(
    DecisionTreeClassifier(),
    params,
    cv=5
)

grid.fit(X_train, y_train)

print(grid.best_params_)
```

---

# 🎲 Random Search

```python
from sklearn.model_selection import RandomizedSearchCV

search = RandomizedSearchCV(
    model,
    param_distributions=params,
    n_iter=10
)
```

---

# 📈 Model Evaluation

## Accuracy

```python
accuracy_score(y_test, pred)
```

---

## Confusion Matrix

```python
confusion_matrix(y_test, pred)
```

---

## Classification Report

```python
classification_report(y_test, pred)
```

---

## Precision

```python
from sklearn.metrics import precision_score

precision_score(y_test, pred)
```

---

## Recall

```python
from sklearn.metrics import recall_score

recall_score(y_test, pred)
```

---

## F1 Score

```python
from sklearn.metrics import f1_score

f1_score(y_test, pred)
```

---

## ROC AUC

```python
from sklearn.metrics import roc_auc_score

roc_auc_score(y_test, pred)
```

---

# 📉 Regression Metrics

```python
from sklearn.metrics import mean_squared_error
from sklearn.metrics import mean_absolute_error
from sklearn.metrics import r2_score

mse = mean_squared_error(y_test, pred)

mae = mean_absolute_error(y_test, pred)

r2 = r2_score(y_test, pred)
```

---

# 💾 Save Model

```python
import joblib

joblib.dump(model, "model.pkl")
```

---

# 📂 Load Model

```python
model = joblib.load("model.pkl")
```

---

# 🔥 Pipeline

```python
pipeline = Pipeline([
    ("scaler", StandardScaler()),
    ("model", RandomForestClassifier())
])

pipeline.fit(X_train, y_train)
```

---

# 🛠 Useful Utilities

```python
model.predict(X)

model.predict_proba(X)

model.score(X_test, y_test)

model.get_params()

model.set_params()
```

---

# 📚 Common Algorithms

| Task | Algorithm |
|------|-----------|
| Regression | Linear Regression |
| Classification | Logistic Regression |
| Classification | SVM |
| Classification | Decision Tree |
| Classification | Random Forest |
| Classification | Naive Bayes |
| Classification | KNN |
| Classification | Gradient Boosting |
| Clustering | KMeans |
| Clustering | DBSCAN |
| Clustering | Agglomerative |
| Dimensionality Reduction | PCA |
| Feature Selection | SelectKBest |

---

# 📝 Best Practices

✅ Handle Missing Values

✅ Encode Categorical Features

✅ Scale Numerical Features

✅ Split Train/Test Data

✅ Use Cross Validation

✅ Tune Hyperparameters

✅ Save Trained Model

✅ Build Pipelines

---

# 📖 Learning Resources

- 🌐 Official Docs: https://scikit-learn.org/stable/
- 📘 User Guide: https://scikit-learn.org/stable/user_guide.html
- 🎓 Tutorials: https://scikit-learn.org/stable/tutorial/

---

# ⭐ If this repository helped you, don't forget to Star it!

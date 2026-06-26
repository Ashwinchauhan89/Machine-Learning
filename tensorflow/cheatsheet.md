# 🧠 TensorFlow Cheat Sheet

<p align="center">
  <img src="https://www.tensorflow.org/images/tf_logo_social.png" width="280">
</p>

> A quick reference guide for **TensorFlow & Keras** to build Deep Learning and Machine Learning models.

---

# 📦 Installation

```bash
pip install tensorflow
```

Check Installation

```python
import tensorflow as tf

print(tf.__version__)
print("GPU Available:", len(tf.config.list_physical_devices('GPU')) > 0)
```

---

# 📌 Import Libraries

```python
import tensorflow as tf
import numpy as np
import matplotlib.pyplot as plt

from tensorflow import keras
from tensorflow.keras import layers
```

---

# 🔢 Create Tensors

```python
tf.constant([1,2,3])

tf.Variable([1,2,3])

tf.zeros((3,3))

tf.ones((2,2))

tf.random.normal((2,3))

tf.random.uniform((2,3))

tf.range(10)

tf.eye(3)
```

---

# 📏 Tensor Information

```python
tensor.shape

tensor.dtype

tensor.ndim

tf.rank(tensor)

tf.size(tensor)
```

---

# 🔄 Tensor Operations

```python
tf.add(a,b)

tf.subtract(a,b)

tf.multiply(a,b)

tf.divide(a,b)

tf.matmul(a,b)

tf.reduce_sum(a)

tf.reduce_mean(a)

tf.reduce_max(a)

tf.reduce_min(a)
```

---

# 🔀 Reshape Tensor

```python
tf.reshape(x,(2,3))

tf.transpose(x)

tf.expand_dims(x,0)

tf.squeeze(x)

tf.concat([a,b],axis=0)

tf.stack([a,b],axis=0)
```

---

# 🔥 Convert NumPy

NumPy → Tensor

```python
tf.convert_to_tensor(array)
```

Tensor → NumPy

```python
tensor.numpy()
```

---

# 🚀 GPU

```python
print(tf.config.list_physical_devices("GPU"))
```

---

# 🧠 Sequential Model

```python
model = keras.Sequential([
    layers.Dense(128, activation="relu"),
    layers.Dense(64, activation="relu"),
    layers.Dense(10, activation="softmax")
])
```

---

# 🏗 Functional API

```python
inputs = keras.Input(shape=(784,))

x = layers.Dense(128, activation="relu")(inputs)

outputs = layers.Dense(10, activation="softmax")(x)

model = keras.Model(inputs, outputs)
```

---

# 📦 Common Layers

```python
layers.Dense()

layers.Conv2D()

layers.MaxPooling2D()

layers.Flatten()

layers.Dropout()

layers.BatchNormalization()

layers.LSTM()

layers.GRU()

layers.Embedding()

layers.GlobalAveragePooling2D()
```

---

# ⚡ Activation Functions

```python
relu

sigmoid

softmax

tanh

elu

selu

gelu

swish
```

---

# 🎯 Compile Model

```python
model.compile(
    optimizer="adam",
    loss="sparse_categorical_crossentropy",
    metrics=["accuracy"]
)
```

---

# 🚀 Train Model

```python
history = model.fit(
    X_train,
    y_train,
    epochs=10,
    batch_size=32,
    validation_split=0.2
)
```

---

# 📊 Evaluate Model

```python
model.evaluate(X_test, y_test)
```

---

# 🔍 Prediction

```python
predictions = model.predict(X_test)

predicted_class = tf.argmax(predictions, axis=1)
```

---

# 💾 Save Model

```python
model.save("model.keras")
```

or

```python
model.save("model.h5")
```

---

# 📂 Load Model

```python
model = keras.models.load_model("model.keras")
```

---

# 🖼 Image Data Generator

```python
train_ds = tf.keras.utils.image_dataset_from_directory(
    "dataset/",
    image_size=(224,224),
    batch_size=32
)
```

---

# 🔄 Data Augmentation

```python
augmentation = keras.Sequential([
    layers.RandomFlip(),
    layers.RandomRotation(0.2),
    layers.RandomZoom(0.2),
    layers.RandomContrast(0.2)
])
```

---

# 📸 CNN Example

```python
model = keras.Sequential([
    layers.Conv2D(32,3,activation="relu"),
    layers.MaxPooling2D(),

    layers.Conv2D(64,3,activation="relu"),
    layers.MaxPooling2D(),

    layers.Flatten(),

    layers.Dense(128,activation="relu"),

    layers.Dense(10,activation="softmax")
])
```

---

# 📝 RNN / LSTM

```python
model = keras.Sequential([
    layers.LSTM(64),

    layers.Dense(1)
])
```

---

# 🤖 GRU

```python
model = keras.Sequential([
    layers.GRU(128),

    layers.Dense(1)
])
```

---

# 📚 Transfer Learning

```python
base_model = tf.keras.applications.MobileNetV2(
    weights="imagenet",
    include_top=False
)

base_model.trainable = False
```

---

# 🎯 TensorBoard

```python
tensorboard = keras.callbacks.TensorBoard(
    log_dir="logs"
)

model.fit(
    X_train,
    y_train,
    callbacks=[tensorboard]
)
```

Run TensorBoard

```bash
tensorboard --logdir logs
```

---

# ⏹ Early Stopping

```python
early_stop = keras.callbacks.EarlyStopping(
    monitor="val_loss",
    patience=5
)
```

---

# 📉 Learning Rate Scheduler

```python
scheduler = keras.callbacks.ReduceLROnPlateau(
    monitor="val_loss",
    factor=0.1,
    patience=3
)
```

---

# 📊 Loss Functions

```python
BinaryCrossentropy()

CategoricalCrossentropy()

SparseCategoricalCrossentropy()

MeanSquaredError()

MeanAbsoluteError()

Huber()
```

---

# ⚙️ Optimizers

```python
Adam()

SGD()

RMSprop()

AdamW()

Adagrad()

Nadam()
```

---

# 📈 Metrics

```python
Accuracy()

Precision()

Recall()

AUC()

MeanAbsoluteError()
```

---

# 🛠 Custom Layer

```python
class MyLayer(layers.Layer):

    def __init__(self):
        super().__init__()

    def call(self, inputs):
        return inputs * 2
```

---

# 🎲 Random Seed

```python
tf.random.set_seed(42)
```

---

# 📂 tf.data Pipeline

```python
dataset = tf.data.Dataset.from_tensor_slices(
    (X, y)
)

dataset = dataset.shuffle(1000)

dataset = dataset.batch(32)

dataset = dataset.prefetch(
    tf.data.AUTOTUNE
)
```

---

# 🔥 Useful TensorFlow Functions

```python
tf.argmax()

tf.argmax(x,axis=1)

tf.cast()

tf.one_hot()

tf.where()

tf.clip_by_value()

tf.math.log()

tf.math.exp()

tf.nn.softmax()

tf.nn.relu()
```

---

# 📚 Popular Pretrained Models

```python
ResNet50

MobileNetV2

EfficientNetB0

InceptionV3

DenseNet121

VGG16

VGG19

Xception
```

---

# 📝 Best Practices

✅ Normalize input data

✅ Use `tf.data.Dataset`

✅ Apply data augmentation

✅ Use callbacks (EarlyStopping, TensorBoard)

✅ Save models in `.keras` format

✅ Use Transfer Learning when possible

✅ Set random seed for reproducibility

✅ Train on GPU if available

---

# 📖 Learning Resources

- 🌐 Official Docs: https://www.tensorflow.org/
- 📘 Keras API: https://keras.io/api/
- 🎓 TensorFlow Tutorials: https://www.tensorflow.org/tutorials
- 🚀 TensorFlow Hub: https://tfhub.dev/

---

# ⭐ If this repository helped you, don't forget to Star it!
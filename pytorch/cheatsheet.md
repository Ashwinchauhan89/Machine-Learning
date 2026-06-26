# 🔥 PyTorch Cheat Sheet

<p align="center">
  <img src="https://pytorch.org/assets/images/pytorch-logo.png" width="250">
</p>

> A quick reference for building Deep Learning models with PyTorch.

---

# 📦 Installation

```bash
pip install torch torchvision torchaudio
```

Check installation

```python
import torch
print(torch.__version__)
print(torch.cuda.is_available())
```

---

# 📌 Import Libraries

```python
import torch
import torch.nn as nn
import torch.optim as optim
from torch.utils.data import DataLoader, Dataset
from torchvision import datasets, transforms
```

---

# 🔢 Creating Tensors

```python
torch.tensor([1,2,3])

torch.zeros(3,3)

torch.ones(2,2)

torch.rand(2,3)

torch.randn(2,3)

torch.arange(0,10)

torch.eye(3)
```

---

# 📏 Tensor Information

```python
x.shape

x.dtype

x.device

x.size()

x.ndim

len(x)
```

---

# 🔄 Tensor Operations

```python
a + b

a - b

a * b

a / b

torch.matmul(a,b)

torch.mm(a,b)

torch.sum(x)

torch.mean(x.float())

torch.max(x)

torch.min(x)
```

---

# 🔀 Reshaping

```python
x.view(2,3)

x.reshape(2,3)

x.flatten()

x.squeeze()

x.unsqueeze(0)

x.transpose(0,1)
```

---

# 🎯 Indexing

```python
x[0]

x[:,1]

x[1:4]

x[-1]
```

---

# 🚀 GPU Support

```python
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")

model.to(device)

tensor.to(device)
```

---

# 🧠 Build Neural Network

```python
class NeuralNetwork(nn.Module):
    def __init__(self):
        super().__init__()

        self.model = nn.Sequential(
            nn.Linear(784,128),
            nn.ReLU(),
            nn.Linear(128,64),
            nn.ReLU(),
            nn.Linear(64,10)
        )

    def forward(self,x):
        return self.model(x)
```

---

# 🏗 Common Layers

```python
nn.Linear()

nn.Conv2d()

nn.MaxPool2d()

nn.BatchNorm2d()

nn.Dropout()

nn.Flatten()

nn.ReLU()

nn.Sigmoid()

nn.Tanh()

nn.Softmax()
```

---

# 🎯 Loss Functions

```python
nn.CrossEntropyLoss()

nn.MSELoss()

nn.BCELoss()

nn.BCEWithLogitsLoss()

nn.L1Loss()
```

---

# ⚙️ Optimizers

```python
optim.SGD(model.parameters(), lr=0.01)

optim.Adam(model.parameters(), lr=0.001)

optim.AdamW(model.parameters(), lr=0.001)

optim.RMSprop(model.parameters())
```

---

# 🔄 Training Loop

```python
for epoch in range(epochs):

    model.train()

    for images, labels in train_loader:

        images = images.to(device)
        labels = labels.to(device)

        optimizer.zero_grad()

        outputs = model(images)

        loss = criterion(outputs, labels)

        loss.backward()

        optimizer.step()
```

---

# ✅ Evaluation

```python
model.eval()

correct = 0

with torch.no_grad():

    for images, labels in test_loader:

        outputs = model(images)

        _, predicted = torch.max(outputs,1)

        correct += (predicted==labels).sum().item()
```

---

# 💾 Save & Load Model

Save

```python
torch.save(model.state_dict(),"model.pth")
```

Load

```python
model.load_state_dict(torch.load("model.pth"))
model.eval()
```

---

# 📂 Dataset & DataLoader

```python
train_loader = DataLoader(
    train_dataset,
    batch_size=32,
    shuffle=True
)

test_loader = DataLoader(
    test_dataset,
    batch_size=32
)
```

---

# 🖼 Image Transformations

```python
transform = transforms.Compose([
    transforms.Resize((224,224)),
    transforms.ToTensor(),
    transforms.Normalize(
        mean=[0.5],
        std=[0.5]
    )
])
```

---

# 📊 Activation Functions

```python
nn.ReLU()

nn.Sigmoid()

nn.Tanh()

nn.LeakyReLU()

nn.Softmax(dim=1)

nn.GELU()
```

---

# 📈 Learning Rate Scheduler

```python
scheduler = optim.lr_scheduler.StepLR(
    optimizer,
    step_size=5,
    gamma=0.1
)
```

---

# 🔍 Useful Functions

```python
torch.argmax()

torch.argmax(outputs, dim=1)

torch.softmax(outputs, dim=1)

torch.cat()

torch.stack()

torch.where()

torch.unique()

torch.clamp()
```

---

# 🛠 Random Seed

```python
torch.manual_seed(42)
```

---

# 📚 torchvision Dataset

```python
train_dataset = datasets.MNIST(
    root="./data",
    train=True,
    download=True,
    transform=transform
)
```

---

# 🔥 CNN Example

```python
model = nn.Sequential(
    nn.Conv2d(3,32,3,padding=1),
    nn.ReLU(),
    nn.MaxPool2d(2),

    nn.Conv2d(32,64,3,padding=1),
    nn.ReLU(),
    nn.MaxPool2d(2),

    nn.Flatten(),
    nn.Linear(64*56*56,128),
    nn.ReLU(),
    nn.Linear(128,10)
)
```

---

# 🎯 Transfer Learning

```python
from torchvision.models import resnet18

model = resnet18(weights="DEFAULT")

model.fc = nn.Linear(model.fc.in_features,10)
```

---

# 📈 TensorBoard

```python
from torch.utils.tensorboard import SummaryWriter

writer = SummaryWriter()

writer.add_scalar("Loss", loss, epoch)

writer.close()
```

---

# 📝 Best Practices

✅ Normalize inputs

✅ Use GPU (`cuda`)

✅ Call `model.train()` during training

✅ Call `model.eval()` during inference

✅ Wrap inference in `torch.no_grad()`

✅ Save only `state_dict()`

✅ Set random seed for reproducibility

---

# 📖 Learning Resources

- 📘 Official Docs: https://pytorch.org/docs/stable/
- 🎓 Tutorials: https://pytorch.org/tutorials/
- 📦 TorchVision: https://pytorch.org/vision/stable/

---

# ⭐ If this repository helped you, don't forget to Star it!
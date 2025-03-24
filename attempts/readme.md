# Train Attempt 1
Model: ResNet15<br>
Optimiser: Adam (lr=0.001)<br>
Transfromations on data:
```python
transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(15),
    transforms.Normalize((mean,), (std,))
])
```
Accuracy: 72.19%

# Train Attempt 2
Model: ResNet15<br>
Optimiser: Adam (lr=0.001)<br>
Transfromations on data:
```python
train_transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(15),
    transforms.RandomAffine(degrees=0, translate=(0.1, 0.1), scale=(0.9, 1.1)),
    transforms.ColorJitter(brightness=0.2, contrast=0.2, saturation=0.2, hue=0.1),
    transforms.RandomCrop(32, padding=4),
    transforms.Normalize((mean,), (std,))
])
```
Accuracy: 72.79%

# Train Attempt 3
Model: ResNet15Enhanced (Added dropout layer with p=0.3)<br>
Optimiser: SGD (lr=0.01, momentum=0.9, weight_decay=5e-4)<br>
Transfromations on data:
```python
train_transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(15),
    transforms.ColorJitter(brightness=0.2, contrast=0.2, saturation=0.2, hue=0.1),
    transforms.RandomCrop(32, padding=4),
    transforms.RandomAffine(degrees=15, translate=(0.1, 0.1), scale=(0.8, 1.2)),
    transforms.Normalize((mean,), (std,))
])
```
Accuracy: 71.54%

# Train Attempt 1
Model: Pre-Trained ResNet15 model from Attempt 2<br>
Optimiser: Adam (lr=0.001)<br>
Transfromations on data:
```python
train_transform = transforms.Compose([
    transforms.ToTensor(),
    transforms.RandomHorizontalFlip(),
    transforms.RandomRotation(15),
    transforms.RandomAffine(degrees=0, translate=(0.1, 0.1), scale=(0.9, 1.1)),
    transforms.ColorJitter(brightness=0.2, contrast=0.2, saturation=0.2, hue=0.1),
    transforms.RandomCrop(32, padding=4),
    transforms.Normalize((mean,), (std,))
])

```
Confusion Matrix:<br>
![](./assets/con_mat_4.png)
Accuracy: 72.32%


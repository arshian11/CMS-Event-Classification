# Train Attempt 1
Model : ResNet15<br>
Optimiser : Adam (lr=0.001)<br>

### Accuracy : 72.19%

# Train Attempt 2
Model : ResNet15<br>
Optimiser : Adam (lr=0.001)<br>

### Accuracy : 72.79%

# Train Attempt 3
Model : ResNet15Enhanced (Added dropout layer with p=0.3)<br>
Optimiser : SGD (lr=0.01, momentum=0.9, weight_decay=5e-4)<br>

### Accuracy : 71.54%

# Train Attempt 4
Model : Pre-Trained ResNet15 model from Attempt 2<br>
Optimiser : Adam (lr=0.001)<br>

Confusion Matrix:<br>
![](https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/con_mat_4.png)<br>
### Accuracy : 72.32%

# Train Attempt 5
Model : ResNet15 Enhanced<br>
- Squeeze-and-Excitation (SE) Block : Global Average Pooling (GAP)
- Residual Block with SE Block

Layers:
- Convolutional Layers : 1 (initial) + 16 (residual) + 3 (shortcuts) = 20
- BatchNorm Layers : 1 (initial) + 16 (residual) + 3 (shortcuts) = 20
- SEBlock FC Layers : 16
- Fully Connected Layer : 1

Optimiser : Adam (lr=0.001, weight_decay=1e-4)<br>
Scheduler : CosineAnnealingLR (T_max=40)<br>
Transfromations on data:
- Cutout: Masks parts of an image by replacing pixels
- Mixup: Blends two images and their labels

Confusion Matrix:<br>
![](https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/con_mat_5.png)<br>
### Accuracy : 72.09%

# Train Attempt 6
Model : ResNet18<br>
Optimiser : Adam (lr=0.001, weight_decay=1e-4)<br>
Scheduler : CosineAnnealingLR (T_max=40)<br>
Confusion Matrix:<br>
![](https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/con_mat_6.png)<br>
### Accuracy : 72.25%

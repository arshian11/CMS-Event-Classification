# Version 1
Model Architecture
### Encoder:
- Input Linear Layer: 21 → 64
- 2 encoder layers
- 4 attention heads
- Dimension of model (d_model) = 64
- Feedforward network dimension = 128

### Decoder:
- Linear Layer: 64 → 128
- ReLu Activation
- Linear Layer: 128 → 21
- Sigmoid Output Activation

### Classifier:
- Linear Layer: 64→ 64
- ReLu Activation
- Dropout(p=0.2) for regularization
- Linear Layer: 64 → 1
- Sigmoid Binary Classification Activation

<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/auto_encode_v1.png" alt="Result Images" width="700">
  <br>
</div>

### AUC Score: 0.7596
### Precision: 0.6843
### Recall: 0.7755
### F1 Score: 0.7271
### Accuracy: 0.6926
  
# Version 2
Model Architecture
### Input Processing Layer:
- Linear Layer: 64 → 128
- Layer Normalization
- GELU Activation
- Dropout(p=0.2) for regularization
- Linear Layer: 128 → 256 
- Layer Normalization

### Encoder:
- 6 encoder layers
- 4 attention heads
- Dimension of model (d_model) = 256
- Feedforward network dimension = 512
- GELU Activation
- Dropout(p=0.2) for regularization
- Layer Normalization

### Decoder:
- Linear Layer: 256 → 512
- Layer Normalization
- GELU Activation
- Dropout(p=0.2) for regularization
- Linear Layer: 512 → 21 
- Sigmoid Output Activation

### Classifier:
- Linear Layer: 256 → 512
- Layer Normalization
- GELU Activation
- Dropout(p=0.2) for regularization
- Linear Layer: 512 → 64
- Layer Normalization
- GELU Activation
- Dropout(p=0.2) for regularization
- Linear Layer: 64 → 1
- Sigmoid Binary Classification Activation

<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/auto_encode_v2.png" alt="Result Images" width="700">
  <br>
</div>

### AUC Score: 0.7707
### Optimal Threshold: 0.5336
### Precision: 0.7068
### Recall: 0.7420
### F1 Score: 0.7240
### Accuracy: 0.7013

# Version 3
Ensemble of the previous two versions 1 and 2

<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/auto_encode_roc_auc_v3.png" alt="ROC-AUC Curve" width="400">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/auto_encode_con_mat_v3.png" alt="Confusion Matrix" width="400">
  <br>
</div>



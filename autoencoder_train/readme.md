# Version 1
- 2 encoder layers
- 4 attention heads
- Dimension of model (d_model) = 64
- Feedforward network dimension = 128
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
- Input Embedding FFC layer
- 6 encoder layers
- 4 attention heads
- Dimension of model (d_model) = 256
- Feedforward network dimension = 512
- GELU Activation
- Dropout(p=0.2) for regularization
- Layer Normalization
- More Depth in Deocder and Classifeir
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

### AUC Score: 0.782
### Accuracy: 0.70987


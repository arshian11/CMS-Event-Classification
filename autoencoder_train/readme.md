# Version 1
Model Created from scratch
### Encoder:
- Input Linear Layer: Transforms input from 21 dimensions → 64 dimensions
- 2 encoder layers
- 4 attention heads
- Dimension of model (d_model) = 64
- Feedforward network dimension = 128

### Decoder:
- Linear Layer: Transforms from 64 dimensions → 128 dimensions
- ReLu Activation
- Linear Layer: Transforms from 128 dimensions → 21 dimensions
- Sigmoid Output Activation

### Classifier:
- Linear Layer: Transforms from 64 dimensions → 64 dimensions
- ReLu Activation
- Dropout(p=0.2) for regularization
- Linear Layer: Transforms from 64 dimensions → 1 dimensions
- Sigmoid Binary Classification Activation

<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/auto_encode_v1.png" alt="Result Images" width="600">
  <br>
</div>

  

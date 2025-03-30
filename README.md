# Event Classification With Masked Transformer Autoencoders

## Common Task 1. Electron/photon classification:
Description: 32x32 matrices with two channels: hit energy and time for two types of
particles, electrons and photons, hitting the detector.

## Approach:
ResNet15 Model was used as the base model

### Model Performance Comparison

| Model                         | Channel Type            | Accuracy (%) |
|--------------------------------|-------------------------|-------------|
| ResNet15                      | Two-Channel Image       | 72.19       |
| ResNet15Enh                   | Two-Channel Image       | 73.33       |
| ResNet15 with SE Block        | Two-Channel Image       | 72.09       |
| Pretrained ResNet18           | Two-Channel Image       | 72.25       |
| ResNet15Enh + FCC             | 2 Single-Channel Images | 50.21       |
| ResNet15Enh                   | 2 Single-Channel Images | 98.61       |

Resnet15Enh : Added Residual Blocks
SE Block : Squeeze-and-Excitation Block

Best Model Performance 
<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/con_mat_8.png" alt="Result Image" width="700">
  <br>
</div>

For detailed information view the attempts section

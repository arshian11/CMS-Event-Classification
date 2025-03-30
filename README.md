# Event Classification With Masked Transformer Autoencoders

## :lock: Common Task 1. Electron/photon classification:
Dataset Description: 32x32 matrices with two channels: hit energy and time for two types of
particles, electrons and photons, hitting the detector.

## :key: Approach:
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

Best Model Performance:
<div align="center">
  <img src="https://github.com/arshian11/CMS-Event-Classification/blob/main/assets/con_mat_8.png" alt="Result Image" width="700">
  <br>
</div>

For detailed information view the attempts section

## :lock: Specific Tasks 2a
- To train a Transformer Autoencoder model of our choice on the dataset using only the first 21 features and only the first 1.1million events. The last 100k items are to be used for test set.
- To train a decoder of our choice which uses the latent space outputs of the Transformer encoder layer as inputs.

## :key: Approach:
Reconstruction Loss : Mean Sqaured Error (MSE)<br>
Classification Loss : Binary Cross Entropy (BCE)<br>

| S.No. | Model | Accuracy(%) | AUC Score |
| --- | --- | --- | ---| 
|1|d_mode=64,2 encoder layers,4 attention heads|69.26| 0.7596|
|2|d_mode=256,6 encoder layers,4 attention heads|70.13| 0.7707|
|3|Ensemble of 1 & 2|70.98|0.782|


Taking the Model with d_mode=256,6 encoder layers,8 attention heads and more deeper Decoder and Classifier in addition with Input Embedding FCC
| Modifications | Accuracy(%) | AUC Score |
| --- | --- | ---| 
|Focal Loss for Classsification|57.45|0.7496|
|Decoder Skip Connection|52.80|0.5000|
|More Depth d_model=512,Layers=12|52.80|0.5000|
|Positional Encoding|70.48|0.7743|


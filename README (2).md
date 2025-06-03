
# 🫁 Chest CT Scan Classification using ResNet18

In this project, a deep learning network (ResNet18) is constructed and refined to categorize chest CT scan images into several cancer-related classifications. A labeled dataset of CT scans is used to train a ResNet18 model using transfer learning, and its performance is assessed on both training and test sets.

## 📂 Dataset
The dataset is structured into three folders:

- `train/`
- `valid/`
- `test/`

There are subdirectories inside each folder that are named after the corresponding classes. Expert radiologists have classified the pictures, which are CT scans of the lungs.

**Source**: The dataset was retrieved from Kaggle, originally used for lung cancer detection research and classification challenges.

## 🏷️ Class Definitions

### Adenocarcinoma Left Lower Lobe
- **Type**: Malignant (Cancer)
- **Details**: A common form of non-small cell lung cancer (NSCLC) that originates in mucus-secreting glands.
- **Location**: Left lower lobe of the lung.
- **Note**: More common in non-smokers and women.

### Large Cell Carcinoma Left Hilum
- **Type**: Malignant (Cancer)
- **Details**: A fast-growing NSCLC subtype with large, abnormal cells.
- **Location**: Near the left hilum (central part of the lung where vessels and bronchi enter).
- **Note**: Known for aggressive behavior and rapid spread.

### Squamous Cell Carcinoma Left Hilum
- **Type**: Malignant (Cancer)
- **Details**: Arises from the squamous cells lining the bronchi.
- **Location**: Also in the left hilum.
- **Note**: Strongly linked to smoking history.

### Benign
- **Type**: Non-cancerous
- **Details**: Includes non-malignant abnormalities, such as scars, infections, or nodules.
- **Note**: No metastatic potential, but some benign lesions require monitoring or treatment.

## 🧠 Model Architecture

- **Base Model**: ResNet18 pre-trained on ImageNet.
- **Modifications**:
  - Replaced the final fully connected layer with a custom classifier.
  - All layers unfrozen for full fine-tuning.

- **Model Interpretability**:
  - Add Grad-CAM or Integrated Gradients to visualize what the model is focusing on.
  - Help doctors understand why a prediction was made.

- **Data augmentations** applied using `torchvision.transforms`.
- **Advanced Augmentation**: Include CutMix, MixUp, or AutoAugment to improve robustness to variations in CT images

## 🏁 Final Results

| Metric         | Value    |
|----------------|----------|
| Train Accuracy | 99.53%   |
| Test Accuracy  | 89.14%   |
| Train Loss     | 0.0231   |
| Test Loss      | 0.3442   |

✅ Indicates strong generalization with some room for further validation improvements.

## 🚀 Future Improvements

- Add Grad-CAM visualizations for model explainability.
- Hyperparameter optimization
- Export to ONNX or TorchScript for deployment

## 🤝 Acknowledgements

- CT scan dataset used under license from Kaggle.
- Model powered by PyTorch.
- Medical guidance based on publicly available oncology resources.

## 🏥 Disclaimer

This model is built for educational and research purposes. It should not be used for actual clinical diagnosis without further validation and regulatory approval.

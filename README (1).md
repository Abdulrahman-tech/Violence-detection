
🎥 Violence Detection in Real-Life Videos using 3D ResNet18

This project leverages a deep learning model (3D ResNet18) to classify real-life surveillance videos as either **violent** or **non-violent**. Using transfer learning and video-specific preprocessing, the model learns temporal and spatial patterns associated with violent behavior.

📂 Dataset

The dataset is structured into two main folders:

```
/Violence
/NonViolence
```

Each folder contains short video clips (in `.mp4` or `.avi` format), categorized by their content. These videos were collected from real-life surveillance footage and manually labeled.

**Source**: Real-Life Violence Situations Dataset — available on [Kaggle](https://www.kaggle.com/datasets/mohamedbakhet/real-life-violence-situations-dataset).

🏷️ Class Definitions

| Class         | Type         | Description                                                                 |
|---------------|--------------|-----------------------------------------------------------------------------|
| Violence      | Positive     | Videos containing real-life violent behavior (fights, assaults, etc.)       |
| NonViolence   | Negative     | Videos without violence (normal daily scenes, people walking, etc.)         |

🧠 Model Architecture

- **Base Model**: `r3d_18` (3D ResNet18) pretrained on Kinetics-400.
- **Modifications**:
  - Final layer replaced to output 2 classes (violence or non-violence).
  - Fine-tuning all layers for improved learning.
- **Clip Details**:
  - 16 frames per clip.
  - Each frame resized to 112×112 pixels.
  - Applied `torchvision.transforms` for normalization and resizing.

📊 Training Setup

- Optimizer: Adam
- Loss Function: CrossEntropyLoss
- Batch Size: 4
- Epochs: 10
- Learning Rate: 0.0001

🏁 Final Results

| Metric            | Value   |
|-------------------|---------|
| Train Accuracy     | ~99%    |
| Test Accuracy      | 97%     |
| Classification Report | Precision: 0.97, Recall: 0.97, F1-Score: 0.97 |
| Loss               | Low and stable across training and validation     |

✅ The model generalizes well with minimal overfitting.

📽️ Sample Inference

Test predictions were successfully made on new video clips using the trained model with frame sampling and preprocessing.

🚀 Future Improvements

- Add Grad-CAM for model explainability (visualize frames where violence is detected).
- Introduce temporal augmentations like time-reversal or random frame skipping.
- Convert to TorchScript or ONNX for deployment on edge devices (e.g., CCTV).

🤝 Acknowledgements

- Dataset courtesy of the Kaggle community.
- Built using PyTorch and Torchvision.
- Project inspired by real-world surveillance and public safety applications.

⚠️ Disclaimer

This project is for educational and research purposes only. It is not validated for production or law enforcement usage. Accuracy may vary across different environments or video sources.

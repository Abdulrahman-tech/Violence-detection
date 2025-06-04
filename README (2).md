This project utilizes a 3D Convolutional Neural Network (ResNet3D-18) to classify video clips as violent or non-violent. It's designed for analyzing real-world surveillance and public footage.

📁 Dataset
Source: Real-Life Violence Situations Dataset

Structure:

Real Life Violence Dataset/
├── Violence/
└── NonViolence/

🧠 Model Overview
Architecture: ResNet3D-18

Modifications:

Final fully connected layer adjusted to output 2 classes (Violence, Non-Violence)

Input Shape: [1, 3, 16, 112, 112] (Batch, Channels, Frames, Height, Width)

🧪 Performance Metrics
Metric	Value
Training Loss	0.0808
Validation Loss	0.1585
Validation Accuracy	95.25%

Classification Report:

markdown
Copy
Edit
              precision    recall  f1-score   support

           0       0.98      0.92      0.95       200
           1       0.92      0.98      0.95       200

    accuracy                           0.95       400
   macro avg       0.95      0.95      0.95       400
weighted avg       0.95      0.95      0.95       400

🔍 Sample Prediction
Input Video: V_10.mp4
Prediction: Violence
Confidence: 1.00
Video Tensor Shape: [1, 3, 16, 112, 112]
en.wikipedia.org

🚀 Future Enhancements

Implement temporal attention mechanisms

Deploy model using TorchScript or ONNX for real-time inference

⚠️ Disclaimer
This project is intended for educational and research purposes only. It is not suitable for deployment in real-world surveillance systems without thorough validation and ethical considerations.



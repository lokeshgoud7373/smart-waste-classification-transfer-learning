# ♻️ Smart Waste Material Classification Using Transfer Learning

An AI-powered waste classification system that uses **transfer learning and deep learning** to identify different types of waste from images. The project provides a user-friendly **web application** where users can upload an image and receive the predicted waste category with a confidence score.

The goal is to support **smart recycling and automated waste segregation** by using computer vision to classify waste materials.

---

live server
https://uaqnuf-aghpauffd-arcadawebapps3.vercel.app



## 📌 Project Overview

Improper waste segregation is a major environmental challenge. Separating waste manually is time-consuming and can lead to incorrect recycling.

This project uses a pretrained deep learning model and **transfer learning** to classify waste images into different material categories.

### Workflow

```text
                Waste Image
                     │
                     ▼
             Image Preprocessing
                     │
                     ▼
             Pretrained CNN
                     │
                     ▼
              Transfer Learning
                     │
                     ▼
              Classification
                     │
          ┌──────────┴──────────┐
          ▼                     ▼
     Waste Category       Confidence Score
          │                     │
          └──────────┬──────────┘
                     ▼
                Web Application
```

---

## ✨ Features

* 📷 Upload waste images
* 🧠 Transfer learning-based classification
* ♻️ Identify recyclable waste categories
* 📊 Display prediction confidence
* 🌐 Interactive web application
* ⚡ Fast image prediction
* 📱 Simple and user-friendly interface
* 📈 Model performance evaluation

---

## 🗑️ Waste Categories

The system can be trained to recognize categories such as:

```text
♻️ Plastic
📄 Paper
🍾 Glass
🥫 Metal
📦 Cardboard
🍎 Organic Waste
🗑️ Other Waste
```

The categories can be modified depending on the dataset used.

---

## 🧠 Transfer Learning

Instead of training a CNN completely from scratch, this project uses a pretrained image-classification network.

Possible pretrained models include:

* MobileNetV2
* EfficientNet
* ResNet50
* DenseNet
* InceptionV3

A pretrained model has already learned general visual features such as edges, shapes, textures, and patterns. These learned features can then be adapted to waste classification.

### Example Architecture

```text
Input Image
     │
     ▼
Resize & Normalize
     │
     ▼
Pretrained CNN
     │
     ▼
Feature Extraction
     │
     ▼
Global Average Pooling
     │
     ▼
Dense Layer
     │
     ▼
Dropout
     │
     ▼
Softmax
     │
     ▼
Waste Category
```

---

## 📊 Dataset

The project requires a labeled waste-image dataset.

A commonly used starting point is **TrashNet**, which contains images across categories such as glass, paper, cardboard, plastic, metal, and trash.

You can also create your own dataset containing images from real-world recycling environments.

Example dataset structure:

```text
dataset/
│
├── cardboard/
├── glass/
├── metal/
├── paper/
├── plastic/
└── trash/
```

### Recommended Dataset Split

```text
Training      → 70%
Validation    → 15%
Testing       → 15%
```

Make sure that test images are kept separate from training images to obtain a meaningful evaluation.

---

## 🔄 Image Preprocessing

Images are processed before being passed to the model.

Typical preprocessing:

```text
Original Image
      ↓
Resize
      ↓
RGB Conversion
      ↓
Normalization
      ↓
Data Augmentation
      ↓
Model Input
```

### Data Augmentation

To improve generalization, training images can be augmented using:

* Rotation
* Horizontal flipping
* Zoom
* Width/height shifting
* Brightness changes
* Random cropping

---

## 🏋️ Model Training

Example configuration:

```text
Model              : MobileNetV2 / EfficientNet
Input Size         : 224 × 224
Optimizer          : Adam
Loss Function      : Categorical Cross Entropy
Batch Size         : 32
Epochs             : 20–30
Transfer Learning  : Yes
```

The pretrained layers can initially be frozen while the new classification layers are trained.

After that, selected pretrained layers can be unfrozen for **fine-tuning**.

---

## 📈 Model Evaluation

The model can be evaluated using:

* Accuracy
* Precision
* Recall
* F1-score
* Confusion Matrix

Example:

```text
Accuracy  : XX.XX%
Precision : XX.XX%
Recall    : XX.XX%
F1 Score  : XX.XX%
```

> Replace the example values with the actual results obtained from your trained model.

---

## 🌐 Web Application

The project includes a web application built with **Streamlit**.

### Application Workflow

```text
User
 │
 ▼
Upload Waste Image
 │
 ▼
Image Preprocessing
 │
 ▼
Transfer Learning Model
 │
 ▼
Prediction
 │
 ▼
Category + Confidence
```

### Example

```text
╔════════════════════════════════════╗
║       ♻️ Smart Waste Classifier    ║
╠════════════════════════════════════╣
║                                    ║
║     Upload a waste image           ║
║                                    ║
║       [ Choose Image ]             ║
║                                    ║
║     Prediction:                    ║
║                                    ║
║     ♻️ PLASTIC                     ║
║                                    ║
║     Confidence: 96.42%             ║
║                                    ║
╚════════════════════════════════════╝
```

---

## 📁 Project Structure

```text
smart-waste-classification-transfer-learning/
│
├── dataset/
│   ├── cardboard/
│   ├── glass/
│   ├── metal/
│   ├── paper/
│   ├── plastic/
│   └── trash/
│
├── models/
│   └── waste_classifier.keras
│
├── notebooks/
│   └── model_training.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── train.py
│   └── predict.py
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```

---

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/smart-waste-classification-transfer-learning.git
cd smart-waste-classification-transfer-learning
```

Create a virtual environment:

```bash
python -m venv venv
```

### Windows

```bash
venv\Scripts\activate
```

### Linux / macOS

```bash
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## 📦 Requirements

Example `requirements.txt`:

```text
tensorflow
numpy
pandas
matplotlib
scikit-learn
pillow
opencv-python
streamlit
```

---

## 🏋️ Train the Model

Place your dataset inside the `dataset/` directory.

Then run:

```bash
python src/train.py
```

After training, the model will be saved as:

```text
models/waste_classifier.keras
```

---

## 🔍 Test the Model

Run:

```bash
python src/predict.py --image sample.jpg
```

Example output:

```text
Image      : sample.jpg
Prediction : Plastic
Confidence : 96.42%
```

---

## 🚀 Run the Web Application

Start the Streamlit application:

```bash
streamlit run app.py
```

The web application allows users to upload an image and automatically classify the waste material.

---

## 🎯 Applications

This system can be used as a foundation for:

* ♻️ Smart recycling systems
* 🏭 Automated waste sorting
* 🏙️ Smart-city waste management
* 🗑️ Intelligent garbage bins
* 🌱 Environmental monitoring
* 🏫 Educational recycling applications
* 📱 Mobile recycling assistants

---

## 🔮 Future Improvements

Future versions can include:

* Real-time camera classification
* Object detection for multiple waste items
* Automated sorting with robotic systems
* Smart-bin integration
* IoT-based waste monitoring
* Waste quantity estimation
* Recycling recommendations
* Mobile application
* Cloud deployment
* Real-time dashboard
* Detection of hazardous waste

### Object Detection Extension

Instead of classifying one image at a time, the system could be extended to detect multiple objects:

```text
Image
  │
  ▼
Object Detection
  │
  ├── Plastic Bottle
  ├── Paper
  ├── Metal Can
  └── Cardboard
```

This would make the system more suitable for automated waste-sorting applications.

---

## ⚠️ Limitations

* Performance depends on the quality and diversity of the training dataset.
* Similar-looking materials may be incorrectly classified.
* Dirty or partially hidden objects can reduce accuracy.
* Lighting and background conditions can affect predictions.
* The model should be tested on real-world images before deployment.

---

## 📊 Expected Result

The completed system provides an end-to-end smart recycling pipeline:

```text
          📷 Waste Image
                 │
                 ▼
       Image Preprocessing
                 │
                 ▼
       Pretrained CNN Model
                 │
                 ▼
        Transfer Learning
                 │
                 ▼
        Waste Classification
                 │
        ┌────────┴────────┐
        ▼                 ▼
   Material Type      Confidence
        │                 │
        └────────┬────────┘
                 ▼
          🌐 Web Application
```

---

## 👨‍💻 Author

**Your Name**

GitHub: `https://github.com/YOUR_USERNAME`

---

## 📄 License

This project is intended for educational and research purposes.

Check the license and usage requirements of any external dataset before redistributing dataset images.

---

## ⭐ Conclusion

**Smart Waste Material Classification Using Transfer Learning** demonstrates how pretrained deep learning models can be adapted for automated waste classification.

By combining **transfer learning, computer vision, and a Streamlit web application**, the project provides a practical foundation for intelligent recycling and automated waste segregation.

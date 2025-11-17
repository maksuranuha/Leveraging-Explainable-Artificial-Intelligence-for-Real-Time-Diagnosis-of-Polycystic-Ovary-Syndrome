# PCOS Detection Using XAI: A Transparent Approach

[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/tensorflow-2.x-orange)](https://www.tensorflow.org/)

AI-powered PCOS detection system using deep learning and explainable AI for transparent, real-time diagnosis from ultrasound images.

## 📋 Overview

PCOS affects millions of women and can lead to infertility, insulin resistance, diabetes, and other complications. Early detection is critical. This project combines three advanced deep learning models (DenseNet201, InceptionV3, EfficientNetV2) achieving **100% accuracy** with seven XAI techniques to provide transparent, interpretable diagnoses. Every prediction includes visual heatmaps explaining which image regions influenced the diagnosis, enabling clinicians to trust and understand AI decisions.

## ✨ Features

- **High Accuracy Models**: DenseNet201, InceptionV3, and EfficientNetV2 architectures achieving perfect classification
- **Explainable AI Integration**: Multiple XAI techniques (GradCAM, ScoreCAM, LayerCAM, EigenCAM, and more)
- **Real-Time Diagnosis**: Flask backend with React frontend for seamless user experience
- **Medical-Grade Interface**: Support for patient health data (blood group, blood pressure, allergies)
- **Flexible Image Support**: JPG, PNG, and SVG formats up to 10 MB

## 🚀 Quick Start

### Prerequisites
- Python 3.8+
- TensorFlow/Keras
- Flask
- React.js

### Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/pcos-xai-detection.git
cd pcos-xai-detection

# Install Python dependencies
pip install -r requirements.txt

# Install frontend dependencies
cd frontend
npm install
```

### Usage

1. **Start the Backend Server**
```bash
python app.py
```

2. **Start the Frontend Application**
```bash
cd frontend
npm start
```

3. **Access the Application**
Navigate to `http://localhost:3000` in your browser

## 📊 Model Performance

All models achieved perfect classification metrics on the test set:

| Model | Precision | Recall | F1-Score | Accuracy |
|-------|-----------|--------|----------|----------|
| DenseNet201 | 1.0000 | 1.0000 | 1.0000 | 100% |
| InceptionV3 | 1.0000 | 1.0000 | 1.0000 | 100% |
| EfficientNetV2 | 1.0000 | 1.0000 | 1.0000 | 100% |

**Test Set Size**: 386 images (157 infected, 229 non-infected)

## 🧠 Model Architecture

### Deep Learning Models
- **DenseNet201**: Dense connections for efficient feature extraction
- **InceptionV3**: Multi-scale feature capture
- **EfficientNetV2**: Optimized efficiency and accuracy balance

### Implementation Details
| Parameter | Value |
|-----------|-------|
| Epochs | 25 |
| Learning Rate | 0.0009 |
| Optimizer | Adam |
| Loss Function | Categorical Cross-Entropy |
| Activation | Softmax |
| Dropout | 0.6 |
| Early Stopping | Yes (Patience: 5) |

## 🔍 Explainable AI Methods

### Supported XAI Techniques

**GradCAM** - Gradient-based Class Activation Mapping
- Efficient and widely adopted
- Creates heatmaps from last convolutional layer gradients
- Good for identifying general areas of abnormality

**ScoreCAM** - Score-based Class Activation Mapping
- Improved precision over GradCAM
- Uses model predictions rather than gradients
- Better at isolating specific cystic regions
- Slightly higher computational cost

**LayerCAM** - Multi-layer Activation Mapping
- Considers multiple network layers
- Captures details from different analysis levels
- Ideal for fine-grained abnormality detection
- Higher computational complexity

**EigenCAM** - PCA-based Activation Mapping
- Fast, backpropagation-free approach
- Captures dominant patterns and features
- Excellent for real-time applications
- Best for broad structural abnormalities

**FullGradCAM** - Comprehensive Gradient Aggregation
- Most thorough explanation approach
- Aggregates gradients across all layers
- Ideal for complex, multi-factor diagnoses
- Higher computational requirements

**XGradCAM & ThresholdCAM** - Advanced Filtering Techniques
- Enhanced gradient scaling and threshold-based filtering
- Improved clarity and focus on relevant regions
- Flexible for different diagnostic needs

## 💻 Application Workflow

1. **Patient Information**: Enter health details (blood group, blood pressure, allergies)
2. **Image Upload**: Submit ultrasound image (JPG, PNG, SVG; ≤10 MB)
3. **Validation**: System verifies successful image import
4. **Analysis**: Deep learning model processes image with XAI interpretation
5. **Results**: Display diagnosis with EigenCAM heatmap visualization

## 📁 Project Structure

```
pcos-xai-detection/
├── models/
│   ├── densenet201_model.h5
│   ├── inceptionv3_model.h5
│   └── efficientnetv2_model.h5
├── xai/
│   ├── gradcam.py
│   ├── scorecam.py
│   ├── layercam.py
│   └── eigencam.py
├── frontend/
│   ├── src/
│   ├── public/
│   └── package.json
├── app.py
├── requirements.txt
└── README.md
```

## 📚 Dataset

Dataset: [PCOS Detection Using Ultrasound Images](https://www.kaggle.com/datasets/anaghachoudhari/pcos-detection-using-ultrasound-images)

The dataset contains labeled ultrasound images categorized as infected and non-infected samples.

## 🔬 Key Research References

- DenseNet Architecture: [arxiv.org/abs/1608.06993](https://arxiv.org/abs/1608.06993)
- Explainable AI Methods: [arxiv.org/abs/2010.11982](https://arxiv.org/abs/2010.11982)
- GradCAM: [arxiv.org/abs/1610.02391](https://arxiv.org/abs/1610.02391)
- ScoreCAM: [arxiv.org/abs/1910.01279](https://arxiv.org/abs/1910.01279)

## 🏥 Clinical Applications

This system is designed for:
- Supporting diagnostic workflows in ultrasound clinics
- Training medical professionals in PCOS identification
- Reducing diagnostic time and improving consistency
- Building trust through transparent AI interpretability

## ⚖️ Disclaimer

This tool is designed as a **diagnostic aid only** and should not replace professional medical judgment. Always consult with qualified healthcare professionals for medical diagnosis and treatment decisions.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📧 Contact & Support

For questions, issues, or suggestions, please open an issue on GitHub or contact the project maintainers.

## 🙏 Acknowledgments

- Kaggle for the PCOS ultrasound dataset
- TensorFlow/Keras team for deep learning frameworks
- XAI research community for explainability methods
- All contributors and supporters of this project

---

⭐ If you find this project helpful, please consider giving it a star!

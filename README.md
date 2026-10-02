
# 🌾 Weed Crop Detector

A YOLO11n-based object detection system that detects and classifies crop and weed plants in agricultural field images.

## 🎯 Project Objective

The goal of this project is to automatically detect:

- 🌾 Crop
- 🌿 Weed

The model draws bounding boxes around detected plants and provides a confidence score for each prediction.

## 🧠 Model

- Model: YOLO11n
- Framework: Ultralytics
- Task: Object Detection
- Input: Agricultural field image
- Output: Bounding boxes, class labels, and confidence scores

## 📊 Dataset

Dataset: Crop and Weed Detection Data with Bounding Boxes

Source:
https://www.kaggle.com/datasets/ravirajsinh45/crop-and-weed-detection-data-with-bounding-boxes

The dataset contains:

- 1,300 images
- 1,300 YOLO annotation files
- 2,072 total bounding boxes

### Classes

| Class ID | Class |
|---|---|
| 0 | Crop |
| 1 | Weed |

The dataset is primarily based on sesame crop fields.

## 🔧 Data Preparation

The dataset was divided into:

| Split | Images |
|---|---:|
| Training | 1,040 |
| Validation | 130 |
| Testing | 130 |

The annotations were verified to be in YOLO format.

## 🚀 Training

The YOLO11n model was trained using Google Colab with a Tesla T4 GPU.

Training configuration:

- Image size: 640 × 640
- Batch size: 16
- Initial training target: 30 epochs
- Training used transfer learning from pretrained YOLO11n weights

## 📈 Test Results

The final model was evaluated on 130 previously unseen test images.

| Metric | Result |
|---|---:|
| Precision | 88.7% |
| Recall | 84.5% |
| mAP@50 | 92.0% |
| mAP@50-95 | 61.5% |

### Class-wise Results

| Class | Precision | Recall | mAP@50 | mAP@50-95 |
|---|---:|---:|---:|---:|
| Crop | 84.3% | 87.3% | 92.2% | 66.6% |
| Weed | 93.1% | 81.6% | 91.7% | 56.3% |

## 📁 Project Structure

```text
WEED-CROP-DETECTOR/
│
├── model/
│   └── crop_weed_detector_best.pt
│
├── README.md
│
└── .gitignore




⚠️ Dataset Limitation

The dataset primarily represents sesame crop fields. Therefore, the model should not be assumed to generalize reliably to all crop types or agricultural environments.

Performance on other crops such as rice, wheat, maize, or vegetables would require additional training and evaluation using representative datasets.

🔮 Future Improvements
Train using more diverse crop types and field conditions
Increase the size and diversity of the dataset
Improve weed recall
Experiment with larger YOLO models
Add weed-density analysis
Evaluate the model on real-world field images
🛠️ Technologies Used
Python
YOLO11n
Ultralytics
PyTorch
Google Colab
Tesla T4 GPU
Git
GitHub
📌 Model

The trained model is available in:

model/crop_weed_detector_best.pt


▶️ How to Run the Model

with:

pip install -r requirements.txt

Then:

yolo predict model=model/crop_weed_detector_best.pt source=your_image.jpg

# NCD-5


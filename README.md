# blood-cell-detection
# 🔬 Blood Cell Detection using YOLOv8

## 📌 Project Overview
Automated detection and counting of **Red Blood Cells (RBC)** and 
**White Blood Cells (WBC)** from peripheral blood smear images using YOLOv8.

## 📊 Dataset
- **Source**: Kaggle - Blood Cell Detection Dataset
- **Images**: 100 annotated images (256x256 px)
- **Annotations**: RBC: 2237 | WBC: 103

## 🏆 Results
| Metric    | Value |
|-----------|-------|
| mAP@50    | 0.985 |
| Precision | 0.981 |
| Recall    | 0.951 |
|F1 Score   | 0.966 |
## 📈 Results
![results](results.png)

## 🔀 Confusion Matrix
![confusion](confusion_matrix.png)

## 👁️ Predictions vs Ground Truth
![predictions](val_batch0_pred.jpg)

## 🛠️ Tech Stack
| Tool | Usage |
|---|---|
| YOLOv8 | Object detection model |
| PyTorch | Deep learning framework |
| Ultralytics | YOLOv8 training pipeline |
| Kaggle | Training environment (GPU T4) |
| Python | Programming language |
| OpenCV | Image processing |
| Pandas | Data manipulation |

---

## 🚀 How to Use the Model

### 1 — Install dependencies
```bash
pip install ultralytics
```

### 2 — Run inference
```python
from ultralytics import YOLO

# Load model
model = YOLO('best.pt')

# Run inference
results = model('your_blood_cell_image.png', imgsz=256, conf=0.25)

# Show results
results[0].show()

# Count cells
rbc_count = int((results[0].boxes.cls == 0).sum())
wbc_count = int((results[0].boxes.cls == 1).sum())
print(f"RBC: {rbc_count} | WBC: {wbc_count}")
```

---

## 📁 Project Structure
```
blood-cell-detection/
    📄 README.md
    📄 LICENSE
    
    📄 results.png
    📄 confusion_matrix.png
    📄 confusion_matrix_normalized.png
    📄 val_batch0_pred.jpg
    📄 val_batch0_labels.jpg
    📄 BoxPR_curve.png
    📄 BoxF1_curve.png
    📄 labels.jpg
    📄 results.csv
```

---

## ⚠️ Dataset Notice
Dataset sourced from [Kaggle - Blood Cell Detection Dataset](https://www.kaggle.com/datasets/draaslan/blood-cell-detection-dataset)
by draaslan. Used strictly for **educational and research purposes only**.

---

## 📚 References
- [YOLOv8 by Ultralytics](https://github.com/ultralytics/ultralytics)
- [Kaggle Dataset](https://www.kaggle.com/datasets/draaslan/blood-cell-detection-dataset)



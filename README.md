# Conditional Polygon Coloring using UNet 🧠🎨



## 🎯 Problem Statement

**“Given a grayscale image of a polygon and a color name (like red, green), generate the colored version of the image.”**

The model learns how to paint grayscale polygon images based on a target color. It is trained on hundreds of examples containing:
- A grayscale polygon shape
- A target color label (e.g., "blue")
- The corresponding correctly-colored polygon

---

## 🧱 Project Structure

The dataset is structured as follows:

```
dataset/
├── training/
│   ├── inputs/
│   ├── outputs/
│   └── data.json
└── validation/
    ├── inputs/
    ├── outputs/
    └── data.json
```

Each sample includes:
- **Input:** Grayscale polygon image
- **Output:** Colored polygon
- **Condition:** Color name (e.g., "red", "blue")

**Supported Colors (9 total):**  
`red`, `blue`, `green`, `yellow`, `orange`, `purple`, `cyan`, `magenta`, `black`

---

## 🧠 Model: UNet Architecture

The core model is a conditional **UNet** that performs image-to-image translation. It works as follows:

### Inputs:
- 64×64 grayscale polygon image
- One-hot encoded color condition

### Output:
- 64×64 colorized image of the polygon

---

## ⚙️ Training Setup

- Epochs: **100**
- Batch Size: **16**
- Optimizer: **Adam**
- Loss Function: **MSE (Mean Squared Error)**
- Validation Split: **20%**

---

## 🎯 Color Conditioning

Each color is mapped to a label (e.g., `"red" = 0`, `"green" = 1`). The model learns to associate color labels with appropriate pixel distributions during training.

---

## 📊 Evaluation

### ✅ Confusion Matrix
> Diagonal values represent correct predictions (e.g., red → red).

### 📈 Loss Curve
> Training loss consistently decreases across epochs.

### 🎨 Sample Predictions

- **Input:** Black polygon
- **Condition:** Color name
- **Prediction:** Generated colorized image
- **Ground Truth:** Correct color output

---

## ✅ Final Accuracy

- Achieved **~90% validation accuracy**
- Visual outputs align well with ground truth samples

---

## 🧾 Final Summary

This project demonstrates:
- Conditional image generation using deep learning
- UNet implementation in PyTorch
- Dataset handling and preprocessing
- Model training and evaluation (visual + quantitative)
- Use of confusion matrix and accuracy plots

---

## 👤 Author

**Ravuka Darshan Jain**  
📧 Email: ravukadarshanjain@gmail.com  
🔗 GitHub: [Darshanjain25933](https://github.com/Darshanjain25933)

---

## 💻 How to Run

### 1. Clone the Repository

```bash
git clone https://github.com/Darshanjain25933/Ayna-Polygon-Colorizer
cd Ayna-Polygon-Colorizer
```

### 2. Install Dependencies

```bash
pip install -r requirements.txt
```

### 3. Launch the Notebook

```bash
jupyter notebook
```
Open `main.ipynb` and run all cells to perform:
- Model loading
- Inference on validation images
- Output visualization

---

## 🧪 Outputs Folder

- All generated color predictions are saved in:  
  `dj`

---

## 📌 License

This project is submitted as part of the Ayna ML Internship Assignment. Educational use only.

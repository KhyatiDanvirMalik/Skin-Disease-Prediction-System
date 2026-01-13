Based on the project details from your report and source code, here is a comprehensive README.md file designed for a GitHub repository. It highlights the medical context, technical methodology (specifically the use of ADASYN and InceptionV3), and your final results.

---

# Skin Disease Prediction using Deep Learning (InceptionV3 & ADASYN)

## Project Overview

This project focuses on the early and accurate diagnosis of skin diseases through an automated **Computer-Aided Diagnostic (CAD)** system. Leveraging **Deep Convolutional Neural Networks (CNNs)**, the system classifies dermatoscopic images into seven distinct clinical categories.

A critical component of this research is the use of **Adaptive Synthetic Sampling (ADASYN)** to resolve severe class imbalances common in medical datasets, ensuring the model is equally sensitive to rare conditions like melanoma as it is to more common benign lesions.

### Target Classes

The model is trained to identify:

1. Actinic Keratoses
2. Basal Cell Carcinoma
3. Benign Keratosis-like Lesions
4. Dermatofibroma
5. Melanoma
6. Melanocytic Nevi
7. Vascular Lesions

---

## Key Features

* 
**Data Balancing:** Implementation of **ADASYN** to adaptively generate synthetic data for "hard-to-learn" minority samples.


* 
**Transfer Learning:** Utilization of the **InceptionV3** architecture, pre-trained on ImageNet, to perform multi-scale feature extraction.


* 
**Comparative Analysis:** Rigorous benchmarking against Basic CNN, CNN with Batch Normalization, and ResNet models.


* 
**Performance Metrics:** Focus on **Recall** and **F1-score** to ensure clinical reliability and minimize false negatives.



---

## Tech Stack

* **Language:** Python
* **Frameworks:** TensorFlow / Keras
* **Data Processing:** Pandas, NumPy, Scikit-learn (Imbalanced-learn for ADASYN)
* **Visualization:** Matplotlib, Seaborn
* **Dataset:** [HAM10000](https://www.kaggle.com/datasets/kmader/skin-cancer-mnist-ham10000) (or specify your source)

---

## Methodology

### 1. Data Preprocessing & Balancing

Medical datasets are often imbalanced. We addressed this using:

* 
**Image Standardization:** Resizing and pixel normalization for CNN ingestion.


* 
**ADASYN:** Unlike standard oversampling, ADASYN focuses on minority samples near the decision boundary, promoting better generalization.



### 2. Model Architecture

After evaluating multiple architectures, **InceptionV3** was selected as the optimal choice. Its parallel filter operations (1x1, 3x3, 5x5) allow the network to capture both fine cellular textures and macroscopic lesion boundaries simultaneously.

---

## Results

The final model achieved high diagnostic precision, particularly outperforming foundational models by significant margins:

| Model | Accuracy | F1-Score |
| --- | --- | --- |
| Basic CNN | ~74% | Low (Biased) |
| ResNet | ~92% | Balanced |
| **InceptionV3** | **98.74%** | **High/Robust** |

Note: InceptionV3 trained on ADASYN data delivered a consistent diagonal performance across all seven classes in the confusion matrix.

---

## Project Structure

```text
├── data/                   # Dataset (Dermatoscopic images)
├── notebooks/
│   └── projectcode.ipynb   # Dataset preprocessing and model training
├── models/
│   └── inception_model.h5  # Trained model weights
├── reports/
│   └── FINAL_REPORT.pdf    # Detailed project documentation
└── README.md

```

---

## Usage

1. **Clone the repository:**
```bash
git clone https://github.com/yourusername/skin-disease-prediction.git

```


2. **Install dependencies:**
```bash
pip install -r requirements.txt

```


3. **Run the Notebook:**
Open `projectcode.ipynb` in Jupyter or Google Colab to see the preprocessing, training, and evaluation steps.

---


## License

This project is licensed under the MIT License - see the LICENSE file for details.

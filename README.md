# ECG Signal Classification

## Overview
This project focuses on **electrocardiogram (ECG) signal analysis and classification** using deep learning techniques. ECG signals reflect the electrical activity of the heart and are widely used for detecting cardiac abnormalities such as arrhythmias.

The goal of this project is to:
- Classify ECG signals into multiple heartbeat categories
- Address class imbalance in medical datasets
- Design and train a **1D Convolutional Neural Network (CNN)** for accurate classification
- Evaluate the model’s performance using standard medical AI metrics

---

## Dataset Description
The dataset consists of ECG heartbeat signals where each sample represents the electrical activity of the heart over time.

### Multi-Class Classification
The dataset contains **5 heartbeat classes**:
- **N**: Normal
- **S**: Supraventricular ectopic beats
- **V**: Ventricular ectopic beats
- **F**: Fusion beats
- **Q**: Unknown beats

Each ECG signal includes characteristic waves:
- **P wave**: Atrial contraction
- **QRS complex**: Ventricular contraction (main peak)
- **T wave**: Ventricular relaxation

Differences between classes are mainly reflected in:
- Timing of the QRS complex
- Shape and spacing between peaks
- Presence of abnormal or irregular patterns

---



## Data Preprocessing
Before feeding data into the neural network:
- Signals were reshaped from **2D to 3D** to match CNN input requirements
- Labels were converted using **One-Hot Encoding**
- All samples were normalized and standardized
- Signals of varying lengths were **zero-padded** to a fixed maximum length

For binary classification tasks:
- Labels were converted to **Normal / Abnormal**
- Data splitting was performed using **stratified sampling** to preserve class ratios

---

## Model Architecture
A **1D Convolutional Neural Network (CNN)** was used due to its effectiveness in time-series and signal processing tasks.

### Key Techniques
- **Early Stopping**  
  Prevents unnecessary training when validation loss stops improving

- **Model Checkpointing**  
  Saves the best model based on minimum validation loss

These techniques help prevent **overfitting** and improve generalization.

---

## Training and Evaluation

### Multi-Class Classification Results
- **Accuracy:** 97.94%
- Strong performance across most classes
- Some overlap observed between visually similar heartbeat types
- Confusion matrix confirms reliable classification

### Binary Classification Results
- **Accuracy:** 98.55%
- Only a very small number of abnormal beats misclassified as normal
- Clinically important due to reduced false negatives

Training and validation curves show:
- Increasing accuracy
- Decreasing loss
- No signs of overfitting

---

## Model Interpretation
To understand **why** the model makes certain predictions:
- Gradient-based analysis was applied
- Sensitive regions of ECG signals were highlighted
- The model correctly focuses on **irregular peaks and abnormal QRS complexes**

This confirms that the model learns **medically meaningful features**, not random noise.

---



---

## Key Takeaways
- Deep learning can effectively classify ECG signals
- Handling class imbalance is critical in medical datasets
- 1D CNNs are well-suited for ECG signal analysis
- Model interpretability is essential for clinical trust

---


---

## Notes
This project was developed as part of a signal processing and medical AI study, focusing on both **performance** and **clinical relevance**.

# Potato Leaf Disease Classification: A Comparative Study

This repository contains the code and experimental results for a comparative study between traditional Machine Learning and Deep Learning approaches for classifying potato leaf diseases. Using the **PlantVillage dataset**, we developed a pipeline that progresses through 7 systematic experiments to achieve a clinically reliable diagnosis tool.

## Project Demo
Check out the system in action here: [Watch Demo Video](https://youtu.be/cmsP6Ncp3jI)

## Project Overview
Agriculture is a backbone of the Rwandan economy, but diseases like **Early Blight** and **Late Blight** cause 20% to 40% yield loss annually. This project aims to bridge the gap caused by the lack of expert agronomists at the village level by providing an automated diagnostic tool.

### Dataset Highlights
* **Source:** [Kaggle PlantVillage Dataset](https://www.kaggle.com/datasets/emmarex/plantdisease)
* **Classes:** Early Blight (1,000), Late Blight (1,000), and Healthy (152).
* **Challenge:** A significant class imbalance (6.6:1 ratio) that reflects real-world data constraints.



## Experimental Progression
The project is structured into 7 distinct experiments to find the best modeling paradigm:

| Exp | Model | Approach | Key Takeaway |
| :--- | :--- | :--- | :--- |
| 1 | **Random Forest** | Classical (HOG) | High variance; struggled with the Healthy class. |
| 2 | **SVM (RBF)** | Classical (HOG) | RBF kernel handled non-linear disease features better. |
| 3 | **Voting Ensemble** | Classical (HOG) | Mixed RF, SVM, and KNN to cancel out individual weaknesses. |
| 4 | **Baseline CNN** | Deep Learning | Significant jump in accuracy; learned features from raw pixels. |
| 5 | **CNN + Regularization** | Deep Learning | Added Dropout and Augmentation to stabilize training. |
| 6 | **Deep CNN** | Deep Learning | Increased complexity led to harder convergence on small data. |
| 7 | **MobileNetV2** | Transfer Learning | **Best Performer (98.8% Accuracy)**; used ImageNet weights. |



## Key Results
The **MobileNetV2 Transfer Learning** model outperformed all others, particularly in identifying the "Healthy" class, which is often the hardest to distinguish in imbalanced sets.

* **Final Accuracy:** 98.8%
* **Macro F1-Score:** 0.974
* **Healthy Recall:** 100% (No healthy plant was misidentified as diseased).



## Repository Structure
* `plantvillage-dataset.ipynb`: The main Jupyter Notebook containing all data preprocessing, HOG feature extraction, model architectures, and evaluation visualizations.
* `README.md`: Project documentation.

## How to Use
1.  **Clone the repo:**
    ```bash
    git clone https://github.com/BirasaDivine/Plant-Disease-Detection.git
    ```
2.  **Install dependencies:**
    ```bash
    pip install tensorflow scikit-learn matplotlib opencv-python
    ```
3.  **Run the Notebook:**
    Open `plantvillage-dataset-birasa-divine.ipynb` in Jupyter or Google Colab to replicate the 7 experiments.

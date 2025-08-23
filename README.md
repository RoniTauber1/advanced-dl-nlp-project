# Advanced Deep Learning NLP Project

Authors: Ofir Czitron & Roni Tauber

---

## 📌 Project Overview

This repository contains the code and resources for our Advanced Deep Learning NLP Project, focused on fine-tuning transformer-based models for sentiment analysis of tweets.

The goal of this project is to fine-tune and evaluate transformer models (such as Twitter RoBERTa) for sentiment classification.

### Workflow

* Data preprocessing and cleaning  
* Stratified splitting of the dataset into train, validation, and test sets  
* Training and hyperparameter optimization with Optuna (manually & HF API)  
* Tracking experiments with Weights & Biases (W\&B)  
* Models compression  
* Final evaluation and visualizations

---

## ⚠️ Important Notes

The code was fully functional and ran successfully from start to finish. However, integrating the project into Git introduced some path and environment issues that caused parts of the code to break. After several attempts to debug and fix the integration, we decided to focus on the core deliverables due to limited time and resources.

We have kept documentation of key steps and results as evidence that the original pipeline worked.

### 🔗 Working Version \- Google Drive

For reference, you can access a Google Drive folder containing the complete working notebook where the entire pipeline runs smoothly without errors:

📁[Drive Folder](https://drive.google.com/drive/folders/1mhKoZMhIgSgBsT9Ybt2kuA6wt7_rOPvf?usp=sharing)

#### Steps:

1. Create a folder: MyDrive/ADV\_DL/  
2. Copy the content into the new file  
3. Run ADV\_DL\_Project\_Drive\_Version.ipynb

*Note: The main notebook may look slightly unorganized due to the multiple iterations and debugging efforts made to improve the pipeline and fix errors during development.*

---

## 🛠️ Requirements

Install the required packages using:

pip install \-r requirements.txt

Main Dependencies:

* torch \- PyTorch framework  
* transformers \- Hugging Face transformers  
* datasets \- Dataset handling  
* optuna \- Hyperparameter optimization  
* wandb \- Experiment tracking (Weights & Biases)  
* scikit-learn \- ML utilities  
* pandas \- Data manipulation  
* numpy \- Numerical computing  
* matplotlib \- Visualization  
* seaborn \- Statistical visualization

---

## 📂 Repository Structure

advanced-dl-nlp-project/  
├── data/                   \# Dataset files (train, validation, test splits)  
├── outputs/               \# Models, Experiment outputs, logs, and Optuna trial folders  
├── notebooks/             \# Jupyter/Colab notebooks for the project  
├── requirements.txt       \# List of dependencies  
├── README.md             \# Project documentation (this file)  
└── .gitignore            \# Ignored files and folders

---

## 📄 Manifest: run\_manifest.json

The run\_manifest.json file is automatically generated after the training process completes. It serves as a centralized reference for all key information about the training run, including model paths, configuration, and hyperparameters.

This file ensures that anyone can reproduce, evaluate, or continue from the saved model without manually tracking paths or settings.

### Contents of the manifest:

| Key | Description |
| ----- | ----- |
| project\_root | Path where all training results and artifacts are saved, including Optuna trial folders |
| model\_alias | The Hugging Face model alias used for training (e.g., cardiffnlp/twitter-roberta-base-sentiment-latest) |
| best\_dir | Full path to the directory containing the best trained model, tokenizer, and configuration files |
| best\_params | A dictionary with the best hyperparameters found during the Optuna tuning process |
| text\_col | The column name in the dataset that contains the text data used for training and evaluation |
| label\_col | The column name in the dataset that contains the labels (target variable) |
| class\_names | A list of all class names corresponding to the label IDs used in the model |

### Example structure:

{  
  "project\_root": "/content/advanced-dl-nlp-project",  
  "results\_root": "/content/advanced-dl-nlp-project/outputs",  
  "model\_alias": "cardiffnlp/twitter-roberta-base-sentiment-latest",  
  "best\_dir": "/content/advanced-dl-nlp-project/outputs/optuna/trial\_2/best",  
  "best\_params": {  
    "lr\_base": 0.000012,  
    "lr\_head": 0.00008,  
    "weight\_decay": 0.00005,  
    "batch\_size": 32  
  },  
  "text\_col": "text\_cardiff",  
  "label\_col": "Sentiment",  
  "class\_names": \["Negative", "Neutral", "Positive"\]  
}

### Usage:

* Model evaluation: The manifest is required when running evaluate\_model\_on\_test to load the correct version of the trained model and tokenizer  
* Reproducibility: It provides all paths and parameters needed to reproduce the training run and replicate results  
* Experiment tracking: When running multiple experiments, each manifest serves as a clear snapshot of the configuration and results

---

## 🚀 How to Use

### 1\. Clone the repository

git clone https://github.com/\<your-username\>/advanced-dl-nlp-project.git  
cd advanced-dl-nlp-project

### 2\. Install dependencies

pip install \-r requirements.txt

### 3\. Run the pipeline

**Recommended:** Use the Google Drive version for the most stable experience as described in the Important Notes section above.


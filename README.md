# 🇮🇩 IndoBERT-based Dengue Tweet Classification (dengue_indobert)

This repository contains the code, data processing pipeline, and experimental results for our research on **multi-class classification of Dengue Hemorrhagic Fever (DHF) tweets in the Indonesian language**, using **IndoBERT-based deep learning architectures**. This work supports real-time public health surveillance using social media data.

📄 [**Read our paper**](https://github.com/irhafidz/dengue_indobert)       
📊 [**Explore our labeled dataset**](https://github.com/irhafidz/dengue_indobert/tree/main/data)          
📈 [**Explore the figures and tables with high-resolution images from our paper**](https://github.com/irhafidz/dengue_indobert/tree/main/results)                     
🧠 Cited our paper/ APA Citation:
Azzahra, N. J., Hafidz, I., Restuningdyah, N. A. P., Rangkuti, R. Y., Hedianto, T., Rabsanjani, R., Widyaswari, M. S., & Anggraeni, W. (2025). IndoBERT-based multi-class classification of dengue fever tweets in Indonesian social media. 

The Github page is created for submission paper of the 2025 International Conference on Advanced Informatics: Concepts, Theory and Applications (ICAICTA).

## 📌 Project Highlights

- **Goal**: Classify Indonesian tweets into:
  - **Label 0**: General dengue-related information (no symptoms)
  - **Label 1**: Personal DHF symptom reports
  - **Label 2**: Other health symptoms not related to DHF

- **Dataset**:  
  - 27,465 raw tweets (Jan 2023–Jun 2025)
  - Preprocessing reduced to 11,689 clean tweets
  - 2,250 labeled tweets (750/class); 743 medically validated

- **Models Used**:
  - `IndoBERT + MLP`
  - `IndoBERT + CNN`
  - `IndoBERT + LSTM`
  - `IndoBERT + CNN-LSTM` (Best)

- **Best Performance**:
  - **Model**: IndoBERT + CNN-LSTM
  - **F1-score**: 0.922 on mixed validation dataset

---

## 🔬 Research Contributions

- Created an **Indonesian DHF symptom dictionary** from WHO-based clinical meta-analysis
- Developed a **multi-stage preprocessing pipeline**: duplicate removal, language filtering, text cleaning
- Labeled tweets through **manual + expert medical validation** from pediatricians, dermatologists, GPs, and others
- Benchmarked **four neural architectures** with extensive hyperparameter tuning

---

## 📈 Results Summary

| Model           | F1-score (Val) |
|----------------|----------------|
| MLP            | 0.904          |
| CNN            | 0.922          |
| LSTM           | 0.918          |
| **CNN-LSTM**   | **0.922** ✅   |
Detailed performance per class available in the paper and `results/` folder

---
## 🩺 Medical Expert Validation

Our research incorporates **clinical validation** by 5 medical specialists to ensure clinical accuracy and contextual relevance:

| **Specialist** | **Expertise** | **Validation Focus** | **Tweets Validated** |
|----------------|---------------|---------------------|---------------------|
| **Pediatrician (Sp.A)** | Pediatric Medicine | DHF symptoms in pediatric cases | 146 tweets |
| **ENT Specialist (Sp.THT-KL)** | Otorhinolaryngology | Upper respiratory symptom validation | 149 tweets |
| **Dermatologist (Sp.KK)** | Dermatology | Skin and rash-related symptoms | 155 tweets |
| **Radiologist (Sp.Rad)** | Radiology | Supporting examination results | 146 tweets |
| **General Practitioner** | General Medicine | General DHF symptoms validation | 147 tweets |

**Total medically validated dataset: 743 tweets** with balanced distribution across all classification labels.
---
## 📁 Repository Structure

```bash
├── data/ # Dataset and clinical validation files
│ ├── tweets_raw/ # Raw tweets collection
│ ├── Dictionary DHF Symptoms.txt # WHO-based symptom dictionary
│ ├── labelled_2250_data.xlsx # Final labeled dataset (2250 tweets)
│ ├── Validated 150 Labels Fifth Doctor (General Practitioner)/
│ ├── Validated 150 Labels_First Doctor (Sp.A)/
│ ├── Validated 150 Labels Fourth Doctor (Sp. Rad)/
│ ├── Validated 150 Labels Second Doctor (Sp. THT-KL)/
│ └── Validated 150 Labels_Third Doctor (Sp. KK)/

├── models_config/ # Trained models by dataset configuration
│ ├── 743 Datasets Model/ # Models trained on validated dataset
│ └── 2250 Datasets Model/ # Models trained on mixed dataset

├── notebooks/ # Jupyter Notebooks for complete pipeline
│ ├── Preprocessing_(One_Example).ipynb
│ ├── DHF_Symptoms_Filtering_(One_example).ipynb
│ ├── Classification_DHF_of_743_Dataset's_Model_IndoBERT_MLP_CNN_LSTM_CNN_LSTM.ipynb
│ └── Classification_DHF_of_2250_Dataset's_Model_IndoBERT_MLP_CNN_LSTM_CNN_LSTM.ipynb

├── results/ # Comprehensive evaluation results and visualizations
│ │
│ ├── 743 Dataset's Model Figures/ # Performance visualizations (validated dataset)
│ │ ├── Confusion Matrix All Models - Dataset Validated only.png
│ │ ├── F1 Validation's Comprehensive Viz (Model with 743 Datasets).png
│ │ ├── Model Efficiency - Performance and Training Time Each Models (743 datasets).png
│ │ ├── Training Loss - Dataset Validated.png
│ │ └── Validation Loss - Dataset Validated.png
│ │
│ ├── 743 Dataset's Model Result/ # Detailed performance metrics and predictions
│ │ ├── results and loss batch/
│ │ ├── all_results_combined.xlsx
│ │ ├── batch_full_experiments.xlsx
│ │ ├── cnn_lstm_sample_predictions.xlsx
│ │ ├── cnn_sample_predictions.xlsx
│ │ ├── lstm_sample_predictions.xlsx
│ │ └── mlp_sample_predictions.xlsx
│ │
│ ├── 2250 Dataset's Model Figures/ # Performance visualizations (mixed dataset)
│ │ ├── Confusion Matrix All Models - Mix Dataset.png
│ │ ├── F1 Validation's Comprehensive Viz (Model with 2250 Datasets).png
│ │ ├── Model Efficiency - Performance and Training Time Each Models (2250 datasets).png
│ │ ├── Training Loss - Mix Dataset.jpg
│ │ └── Validation Loss - Mix Dataset.jpg
│ │
│ ├── 2250 Dataset's Model Result/ # Comprehensive experimental results
│ │ ├── results and loss batch/
│ │ ├── sample_pred/
│ │ ├── all_results_combined.csv
│ │ ├── batch_full_experiments.xlsx
│ │ ├── experiment_results_table.xlsx
│ │ └── experiment_results_table_with_time.xlsx
│ │
│ └── Paper Tables and Figures/ # Publication-ready visualizations from research paper
│ ├── Fig. 1. Research methodology flowchart outlining all major stages from data acquisition t ...
│ ├── Fig. 2. Expert Labelling Workflow for DHF Tweet Classification.png
│ ├── Fig. 3. Flowchart for the Text Filtering and Manual Labeling Process.png
│ ├── TABLE I. DATASET DESCRIPTION.png
│ ├── TABLE II. DHF SYMPTOMS DICTIONARY FOR CLASSIFICATION.png
│ ├── TABLE III. DATA ANNOTATION LABELLING DEFINITION FOR CLASSIFICATION.png
│ ├── TABLE IV. MEDICAL EXPERT VALIDATION.png
│ ├── TABLE V. CLASSIFICATION MODEL ARCHITECTURE.png
│ ├── TABLE VI. MODEL PERFORMANCE ON MIXED DATASET.png
│ ├── TABLE VII. MODEL PERFORMANCE ON MIXED DATASET VALIDATION.png
│ └── TABLE VIII. EXPERIMENTS RESULT.png

└── README.md

```

---

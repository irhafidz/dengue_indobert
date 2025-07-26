# 🇮🇩 IndoBERT-based Dengue Tweet Classification (dengue_indobert)

This repository contains the code, data processing pipeline, and experimental results for our research on **multi-class classification of Dengue Hemorrhagic Fever (DHF) tweets in the Indonesian language**, using **IndoBERT-based deep learning architectures**. This work supports real-time public health surveillance using social media data.

📄 [**Read our paper**](https://github.com/irhafidz/dengue_indobert)  
📊 [**Explore our labeled dataset**](https://github.com/irhafidz/dengue_indobert/tree/main/data)  
🧠 Cited our paper/ APA Citation:
Azzahra, N. J., Hafidz, I., Restuningdyah, N. A. P., Rangkuti, R. Y., Hedianto, T., Rabsanjani, R., Widyaswari, M. S., & Anggraeni, W. (2025). IndoBERT-based multi-class classification of dengue fever tweets in Indonesian social media. 

The Github page is created for submission the 2025 International Conference on Advanced Informatics: Concepts, Theory and Applications (ICAICTA).

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
## 📁 Repository Structure

```bash
├── data/                                  # Dataset and symptom dictionary
│   ├── tweets_raw/                        # Raw tweets (folder)
│   ├── Dictionary DHF Symptoms.txt        # Symptom dictionary (raw text format)
│   └── labelled_2250_data.xlsx            # Final labeled dataset (2250 tweets)

├── models_config/                         # Saved models grouped by dataset size
│   ├── 743 Datasets Model/                # All models trained on 743 dataset
│   └── 2250 Datasets Model/               # All models trained on 2250 dataset

├── notebooks/                             # Jupyter Notebooks for preprocessing, classification
│   ├── Preprocessing_(One_Example).ipynb
│   ├── DHF_Symptoms_Filtering_(One_example).ipynb
│   ├── Classification_DHF_of_743_Dataset's_Model_IndoBERT_MLP_CNN_LSTM_CNN_LSTM.ipynb
│   └── Classification_DHF_of_2250_Dataset's_Model_IndoBERT_MLP_CNN_LSTM_CNN_LSTM.ipynb

├── results/                               # Evaluation results and visualizations
│
│   ├── 743 Dataset's Model Figures/
│   │   ├── Confusion Matrix All Models - Dataset Validated only.png
│   │   ├── F1 Validation's Comprehensive Viz (Model with 743 Datasets).png
│   │   ├── Model Efficiency - Performance and Training Time Each Models (743 datasets).png
│   │   ├── Training Loss - Dataset Validated.png
│   │   └── Validation Loss - Dataset Validated.png
│
│   ├── 743 Dataset's Model Result/
│   │   ├── results and loss batch/            # Batch logs and figures
│   │   ├── all_results_combined.xlsx
│   │   ├── batch_full_experiments.xlsx
│   │   ├── cnn_lstm_sample_predictions.xlsx
│   │   ├── cnn_sample_predictions.xlsx
│   │   ├── Istm_sample_predictions.xlsx
│   │   └── mlp_sample_predictions.xlsx
│
│   ├── 2250 Dataset's Model Figures/
│   │   ├── Confusion Matrix All Models - Mix Dataset.png
│   │   ├── F1 Validation's Comprehensive Viz (Model with 2250 Datasets).png
│   │   ├── Model Efficiency - Performance and Training Time Each Models (2250 datasets).png
│   │   ├── Training Loss - Mix Dataset.jpg
│   │   └── Validation Loss - Mix Dataset.jpg
│
│   └── 2250 Dataset's Model Result/
│       ├── results and loss batch/
│       ├── sample_pred/
│       ├── all_results_combined.csv
│       ├── batch_full_experiments.xlsx
│       ├── experiment_results_table.xlsx
│       └── experiment_results_table_with_time.xlsx

└── README.md

```

---

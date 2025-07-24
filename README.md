# dengue_indobert

🇮🇩 IndoBERT-based Dengue Tweet Classification

This repository contains the code, data processing pipeline, and experimental results for our research on multi-class classification of Dengue Hemorrhagic Fever (DHF) tweets in the Indonesian language, using IndoBERT-based deep learning architectures. This work supports real-time public health surveillance using social media data.

📄 Read our paper
📊 Explore our labeled dataset
🧠 Developed by researchers from ITS, Universitas Mataram, and Universitas NU Surabaya.
📌 Project Highlights

Goal: Classify Indonesian tweets into:
        Label 0: General dengue-related information (no symptoms)
        Label 1: Personal DHF symptom reports
        Label 2: Other health symptoms not related to DHF

Dataset:
       27,465 raw tweets (Jan 2023–Jun 2025)
       Preprocessing reduced to 11,689 clean tweets
       2,250 labeled tweets (750/class); 743 medically validated

Models Used:
- IndoBERT + MLP
- IndoBERT + CNN
- IndoBERT + LSTM
- IndoBERT + CNN-LSTM (Best)

Best Performance:

    Model: IndoBERT + CNN-LSTM
    F1-score: 0.922 on mixed validation dataset

🔬 Research Contributions

    Created an Indonesian DHF symptom dictionary from WHO-based clinical meta-analysis
    Developed a multi-stage preprocessing pipeline: duplicate removal, language filtering, text cleaning
    Labeled tweets through manual + expert medical validation from pediatricians, dermatologists, GPs, and others
    Benchmarked four neural architectures with extensive hyperparameter tuning

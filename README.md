🇮🇳 Tamil Offensive Language Classification
Hybrid IndicBERT + LSTM + CNN Model

This project implements a hybrid deep-learning architecture for classifying Tamil text into six categories, focusing on offensive language detection in social media content.

🚀 Overview

The goal of this project is to automatically categorize Tamil text based on the presence and target of offensive speech. The model integrates:

IndicBERT for contextualized embeddings

LSTM for sequential pattern modeling

CNN (1D) for capturing local linguistic features

This hybrid design provides a strong balance between contextual understanding and phrase-level feature extraction.

🧠 Model Architecture
🔹 IndicBERT (Feature Extractor)

Pre-trained model: ai4bharat/indic-bert

Extracts high-quality multilingual contextual embeddings

Frozen during training to preserve its learned representations and reduce training time

🔹 LSTM Layer

Learns long-range dependencies in Tamil text

🔹 1D CNN Layer

Extracts local n-gram-like patterns from sequences

🔹 Dense Output Layer

Produces final classification across 6 labels

💾 Dataset

The model was trained on the Tamil Offensive Language Detection Dataset.

Split	Samples
Training	35,139
Validation	4,388
Test	4,392
🏷️ Target Classes

The classifier predicts one of the following six categories:

Not_offensive

Offensive_Targeted_Insult_Group

Offensive_Targeted_Insult_Individual

Offensive_Targeted_Insult_Other

Offensive_Untargeted

not-Tamil

📊 Performance Summary

Although the model achieves strong overall accuracy, it has difficulty detecting minority offensive categories due to significant class imbalance.

Metric	Score
Validation Weighted F1	0.6442
Final Test Accuracy	0.7375
Final Test Macro F1	0.2273
🔍 Key Insight

Some minority offensive classes achieved F1 ≈ 0.00

Indicates a strong need for class imbalance solutions such as:

Oversampling

Focal loss

Class-balanced loss

Data augmentation

⚙️ Setup & Execution
1️⃣ Install Dependencies
pip install transformers pandas scikit-learn accelerate torch torchvision torchaudio

2️⃣ Configure Paths in the Notebook

Update the following variables:

TRAIN_FILE_PATH

VAL_FILE_PATH

TEST_FILE_PATH

TEXT_COLUMN

LABEL_COLUMN

3️⃣ Run the Notebook

Execute all cells in:

model5_final.ipynb

4️⃣ Output Files

The notebook produces:

submission.jsonl

submission.zip

These contain predictions for the test dataset.

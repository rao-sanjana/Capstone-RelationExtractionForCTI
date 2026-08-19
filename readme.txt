Hybrid Training with Large Language Model Verified Pseudo-Labels for Cyber Threat Relation Extraction


Overview:
This project explores automated relation extraction from Cyber Threat Intelligence text, identifying relationships between entities such as threat actors, malware, tools, and targets. It combines fine-tuned transformer classifiers with an LLM-based extraction and multi-stage LLM verification pipeline.

There are two main approaches. The first is supervised classification, which fine-tunes transformer models such as BERT and SecureBERT on a labelled CTI relation dataset, along with a hybrid model trained using pseudo-labels to improve performance. The second is LLM-based extraction, which uses a large language model to pull candidate relations directly from CTI reports, normalizes them, and verifies each candidate against MITRE ATT&CK data.


Notebooks:
Labelled_Dataset_Preprocessing.ipynb - loads and explores the labelled CTI relation dataset.
Baseline_Training.ipynb - prepares the relation classification dataset and fine-tunes baseline models, BERT and SecureBERT, for relation extraction.
LLM_Extraction.ipynb - extracts candidate entity relations from raw CTI report text using an LLM, including normalization of relation phrasing.
LLM_Verification.ipynb - verifies LLM-extracted relation candidates against MITRE ATT&CK data and with cosine-similarity.
Hybrid_training.ipynb - trains a hybrid model using the original labelled split combined with pseudo-labelled data, and compares results against the baseline.


Outputs:
The outputs folder contains generated artifacts from the pipeline, including the train, validation and test split, evaluation results for the baseline and hybrid models, LLM-extracted and verified relation candidates, and the pseudo-labels used for hybrid training.


Tech Stack:
The project uses BERT and SecureBERT through Hugging Face Transformers, along with a Groq-hosted LLM.
Other libraries include datasets, torch, scikit-learn, evaluate, accelerate, sentence-transformers, pymupdf for PDF parsing, and nltk. 


Getting Started:
These notebooks were developed using Google Colab and mount Google Drive to store intermediate outputs. To run them, open a notebook in Colab or Jupyter, run the dependency installation cell at the top, update the Drive directory path if using Colab, and then run the remaining cells in order.
Some notebooks also require API keys. The LLM_Extraction and LLM_Verification notebooks needs a Groq API key to access the Groq-hosted LLM, and they also needs a Hugging Face token to download the model used for extraction. Set these as environment variables or Colab secrets, for example GROQ_API_KEY and HF_TOKEN, before running the relevant cells.

Authors:
Developed as part of a capstone project on relation extraction for cyber threat intelligence.

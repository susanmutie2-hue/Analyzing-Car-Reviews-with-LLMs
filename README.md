# Analyzing Car Reviews with Large Language Models (LLMs)

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Python 3.8+](https://img.shields.io/badge/python-3.8%2B-blue.svg)](https://www.python.org/)
[![Hugging Face](https://img.shields.io/badge/Hugging%20Face-Transformers-yellow.svg)](https://huggingface.co/)

## 🚗 Project Overview

**Car-ing is sharing**, an auto dealership company specializing in car sales and rentals, is elevating its customer experience and internal support systems using **Large Language Models (LLMs)**. 

As an AI and NLP developer, this project prototypes a multi-functional chatbot application and analytical workflow designed to assist both customers and human support agents. Using pre-trained Hugging Face transformer models, the pipeline automates customer feedback analysis, question-answering, text translation, summarization, and responsible AI safety checks.

---

## 🛠️ Key Features & Capabilities

1. **Sentiment Classification & Evaluation**
   - **Model:** `distilbert-base-uncased-finetuned-sst-2-english`
   - Classifies customer text reviews as positive or negative.
   - Evaluates performance metrics using Hugging Face `evaluate` (`Accuracy` & `F1-Score`).

2. **Neural Machine Translation & Quality Scoring**
   - **Model:** `Helsinki-NLP/opus-mt-en-es`
   - Extracts and translates English customer review snippets into Spanish.
   - Computes the **BLEU score** against human reference translations to evaluate translation quality.

3. **Extractive Question Answering (QA)**
   - **Model:** `deepset/minilm-uncased-squad2`
   - Extracts precise answers to specific customer/agent inquiries directly from review text context (e.g., querying product reliability and ride quality).

4. **Text Summarization & Bias/Safety Analysis**
   - **Model:** `facebook/bart-large-cnn`
   - Generates concise summaries of lengthy customer reviews.
   - Runs safety audits using `evaluate` for **Toxicity** and **Regard** to ensure responsible AI deployments.

---

## 📁 Repository Structure

```text
Analyzing-Car-Reviews-with-LLMs/
│
├── data/
│   ├── car_reviews.csv              # Dataset containing car reviews and labels
│   └── reference_translations.txt   # Reference translations for BLEU scoring
│
├── car.jpeg                         # Project asset image
├── notebook (2).ipynb               # Main Jupyter Notebook containing the full pipeline
└── README.md                        # Project documentation

Results Summary

Sentiment Analysis: Achieved an Accuracy of 80% and an F1-Score of ~0.86 on the evaluation sample.

Translation: High fidelity Spanish translation validated with a robust BLEU score of ~0.78.

Safety & Ethics: Generated summaries exhibited near-zero maximum toxicity (0.00013) and predominantly positive regard distribution.

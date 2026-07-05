**AI- Research Paper Analysis and Semantic Search using NLP & Transformers**

## Project Overview

Research papers are published every day, making it difficult for students and researchers to find the most relevant papers and understand them quickly. This project builds an intelligent research paper analysis system using Natural Language Processing (NLP), Transformer models, and Semantic Search techniques.

The system searches research papers based on their meaning instead of exact keywords. It also generates summaries, extracts important keywords, and identifies technical entities from research papers to make information easier to understand.

---

## Problem Statement

Searching through thousands of research papers manually is time-consuming. Traditional keyword-based search often fails to retrieve papers that discuss similar topics using different words. Reading long abstracts also requires significant effort.

This project solves these problems by providing:

- Semantic search for finding relevant research papers.
- Automatic summarization of research paper abstracts.
- Keyword extraction from research papers.
- Technical entity recognition using NLP techniques.

---

## Dataset

This project uses the **ML-ArXiv Papers Dataset** available on Hugging Face.
Dataset:https://huggingface.co/datasets/CShorten/ML-ArXiv-Papers

The dataset contains:

- Research Paper Titles
- Research Paper Abstracts

Dataset Link:
https://huggingface.co/datasets/CShorten/ML-ArXiv-Papers

---

## Features Implemented

### 1. Data Preprocessing

- Loaded the ML-ArXiv Papers dataset.
- Selected the title and abstract columns.
- Combined both columns into a single `paper_text` column.
- Removed unnecessary spaces and newline characters.
- Prepared clean text for further processing.

---

### 2. Sentence Embeddings

- Used the **all-MiniLM-L6-v2** Sentence Transformer model.
- Converted research papers into dense vector embeddings.
- Generated embeddings for approximately 15,000 research papers.

---

### 3. Similarity Measurement

- Used Cosine Similarity to compare research paper embeddings.
- Measured semantic similarity between papers instead of keyword matching.

---

### 4. Semantic Search using FAISS

- Created a FAISS index for efficient vector search.
- Stored all paper embeddings in the index.
- Retrieved the Top-K most relevant research papers based on the user's query.

Example:

```python
search_paper("deep learning for medical image analysis")
```

---

### 5. Research Paper Summarization

- Used the **facebook/bart-large-cnn** model for abstractive summarization.
- Generated short summaries of retrieved paper abstracts.
- Built a function to search and summarize multiple papers.

Example:

```python
search_and_summarize("Deep learning in medical imaging", k=5)
```

---

### 6. Keyword Extraction

- Used **KeyBERT** for keyword extraction.
- Extracted important keywords and phrases from research papers.

Example:

- Deep Learning
- Medical Imaging
- Image Segmentation

---

### 7. Named Entity Recognition (NER)

Three different approaches were implemented for technical entity recognition.

#### Approach 1: Rule-Based NER

Used spaCy's EntityRuler to identify predefined technical entities such as:

- Python
- TensorFlow
- PyTorch
- FastAPI
- BERT
- GPT
- FAISS
- spaCy

---

#### Approach 2: Zero-Shot Classification

Implemented using the **facebook/bart-large-mnli** model.

This approach classifies extracted entities into categories such as:

- Programming Language
- Framework
- Library
- Model
- Method
- Application
- Task
- Vector Database

---

#### Approach 3: Hybrid Technical NER

Combined spaCy EntityRuler with additional technical patterns to improve entity recognition.

The system identifies:

- Programming Languages
- Libraries
- Frameworks
- AI Models
- Methods
- Applications
- Tasks
- Vector Databases

---

## Technologies Used

- Python
- Pandas
- NumPy
- Sentence Transformers
- FAISS
- Hugging Face Transformers
- KeyBERT
- spaCy
- Scikit-learn

---

## Project Workflow

```
Research Paper Dataset
        ↓
Data Preprocessing
        ↓
Sentence Transformer Embeddings
        ↓
FAISS Semantic Search
        ↓
Relevant Research Papers
        ↓
Research Paper Summarization
        ↓
Keyword Extraction
        ↓
Named Entity Recognition
```

---

## Project Structure

```
AI-Research-Paper-Analysis-System
│
├── AI_Research_Paper_Intelligent_System.ipynb
├── README.md
├── requirements.txt
```

---

## Note

The `paper_embeddings.npy` and `paper_faiss.index` files are not included in this repository because of GitHub's file size limit. These files are generated automatically when the notebook is executed.

---

## Key Learnings

Through this project, I gained practical experience in:

- Natural Language Processing
- Sentence Embeddings
- Semantic Search
- FAISS Vector Database
- Transformer-Based Summarization
- Keyword Extraction
- Named Entity Recognition
- Zero-Shot Classification
- Building an end-to-end NLP pipeline

---

## Future Scope

Possible improvements for this project include:

- Developing a Streamlit or FastAPI web application.
- Supporting PDF upload and analysis.
- Implementing research paper recommendations.
- Adding paper comparison and citation generation.
- Improving entity recognition using domain-specific transformer models.

---

## Author

Harshita Tiwari

B.Tech Computer Science Engineering

Interested in Machine Learning, Artificial Intelligence, Natural Language Processing, and Data Analytics.

---

## Acknowledgement

This project was developed as part of my learning journey in Natural Language Processing. It helped me understand how semantic search, transformer models, and NLP techniques can be combined to build an intelligent research paper analysis system.

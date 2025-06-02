# GenAI

## Overview

This project focuses on building a **Retrieval-Augmented Generation (RAG)
system** designed for **news retrieval and question answering**. It is a
collaboration between **ETH Zurich**, **Lucerne University of Applied Sciences
and Arts (HSLU)**, and **Google DeepMind**, as part of the HSLU Applied
Information and Data Science Master's Program.

The system leverages state-of-the-art **retrieval** and **generation
techniques** to provide accurate responses to user queries based on a structured
dataset of ETH Zurich news articles.

## Project Goals

The primary objective is to develop an end-to-end **multilingual RAG pipeline**
capable of efficiently retrieving and synthesizing relevant answers from news
documents. The system is structured into three main phases:

1. **Data Preparation** – Extract, clean, and structure news articles from HTML
   files while enriching metadata to support retrieval.
2. **Building the RAG System** – Implement multiple retrieval strategies,
   including **BM25, dense embedding search, GraphRAG**, and hybrid approaches.
   Enhance response quality through **advanced post-retrieval techniques like
   re-ranking**.
3. **Evaluation** – Assess answer accuracy using **automated metrics** (e.g.,
   semantic F1 score, BLEU, ROUGE) and **human evaluation** (relevance,
   correctness, clarity).

## Deliverables

Participants will submit:

- **Codebase** – A well-documented implementation (preferably in Python).
- **Evaluation Report** – A comprehensive analysis of retrieval and generation
  performance.

This project provides an opportunity to explore the latest advancements in
**retrieval-based NLP**, contributing to the development of **trustworthy,
efficient, and scalable AI-driven Q&A systems**.

For further details, refer to the
**[project documentation](/Guidelines/Project%20Requirements.pdf)**.

# Milestone Checklist

## Phase 1: Data Preparation (10 points)

### Loading, Parsing, and Cleaning HTML Files

- [x] Use BeautifulSoup to extract main text from `.html` files
- [x] Utilize Docling for advanced document parsing
- [x] Implement a hybrid approach (BeautifulSoup + Docling) for comparison

### Multilingual Text Preprocessing and Cleaning

- [x] Remove extra spaces, redundant line breaks, and normalize Unicode
      characters
- [x] Standardize date formats from different sources
- [x] Handle German-specific text processing (e.g., compound words, umlaut
      normalization)
- [x] Adds fields such as language, title, date, source
- [x] Adds main content, named entities, topics, keywords, summary
- [x] Compare both summaries and choose the best one
- [x] Store cleaned text and metadata in a structured format (JSON, CSV, or
      database) Explore which format is best for the project
- [x] Create additional metadata to support semantic search and context
      filtering

### Deliverables

- [x] Write a brief report comparing BeautifulSoup and Docling in a Python
      notebook
- [x] Submit a structured multilingual dataset with enriched metadata

## Phase 2.1: Research Agents - Retrieval Strategies (30 points)

### Data Preprocessing and Benchmark Construction

- [x] Chunk news text data using fixed-size segmentation or semantic
      segmentation
- [ ] Use GPT-4o to verify paragraph relevance to a given question (Pascal)
- [ ] Assign ground-truth relevance labels (1.0, 0.5, 0.0) for evaluation
      (Pascal)

### Implement Retrieval Strategies

- [x] Baseline: BM25 Keyword-Based Retrieval
- [x] Semantic Search: Dense Vector Retrieval (using mBERT, Sentence-BERT, etc.)
      -> Sentence-BERT
- [x] GraphRAG-Based Retrieval (Microsoft Local-to-Global GraphRAG)
- [x] Hybrid Retrieval (BM25 + Dense + GraphRAG)

### Evaluate Retrieval Performance

- [x] Analyze retrieval methods using Precision@k, Recall@k, and MRR metrics
- [ ] Examine query routing, query rewriting, and expansion methods

### Deliverables

- [ ] Submit a benchmark dataset with relevance scores
- [ ] Implement and integrate a hybrid retrieval pipeline
- [ ] Write a comparative report on retrieval strategies and performance

## Phase 2.2: Aggregation & Response Synthesis (30 points)

### Implement Re-ranking Models

- [ ] Apply re-ranking techniques (EcoRank, Set-Encoder, List-Aware Reranking,
      etc.)
- [ ] Compare performance with pre-built re-ranking solutions (e.g., OpenAI,
      Cohere)
- [ ] Integrate summarization and fusion techniques

### Evaluate Re-ranking Performance

- [ ] Assess improvements in Precision@k, Recall@k, MRR after re-ranking
- [ ] Evaluate computational efficiency of re-ranking models
- [ ] Conduct qualitative analysis on document alignment with queries

### Deliverables

- [ ] Submit an integrated re-ranking model within the RAG pipeline
- [ ] Provide performance metrics and visualization
- [ ] Conduct qualitative analysis on relevance ordering

## Phase 3: Evaluation (5 points)

### Automated Metrics Calculation

- [ ] Compute Semantic Exact Match, Semantic F1 Score, BLEU/ROUGE
- [ ] Compare generated answers with ground truth using structured evaluation

### Human Evaluation

- [ ] Rate answers based on Relevance, Correctness, and Clarity (scale 1-5)
- [ ] Provide a written analysis summarizing human evaluation results

### Reporting and Presentation

- [ ] Present results using tables and charts within a Python notebook
- [ ] Summarize system performance and identify areas for improvement

### Deliverables

- [ ] Submit calculated automated metrics for RAG-generated responses
- [ ] Conduct human assessment of answer quality
- [ ] Provide a final report on evaluation results

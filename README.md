# NutriChat: A Local RAG Pipeline for Nutritional Information

## Project Overview

NutriChat is a Retrieval Augmented Generation (RAG) pipeline built from scratch, designed to intelligently interact with PDF documents using a Large Language Model (LLM). This project focuses on processing nutritional information and providing accurate responses to user queries.

### Workflow Overview

1. **Document Processing**: 
   - Start with a collection of documents (e.g., PDFs or a 1200-page nutrition textbook)
   - Preprocess documents into smaller chunks (e.g., groups of 10 sentences each)

2. **Embedding Creation**:
   - Transform text chunks into numerical representations using sentence transformers
   - Store embeddings in torch.tensor format for efficiency

3. **Query Processing**:
   - User inputs a query (e.g., "What are the macronutrients? And what do they do?")
   - Transform query into numerical representation using the same embedding model

4. **Similarity Search**:
   - Compare query embedding to document embeddings
   - Retrieve relevant document passages

5. **LLM Processing**:
   - Feed query and relevant passages to a locally-run LLM on an RTX 4090 GPU
   - Generate response based on the provided context

6. **User Interaction**:
   - Present generated text through an optional chat web app interface

This entire process occurs locally, ensuring data privacy and control.

### Key Features

- Runs entirely on a local GPU for enhanced privacy and control
- Enables natural language querying of PDF documents
- Generates accurate responses using a locally-run LLM
- Built from the ground up for deep insights into the RAG process
- Efficient handling of large datasets (100k+ embeddings) with option for vector database integration

## Project Structure

NutriChat is developed in two major phases:

### Phase 1: Document Preprocessing and Embedding Creation

1. PDF Import and Parsing
2. Text Preprocessing (Analysis, cleaning, formatting, chunking)
3. Embedding Generation
4. Embedding Storage

### Phase 2: Search and Answer Generation

1. Vector Search Implementation
2. Prompt Engineering for Context Integration
3. LLM-based Response Generation
4. Query-Answer Process Optimization

## Technical Details

- **Embedding Model**: `all-mpnet-base-v2` from `sentence-transformers`
- **LLM**: `gemma-2b-it` (locally run)
- **Tokenization**: Utilizes advanced NLP libraries like spaCy
- **Chunking Strategy**: Groups sentences into manageable chunks (default: 10 sentences per chunk)
- **Similarity Search**: Implemented using PyTorch for efficient vector comparisons
- **Hardware**: Optimized for local execution on NVIDIA RTX 4090 GPU

## Setup and Installation

(Include steps for setting up the project, including required libraries and any specific instructions for running the LLM locally)

## Usage

(Provide examples of how to use NutriChat, including sample queries and expected outputs)

## Project Roadmap

- [x] PDF Parsing and Text Extraction
- [x] Text Preprocessing and Chunking
- [x] Embedding Generation
- [x] Similarity Search Implementation
- [x] Local LLM Integration
- [x] Prompt Engineering and Augmentation
- [ ] User Interface Development
- [ ] Performance Optimization
- [ ] Extensibility for Different Domains

## Acknowledgments

- NVIDIA for inspiration on the RAG workflow
- Hugging Face for providing access to powerful language models and tools
- Daniel Bourke for the course and guidance in building this [RAG pipeline](https://www.youtube.com/watch?v=qN_2fnOPY-M)
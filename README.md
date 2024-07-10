# Medical Chatbot
This project utilizes Langchain, FAISS, and HuggingFace Embeddings to create a medical chatbot capable of answering medical-related queries by leveraging a vector database constructed from the Gale Encyclopedia of Medicine.

# Table of Contents
- Introduction
- Installation
- Code Overview
- Vector Database Creation
- Querying the Vector Database
- Text Cleaning and Formatting

# Introduction
The Llama2 Medical Chatbot is designed to provide accurate and reliable medical information by leveraging advanced language models and vector search techniques. This project utilizes Langchain, FAISS, and HuggingFace Embeddings to construct a vector database from the Gale Encyclopedia of Medicine. Users can query this database to retrieve relevant medical information, making it a valuable tool for medical professionals, students, and anyone seeking trustworthy health-related answers.

# Installation
- langchain
- langchain_community
- pypdf
- sentence-transformers
- faiss-cpu

# Code Overview
## Vector Database Creation
The create_vector_db function in create_vector_db.py performs the following steps:

1. Loads the PDF document using PyPDFLoader.
2. Splits the document into chunks using RecursiveCharacterTextSplitter.
E3. mbeds the text chunks using HuggingFaceEmbeddings.
4. Creates a FAISS vector store from the embedded text chunks and saves it locally.

## Querying the Vector Database
The query_vector_db function in query_vector_db.py:

1. Loads the FAISS vector store with dangerous deserialization allowed.
2. Searches the vector store for the top k most similar results to the query.
3. Cleans and concatenates the search results.
4. Left aligns the text to ensure readability.
## Text Cleaning and Formatting
The clean_text function removes unnecessary whitespace and ensures proper punctuation and formatting. The left_align_text function wraps the text to a specified width for better readability.

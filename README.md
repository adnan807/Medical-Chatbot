# Medical Chatbot
This project utilizes Langchain, FAISS, and HuggingFace Embeddings to create a medical chatbot capable of answering medical-related queries by leveraging a vector database constructed from the Gale Encyclopedia of Medicine.

# Table of Contents
- Introduction
- Installation
- Usage
- Code Overview
- Vector Database Creation
- Querying the Vector Database
- Text Cleaning and Formatting

# Introduction
The Llama2 Medical Chatbot project aims to provide accurate medical information by using state-of-the-art language models and vector search techniques. It extracts and indexes content from medical literature and allows users to query this content in a user-friendly manner.

# Installation
- Clone the repository:
- Install the required dependencies
- Download the Gale Encyclopedia of Medicine PDF

# Creating the Vector Database
To create the vector database from the PDF document, run:
python create_vector_db.py

# Querying the Vector Database
To query the vector database, modify the QUERY variable in the query_vector_db.py file with your question and run:

python query_vector_db.py

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

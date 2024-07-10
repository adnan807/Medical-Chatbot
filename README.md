# Medical Chatbot
This project utilizes Langchain, FAISS, and HuggingFace Embeddings to create a medical chatbot capable of answering medical-related queries by leveraging a vector database constructed from the Gale Encyclopedia of Medicine.

Table of Contents
Introduction
Installation
Usage
Code Overview
Vector Database Creation
Querying the Vector Database
Text Cleaning and Formatting
License
Introduction
The Llama2 Medical Chatbot project aims to provide accurate medical information by using state-of-the-art language models and vector search techniques. It extracts and indexes content from medical literature and allows users to query this content in a user-friendly manner.

Installation
Clone the repository:

sh
Copy code
git clone https://github.com/your-username/llama2-medical-chatbot.git
cd llama2-medical-chatbot
Install the required dependencies:

sh
Copy code
pip install -r requirements.txt
Download the Gale Encyclopedia of Medicine PDF and place it in the specified path:

sh
Copy code
DATA_PATH = '/content/drive/MyDrive/Projects/Llama2-Medical-Chatbot/71763-gale-encyclopedia-of-medicine.-vol.-1.-2nd-ed.pdf'
Usage
Creating the Vector Database
To create the vector database from the PDF document, run:

sh
Copy code
python create_vector_db.py
Querying the Vector Database
To query the vector database, modify the QUERY variable in the query_vector_db.py file with your question and run:

sh
Copy code
python query_vector_db.py
Code Overview
Vector Database Creation
The create_vector_db function in create_vector_db.py performs the following steps:

Loads the PDF document using PyPDFLoader.
Splits the document into chunks using RecursiveCharacterTextSplitter.
Embeds the text chunks using HuggingFaceEmbeddings.
Creates a FAISS vector store from the embedded text chunks and saves it locally.
Querying the Vector Database
The query_vector_db function in query_vector_db.py:

Loads the FAISS vector store with dangerous deserialization allowed.
Searches the vector store for the top k most similar results to the query.
Cleans and concatenates the search results.
Left aligns the text to ensure readability.
Text Cleaning and Formatting
The clean_text function removes unnecessary whitespace and ensures proper punctuation and formatting. The left_align_text function wraps the text to a specified width for better readability.

# Tattava ChatBot 

This project was done for the NYD Hackathon 2025 and it implements a semantic search system using FAISS and a pre-trained transformer model to retrieve relevant verses from two sources: the Bhagavad Gita and the Patanjali Yoga Sutras. It uses embeddings to compare the semantic similarity of a query with the verses and incorporates a distance threshold to handle inappropriate or irrelevant queries.

## Features

1. **Semantic Search**: Uses embeddings from a pre-trained transformer model to perform similarity-based search.
2. **Multiple Sources**: Supports semantic search for verses from:
   - Bhagavad Gita
   - Patanjali Yoga Sutras
3. **Query Handling**:
   - Determines the most relevant source based on the query.
   - Implements a distance threshold to filter out irrelevant queries.
4. **Contextual Answers**: Generates answers using a language model, referencing the context of the matched verse.

## Requirements

- Python 3.8 or higher
- Required Python packages:
  - `faiss`
  - `sentence-transformers`
  - `numpy`
  - `pandas`
  - `transformers` 

## Code Overview

The **retrieve_and_answer(query)** function processes user queries by determining their source (Bhagavad Gita or Yoga Sutras), generating embeddings, and searching the corresponding FAISS index. It uses a **DISTANCE_THRESHOLD** to evaluate the relevance of the closest match; if the distance exceeds the threshold, it provides a fallback response. Otherwise, it retrieves the matched verse and generates a contextual answer using the generate_text(context, query, source_name) function. This helper function takes the context, query, and source name to create a response using a language model, ensuring appropriate and meaningful answers are provided.

## Usage
1. Download the .ipynb notebook
2. Restart session and refresh runtine and connect to GPU
3. Download the CSV files from the folder **'Dataset'** and change the path under **'Load Dataframes'** section.
4. Run all the cells-> Runtime > Run All
Note: All the installs and import have been made compatible for the code to run in Google Colab, please make the necessary environment changes.

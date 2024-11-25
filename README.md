# Arxiv Paper Processor with Gradio, LangChain, Qdrant, and Ollama

## Description
This project is an AI-powered research assistant that processes academic papers from **arXiv**. It uses **Gradio** to create a simple web interface, **LangChain** for advanced natural language processing tasks, **Qdrant** for storing and retrieving embeddings, and **Ollama** for AI-driven conversational responses.

The system allows users to enter a research topic and a related question. It then fetches the most relevant academic papers from **arXiv**, processes them into manageable chunks, and answers the question based on the context provided by these papers.

## Features
- **Arxiv API Integration**: Automatically downloads academic papers related to a specified topic.
- **Text Processing**: Extracts content from downloaded PDFs and splits it into manageable chunks.
- **Qdrant Vector Store**: Uses **Qdrant** to store the text chunks and their embeddings for efficient retrieval.
- **Ollama Model Integration**: Utilizes **Ollama**'s AI models to generate answers based on the papers' content.
- **Gradio Interface**: A user-friendly interface for interacting with the system.

## Installation
### 1. Install Python Dependencies
To set up this project, you will need to install the following dependencies:
```bash
pip install gradio arxiv langchain_community qdrant-client PyPDF2 langchain
```
### 2. Install Ollama
- Ollama is required for running the Llama 2 (7B) model. Follow these steps:
- Download and install Ollama from [its official website](https://ollama.com/).
- Pull the Llama 2 (7B) model by running:
`ollama pull llama2:7b-chat`

## Optional:
**CUDA (if using GPU for inference): Make sure CUDA is installed for better performance with large models.*

## Usage
1. Clone this repository.
2. Install the required dependencies using the command above.
3. Run the script:
   `python app.py`
4. Interact:
  - Open the Gradio interface in your browser (usually at **http://127.0.0.1:7860**).
  - Input a topic you want to search papers about.
  - Ask a question based on the downloaded papers.
    ### Example Input:
  - **Topic:** "Voice Cloning"
  - **Question:** "How Transformer model is used for voice cloning?"
  - **Output:** The system will return an answer based on the content of the downloaded and processed papers.

## Components Used
- **Gradio:** For creating the interactive web interface.
- **Arxiv API:** To fetch academic papers.
- **LangChain:** For natural language processing and managing chains of tasks.
- **Qdrant:** For storing and retrieving vector embeddings.
- **Ollama:** To generate intelligent responses based on the fetched papers.

## Code Overview
**1. process_papers function:** The core function that manages the entire process:
  - Downloads papers from arXiv.
  - Loads the papers and splits the text into chunks.
  - Creates document embeddings and stores them in Qdrant.
  - Uses llama2:7b-chat via LangChain to answer questions.
**2. Gradio Interface:** The UI is created using Gradio, which allows users to input a topic and a question, then view the answer in real-time.


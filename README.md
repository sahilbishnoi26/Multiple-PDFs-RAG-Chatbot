# Multiple-PDFs-RAG-Chatbot

A Streamlit app to chat with uploaded pdfs using LLMs. Users can choose between OpenAI and Hugging Face models for both embeddings and LLMs in the app.

## Features
- **Upload PDFs**: Extract and preprocess text from multiple PDFs.
- **Model Selection**:
  - **Embeddings**: Choose between OpenAI embeddings or Hugging Face's `hkunlp/instructor-xl`.
  - **LLMs**: Choose between OpenAI GPT-based models or Hugging Face's `google/flan-t5-base`. Note: Better options available via Groq, use DeepSeek R1 or Llama 3.3
- **Semantic Search**: FAISS-based similarity search for efficient retrieval.
- **Conversational Q&A**: Interactive chat with memory of the conversation.

## Technologies Used
- **Streamlit**: Interactive user interface.
- **LangChain**: Manages retrieval and conversational workflows.
- **FAISS**: Vector-based similarity search.
- **Hugging Face Transformers**: Provides embeddings and language model functionality.
- **OpenAI**: Optional integration for embeddings and LLMs.
- **PyPDF2**: Extracts text from PDFs.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/Multiple-PDFs-RAG-Chatbot.git
   cd Multiple-PDFs-RAG-Chatbot
   ```
2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate    # Linux/Mac
   venv\Scripts\activate       # Windows
   pip install -r requirements.txt
   ```
3. Set up environment variables in a `.env` file:
   ```
   HUGGINGFACEHUB_API_TOKEN=your_huggingface_api_token
   OPENAI_API_KEY=your_openai_api_key  # Optional, if using OpenAI models
   ```

## Usage
1. Run the app:
   ```bash
   streamlit run app_update.py
   ```
2. In the sidebar:
   - Upload one or more PDF files.
   - Select your preferred embedding model (OpenAI or Hugging Face).
   - Select your preferred LLM (OpenAI or Hugging Face).
   - Click "Process" to prepare the app.
3. In the main area, ask questions and receive AI-generated answers.

![alt text](https://github.com/sahilbishnoi26/Multiple-PDFs-Chatbot/blob/main/pdf_chatbot.jpg)

## Troubleshooting
- **Missing API Token**: Ensure `HUGGINGFACEHUB_API_TOKEN` and `OPENAI_API_KEY` are correctly set in the `.env` file or as environment variables.
- **CUDA Out of Memory**: Use smaller models like `flan-t5-base` or run on CPU.
- **FAISS Warnings**: Install FAISS with AVX2 support using:
  ```bash
  pip install faiss-cpu
  ```

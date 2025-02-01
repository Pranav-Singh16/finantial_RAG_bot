# Gradio Chatbot with Hugging Face, Pinecone, and PDF Support

A sophisticated chatbot interface built with Gradio that leverages Hugging Face for natural language processing and Pinecone for vector storage. The chatbot can process text queries and uploaded PDF files to provide context-based responses.

## 🌟 Features

- **Gradio Interface**: Simple and interactive UI for chatbot interaction
- **Hugging Face Integration**: Powerful text generation using state-of-the-art models
- **Pinecone Integration**: Efficient vector storage and similarity search
- **PDF Processing**: Extract and analyze text from uploaded PDF documents
- **Customizable Avatars**: Personalized bot and user avatars
- **Docker Support**: Containerized deployment for easy setup

## 🚀 Prerequisites

Before running this project, you'll need:

- Python 3.9 or higher
- Docker (optional but recommended)
- [Hugging Face API Key](https://huggingface.co/settings/tokens)
- [Pinecone API Key](https://www.pinecone.io/start/)

## 📁 Project Structure

```
/project-root
│
├── app.py              # Main Python script running the Gradio app
├── Dockerfile          # Docker configuration for the app
├── requirements.txt    # List of Python dependencies
├── .env               # Environment variables
└── image/             # Avatar images
    ├── bot.png
    └── user.jpg
```

## 🛠️ Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/gradio-chatbot.git
cd gradio-chatbot
```

### 2. Install Dependencies

For local installation (without Docker):
```bash
pip install -r requirements.txt
```

Create a `.env` file:
```env
HUGGINGFACE_API_KEY=your_huggingface_api_key
PINECONE_API_KEY=your_pinecone_api_key
PINECONE_ENVIRONMENT=your_pinecone_environment
```

### 3. Docker Setup (Recommended)

Build the Docker image:
```bash
docker build -t gradio-chatbot .
```

Run the container:
```bash
docker run -p 7860:7860 \
  -e HUGGINGFACE_API_KEY=your_huggingface_api_key \
  -e PINECONE_API_KEY=your_pinecone_api_key \
  -e PINECONE_ENVIRONMENT=your_pinecone_environment \
  gradio-chatbot
```

### 4. Running the App

Local execution:
```bash
python app.py
```

Access the chatbot at `http://localhost:7860`

## 💻 Usage

### Chatbot Interaction
- Type messages in the input box for text-based conversations
- Upload PDF files for document analysis and context-based responses
- Use custom avatars by replacing images in the `/image` directory

## 🐳 Dockerfile Overview

The included Dockerfile:
- Uses `python:3.9-slim` as base image
- Installs system dependencies including `libmagic1`
- Sets up Python environment with required packages
- Configures environment variables for API keys
- Exposes port 7860 for the Gradio interface

## 📦 Requirements

Key dependencies (full list in `requirements.txt`):
```
gradio==3.24.1
huggingface_hub==0.15.1
langchain==0.0.123
pinecone-client==2.0.3
python-dotenv==0.21.0
transformers==4.26.1
PyPDF2==3.0.0
Pillow==9.4.0
```


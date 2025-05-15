# DeepTube Chat

![DeepTube Chat Logo](https://github.com/aadarshvani/deeptube-chat/images/logo.png)

> An intelligent chatbot platform for interacting with YouTube video content through AI Agents and RAG (Retrieval Augmented Generation).

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.95.0+-green.svg)](https://fastapi.tiangolo.com/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.22.0+-red.svg)](https://streamlit.io/)

## 📝 Table of Contents

- [About](#about)
- [Demo](#demo)
- [Key Features](#key-features)
- [System Architecture](#system-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [API Documentation](#api-documentation)
- [Technology Stack](#technology-stack)
- [Project Roadmap](#project-roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🔍 About

DeepTube Chat is an advanced interactive platform that enables users to have meaningful conversations about YouTube video content. The application extracts transcripts from YouTube videos, processes them using RAG (Retrieval Augmented Generation) techniques, and facilitates contextual discussions about specific sections or the entire video content.

Whether you're a student trying to understand educational content, a researcher analyzing interviews, or simply someone looking to get quick insights from long videos without watching them entirely, DeepTube Chat offers an intelligent solution.

## 🎬 Demo

[View Live Demo](https://deeptube-chat.yourdomain.com)

![DeepTube Chat Demo](https://github.com/yourusername/deeptube-chat/raw/main/assets/demo.gif)

## ✨ Key Features

- **Multiple LLM Support**: Select from various Large Language Models (OpenAI, Anthropic, Cohere, Mistral, Llama)
- **YouTube Integration**: Extract and process transcripts from any YouTube video via URL
- **RAG Implementation**: Generate and store embeddings of video content for contextual responses
- **Chapter-Based Summaries**: Automatically generate detailed video summaries with chapter breakdowns
- **Contextual Chat**: Discuss specific chapters or the entire video with AI that understands the content
- **Session-Based Memory**: Maintain chat history within the current session for coherent conversations
- **Document Upload**: Provide additional context through supplementary document uploads
- **Multi-Video Analysis**: Compare or reference multiple videos in a single conversation
- **Citations**: AI responses include timestamp references to relevant video sections

## 🏗️ System Architecture

DeepTube Chat follows a modular architecture with the following key components:

```
DeepTube Chat
├── Frontend (Streamlit)
│   ├── User Interface
│   ├── Video Input Handler
│   ├── Chat Interface
│   └── Model Selection
├── Backend (FastAPI)
│   ├── YouTube API Integration
│   ├── Transcript Processor
│   ├── RAG Engine
│   │   ├── Text Chunking
│   │   ├── Embedding Generator
│   │   └── Vector Storage
│   ├── LLM Connector
│   ├── Document Processor
│   └── Session Manager
└── Database
    ├── Vector DB (Chroma/FAISS/Pinecone)
    └── Session Storage
```

## 🚀 Installation

### Prerequisites

- Python 3.9+
- Git
- API keys for chosen LLM providers (OpenAI, Anthropic, etc.)
- YouTube Data API key

### Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/deeptube-chat.git
   cd deeptube-chat
   ```

2. Create and activate a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate  # On Windows: .venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Set up environment variables:
   ```bash
   cp .env.example .env
   # Edit .env with your API keys
   ```

5. Run the application:
   ```bash
   # Terminal 1 - Backend
   python -m backend.main

   # Terminal 2 - Frontend
   streamlit run frontend/app.py
   ```

6. Open your browser and navigate to http://localhost:8501

### Docker Installation

```bash
docker-compose up -d
```

## 📖 Usage

### Basic Usage

1. Enter a YouTube URL in the input field
2. Select your preferred LLM model
3. Wait for transcript extraction and processing
4. Start chatting about the video content

### Advanced Features

- **Chapter Navigation**: Click on generated chapters to focus the conversation on specific sections
- **Document Upload**: Add PDF, DOCX, or TXT files to provide additional context
- **Model Configuration**: Adjust temperature, max tokens, and other model parameters
- **Export Chat**: Save your conversation history for future reference
- **Multi-Video Analysis**: Add multiple video URLs to compare or reference content across videos

## 📚 API Documentation

The DeepTube Chat API is available for developers who want to integrate our technology into their applications.

API documentation is available at:
- Swagger UI: http://localhost:8000/docs
- ReDoc: http://localhost:8000/redoc

### Example API Request

```python
import requests

api_url = "http://localhost:8000/api/v1/chat"
payload = {
    "youtube_url": "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    "question": "What is the main theme of this video?",
    "model": "gpt-4",
    "chat_history": []
}

response = requests.post(api_url, json=payload)
print(response.json())
```

## 🛠️ Technology Stack

### LLM Providers
- OpenAI API (GPT-3.5-Turbo, GPT-4)
- Anthropic API (Claude models)
- Cohere API (Command models)
- Mistral AI API (Mistral models)
- Llama API (Meta's Llama models)

### Vector Databases
- Chroma (Lightweight, easy to set up)
- FAISS (Facebook AI Similarity Search, efficient for larger datasets)
- Pinecone (Managed vector database service)
- Qdrant (Vector search engine)
- Weaviate (Vector search engine with GraphQL interface)

### YouTube APIs
- YouTube Data API v3 (To fetch video metadata)
- youtube-transcript-api (To extract video transcripts)

### Frontend
- Streamlit (For rapid UI development)
- Gradio (Alternative for interactive UI components)
- React (For more complex UI requirements - optional)

### Backend
- FastAPI (Modern, high-performance web framework)
- LangChain (Framework for LLM application development)
- LlamaIndex (For document retrieval and indexing)

### Document Processing
- PyPDF2/PyMuPDF (For PDF processing)
- python-docx (For DOCX file processing)
- Unstructured (For handling various document formats)

### Database
- SQLite (For lightweight development)
- PostgreSQL (For production deployment)

## 📅 Project Roadmap

### Phase 1: Project Setup and Basic Structure (Weeks 1-2)
- [x] Environment setup and project architecture
- [x] Basic YouTube API integration
- [x] Transcript extraction functionality

### Phase 2: RAG Implementation and Core Functionality (Weeks 3-4)
- [x] Embedding and vector storage setup
- [x] LLM integration and chapter generation
- [ ] Optimization of chunking strategies

### Phase 3: Chat Interface and User Experience (Weeks 5-6)
- [ ] Basic chat functionality with RAG integration
- [ ] Advanced chat features with context awareness
- [ ] Response streaming implementation

### Phase 4: Document Upload and Additional Features (Weeks 7-8)
- [ ] Document processing and integration
- [ ] Multi-video support
- [ ] User preferences and settings

### Phase 5: Testing, Deployment, and Documentation (Weeks 9-10)
- [ ] Comprehensive testing
- [ ] Deployment optimization
- [ ] Documentation and tutorials

### Future Enhancements
- [ ] Multi-modal support with video frame analysis
- [ ] User authentication system
- [ ] Custom model fine-tuning
- [ ] Analytics dashboard
- [ ] Collaborative features
- [ ] Mobile application

## 🤝 Contributing

We welcome contributions to DeepTube Chat! Please follow these steps:

1. Fork the repository
2. Create a new branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Run tests (`pytest`)
5. Commit your changes (`git commit -m 'Add some amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

Please make sure to update tests as appropriate and adhere to our code style guidelines.

### Development Setup

For detailed development setup instructions, please see [CONTRIBUTING.md](CONTRIBUTING.md).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

Project Maintainer - [@aadarshvani](https://github.com/aadarshvani) - aadarshvani.data@gmail.com

Project Link: [https://github.com/yourusername/deeptube-chat](https://github.com/yourusername/deeptube-chat)

---

<p align="center">Made with ❤️ by the DeepTube Chat Team</p>

# AI Personal Assistant with JavaScript Frontend

An AI-powered personal assistant built using **Python, FastAPI, Groq, HTML, CSS, and JavaScript**. The application connects a web-based chat interface to a backend API that processes user messages and generates AI responses using a Groq-hosted language model.

## Overview

This project demonstrates how to build a full-stack AI application by integrating a JavaScript frontend with a Python backend and a large language model API.

The frontend provides the user interface for interacting with the assistant, while the backend manages chat requests and communicates with the configured Groq model.

## Features

- Interactive web-based chat interface
- AI-generated responses through the Groq API
- FastAPI backend with a dedicated chat route
- Modular backend architecture using routes and services
- JavaScript frontend with asynchronous API requests
- JSON-based communication between frontend and backend
- Configuration separated from business logic

## Tech Stack

### Backend
- Python
- FastAPI
- Pydantic
- Groq API

### Frontend
- HTML5
- CSS3
- JavaScript
- Fetch API

### AI Integration
- Large Language Models (LLMs)
- Groq-hosted model inference

## Project Structure

```text
AI_personal_assistant_with_js/
├── backend/
│   ├── routes/
│   │   └── chat.py
│   ├── services/
│   │   └── groq_service.py
│   ├── app.py
│   ├── config.py
│   └── requirements.txt
├── frontend/
│   ├── css/
│   ├── js/
│   └── index.html
├── .gitignore
└── README.md
```

## Architecture

```text
User
  |
  v
Frontend
HTML + CSS + JavaScript
  |
  | HTTP Request (JSON)
  v
FastAPI Backend
  |
  v
Chat Route
routes/chat.py
  |
  v
Groq Service
services/groq_service.py
  |
  v
Groq API / Language Model
  |
  v
Generated Response
  |
  v
Frontend Chat Interface
```

## How It Works

1. The user enters a message in the frontend.
2. JavaScript sends the message to the FastAPI backend.
3. The chat route receives and processes the request.
4. The Groq service sends the request to the configured language model.
5. The model generates a response.
6. The backend returns the response to the frontend.
7. JavaScript displays the result in the chat interface.

## Getting Started

### Prerequisites

- Python installed on your system
- A Groq API key
- Git

### 1. Clone the Repository

```bash
git clone https://github.com/2k24csaiml1b2414254-lgtm/AI_personal_assistant_with_js.git
cd AI_personal_assistant_with_js
```

### 2. Install Backend Dependencies

```bash
python -m pip install -r backend/requirements.txt
```

### 3. Configure Environment Variables

Create a `.env` file in the location expected by your backend configuration.

Example:

```env
GROQ_API_KEY=your_groq_api_key_here
```

Use the exact variable name expected by `backend/config.py` and `backend/services/groq_service.py`.

**Security:** Never commit your real API key or `.env` file to GitHub.

### 4. Start the Backend

From the repository root, run:

```bash
uvicorn app:app --app-dir backend --reload
```

If the backend uses imports that depend on the working directory, you may instead need to run it from inside the `backend/` directory:

```bash
cd backend
uvicorn app:app --reload
```

The API is typically available at:

http://127.0.0.1:8000

### 5. Open the Frontend

If FastAPI serves the frontend homepage, open:

http://127.0.0.1:8000/

If the frontend is served separately, follow the configuration in `backend/app.py` and the API URL in `frontend/js/api.js`.

## API Endpoint

The application includes a dedicated chat route at `backend/routes/chat.py`.

The exact endpoint path, request fields, and response schema depend on the implementation in that file.

Example request format:

```json
{
  "message": "Explain artificial intelligence in simple terms."
}
```

Example response format:

```json
{
  "response": "Artificial intelligence enables computers to perform tasks that typically require human intelligence."
}
```

These JSON examples are illustrative. Check the actual implementation before using them as API documentation.

## Configuration

Application configuration is maintained in `backend/config.py`, while communication with the Groq API is handled by `backend/services/groq_service.py`.

Keep credentials in environment variables and avoid hardcoding API keys in source files.

## Security Considerations

- Keep API keys private.
- Exclude `.env` files from version control.
- Restrict CORS to trusted origins when deploying publicly.
- Avoid exposing internal exception messages in API responses.
- Add appropriate request validation and rate limiting for public deployments.

## Future Improvements

- Conversation history and contextual follow-up questions
- Streaming responses for a more interactive experience
- Persistent chat history
- User authentication
- Voice input and text-to-speech
- Improved error handling and application logging
- Production deployment and API monitoring

## Learning Outcomes

- Building REST APIs using FastAPI
- Integrating an LLM through the Groq API
- Connecting JavaScript frontend code to a Python backend
- Structuring backend code into routes, services, and configuration
- Handling JSON requests and asynchronous API responses
- Managing environment variables and application configuration

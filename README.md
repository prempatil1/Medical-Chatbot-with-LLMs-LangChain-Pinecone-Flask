# MediBot — AI Healthcare Assistant

MediBot is a document-based medical question-answering chatbot built with Flask, LangChain, Pinecone, Hugging Face embeddings, and Groq.

## Features

- Modern responsive chat interface with light and dark themes.
- Suggested questions to help start a conversation.
- Loading feedback while the assistant is generating an answer.
- Document-based retrieval using the medical PDF in `data/` and the Pinecone index.
- Clear reminder that chatbot responses do not replace professional medical advice.

## Tech stack

- Python and Flask
- LangChain
- Pinecone vector database
- Hugging Face sentence-transformer embeddings
- Groq LLM API
- HTML, CSS, and JavaScript

## Run locally

### 1. Clone the repository and open its folder

```bash
git clone https://github.com/prempatil1/Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS.git
cd Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask-AWS
```

### 2. Create and activate the Conda environment

```bash
conda create -n medibot python=3.10 -y
conda activate medibot
```

If you already created the `medibot` environment, just activate it.

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure API keys

Copy `.env.example` to `.env`:

```bash
cp .env.example .env
```

Open `.env` and add your own Pinecone and Groq API keys:

```ini
PINECONE_API_KEY=your_pinecone_api_key
GROQ_API_KEY=your_groq_api_key
```

**Keep `.env` private. Never commit it or share it in screenshots or ZIP files.**

### 5. Prepare the Pinecone index (first-time setup only)

If your Pinecone index has not been populated yet, run:

```bash
python store_index.py
```

The app expects an existing Pinecone index named `medical-chatbot`.

### 6. Start MediBot

```bash
python app.py
```

Open the app in your browser:

```text
http://127.0.0.1:8080
```

## Project structure

```text
Medical-Chatbot-with-LLMs-LangChain-Pinecone-Flask/
├── data/
│   └── Medical_book.pdf
├── research/
│   └── trials.ipynb
├── src/
│   ├── helper.py
│   └── prompt.py
├── static/
│   └── style.css
├── templates/
│   └── chat.html
├── .env.example
├── app.py
├── requirements.txt
└── store_index.py
```

## Medical information notice

MediBot is an educational project. Its responses may be incomplete or inaccurate and are not a diagnosis, prescription, or substitute for advice from a qualified healthcare professional. For urgent or worsening symptoms, seek professional medical care.

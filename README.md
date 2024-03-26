# AfroChat Backend

Backend for **AfroChat**, an AI chat platform available as a web/mobile app and a Telegram bot. Built with FastAPI and PostgreSQL, it connects users to LLMs (OpenAI, Google Gemini) through chat, AI personas, web-search answers and tools.

## Features

- **Chat**: conversations with multiple LLMs and AI personas, with history, search and pinning
- **Ask**: answers backed by live web search (DuckDuckGo), with sources and follow-up questions
- Telegram bot and Mini App (aiogram)
- Image generation, OCR and other AI tools
- Auth (JWT, Google OAuth), payments and usage stats

## Tech stack

FastAPI · PostgreSQL · SQLAlchemy (async) · Alembic · aiogram · Docker · pytest

## Project structure

```
app/
├── bot/            # Telegram bot
├── database/       # DB setup
└── routers/api_v1/ # API modules (Ask, chat, Auth, Persona, Tools, Payment, ...)
migrations/         # Alembic migrations
tests/              # API tests
main.py             # App entry point
```

## Running locally

1. Create a `.env` file with `DATABASE_URL`, `OPENAI_API_KEY`, `GOOGLE_GEMINI_API`, `TELEGRAM_BOT_TOKEN` and `SECRET_KEY`.
2. Start the app and database:
   ```bash
   docker compose up --build
   ```
3. Apply migrations:
   ```bash
   alembic upgrade head
   ```
4. Open the API docs at http://localhost:8000/docs.

# Introduction

<div align="center">

# 🫀 MalicoreAI

**Your personal AI-powered health & lifestyle agent**

*Mental wellness · Physical health · Daily habit tracking — all in one place*

[![Python](https://img.shields.io/badge/Python-3.11+-1D9E75?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.111+-0F6E56?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![Powered by Claude](https://img.shields.io/badge/Powered%20by-Claude%20AI-9FE1CB?style=flat-square)](https://anthropic.com)
[![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)](LICENSE)

</div>

---

## What is MalicoreAI?

MalicoreAI is a personal AI health companion that helps you monitor and improve your lifestyle — from mental wellness and stress management to physical health, sleep, nutrition, and daily habits. It learns from your daily check-ins and gives you personalised, context-aware guidance powered by Anthropic's Claude AI.

Think of it as a brilliant, always-available friend who happens to know a lot about health.

---

## Features

- **AI health chat** — conversational agent that remembers your context and adapts to your current state
- **Daily check-ins** — log mood, energy, sleep, stress, and symptoms; get instant AI insights
- **Mental wellness support** — anxiety, stress, motivation, emotional wellbeing
- **Physical health guidance** — nutrition, hydration, exercise, recovery
- **Personalised system prompts** — your check-in data is woven into every conversation
- **REST API** — clean FastAPI backend ready to connect to any frontend

---

## Tech stack

| Layer | Technology |
|---|---|
| Backend | FastAPI (Python) |
| AI agent | Anthropic Claude (`claude-sonnet-4`) |
| Validation | Pydantic v2 |
| Runtime | Uvicorn (ASGI) |
| Frontend *(coming soon)* | HTML / CSS / JavaScript |

---

## Project structure

```
malicoreai/
├── app/
│   ├── main.py                  # FastAPI app entry point
│   ├── routers/
│   │   ├── chat.py              # POST /api/v1/chat
│   │   ├── health.py            # POST /api/v1/health/checkin
│   │   └── users.py             # POST /api/v1/users
│   ├── models/
│   │   └── schemas.py           # Pydantic request/response models
│   ├── services/
│   │   └── claude_service.py    # Claude API integration & prompt building
│   └── middleware/
│       └── rate_limit.py        # Rate limiting (60 req/min per IP)
├── tests/
├── requirements.txt
├── .env.example
└── README.md
```

---

## Quick start

```bash
# 1. Clone the repo
git clone https://github.com/malicoreAI/malicoreai.git
cd malicoreai

# 2. Create a virtual environment
python -m venv venv && source venv/bin/activate

# 3. Install dependencies
pip install -r requirements.txt

# 4. Set up environment variables
cp .env.example .env
# Add your ANTHROPIC_API_KEY to .env

# 5. Run the server
uvicorn app.main:app --reload
```

Interactive API docs available at **http://localhost:8000/docs**

---

## API overview

### Chat with the agent
```http
POST /api/v1/chat/
```
```json
{
  "user_id": "abc123",
  "message": "I've been feeling anxious lately",
  "health_context": {
    "mood_score": 4,
    "stress_level": "high",
    "sleep_hours": 5.5
  }
}
```

### Daily check-in
```http
POST /api/v1/health/checkin
```
```json
{
  "user_id": "abc123",
  "check_in": {
    "mood_score": 7,
    "energy_score": 6,
    "sleep_hours": 7.5,
    "stress_level": "moderate",
    "physical_symptoms": ["mild headache"],
    "notes": "Big presentation today"
  }
}
```

---

## Roadmap

- [x] FastAPI backend with Claude integration
- [x] Daily health check-in with AI insights
- [x] Personalised context-aware conversations
- [ ] HTML/CSS/JS frontend
- [ ] User authentication (JWT)
- [ ] Persistent storage (Supabase / PostgreSQL)
- [ ] Streaming responses
- [ ] Mood trend dashboard
- [ ] Mobile app

---

## Contributing

Contributions, issues, and feature requests are welcome. Feel free to open an issue or submit a pull request.

---

## License

MIT © [malicoreAI](https://github.com/malicoreAI)

---

<div align="center">
  Built in Poland 🇵🇱 · Powered by <a href="https://anthropic.com">Anthropic Claude</a>
</div>

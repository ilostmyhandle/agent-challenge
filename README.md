# ARIA — Autonomous Research & Intelligence Agent

ARIA is an AI-powered social media intelligence agent built with ElizaOS v2 and deployed on Nosana's decentralized GPU network. Designed for brand managers, founders, and content strategists who need real-time content intelligence without the guesswork.

## What ARIA Does

ARIA thinks like a senior social media strategist. Ask her to analyze content strategies, generate viral tweet angles, identify trending hooks, draft LinkedIn posts, or break down what your competitors are doing wrong — and she delivers sharp, actionable output instantly.

**Core capabilities:**
- Content hook generation for Twitter, LinkedIn, and Instagram
- Trend analysis and platform-specific strategy advice
- Brand voice development and post drafting
- Audience targeting and engagement strategy

## Tech Stack

- **ElizaOS v2** — agent orchestration and plugin framework
- **Nosana** — decentralized GPU deployment on Solana
- **Qwen3.5-27B-AWQ-4bit** — LLM inference running on a self-hosted Nosana GPU endpoint
- **Docker** — containerized deployment
- **SQLite** — lightweight persistent memory

## Quick Start
```bash
git clone https://github.com/ilostmyhandle/agent-challenge
cd agent-challenge
cp .env.example .env
# Add your inference endpoint details to .env
bun install
bun start
```

Then open `http://localhost:3002` in your browser.

## Environment Variables
```
# Option 1 — Use your own Nosana Qwen endpoint
OPENAI_API_KEY=nosana
OPENAI_API_URL=https://your-nosana-qwen-endpoint.node.k8s.prd.nos.ci/v1
SMALL_OPENAI_MODEL=Qwen3.5-27B-AWQ-4bit
MEDIUM_OPENAI_MODEL=Qwen3.5-27B-AWQ-4bit
LARGE_OPENAI_MODEL=Qwen3.5-27B-AWQ-4bit
SERVER_PORT=3001

# Option 2 — Use Groq as fallback
GROQ_API_KEY=your_key_here
SMALL_GROQ_LANGUAGE_MODEL=llama-3.1-8b-instant
MEDIUM_GROQ_LANGUAGE_MODEL=llama-3.3-70b-versatile
LARGE_GROQ_LANGUAGE_MODEL=llama-3.3-70b-versatile
SERVER_PORT=3001
```

## Nosana Deployment

ARIA runs on Nosana's GPU infrastructure using the job definition in `nos_job_def/nosana_eliza_job_definition.json`.

The inference layer is a separate Qwen3.5-27B-AWQ-4bit endpoint also deployed on Nosana, making this a fully decentralized stack — compute and inference both on Nosana.

Live deployment: `https://2m4qmgwscjbiz4pfjhc6nbkatnyplaiszecdzn1tktfw.node.k8s.prd.nos.ci/`

## Character

ARIA's personality and capabilities are defined in `characters/agent.character.json`. She is direct, strategic, and fluent in the language of digital brand building.

## License

MIT

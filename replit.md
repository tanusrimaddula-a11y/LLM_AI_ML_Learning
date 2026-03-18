# NewsWave AI - Workspace

## Overview

NewsWave AI is a voice-first, AI-powered personalized news assistant built for the Murf AI Hackathon. It solves the daily news overload problem by providing concise, personalized, voice-based news briefings with interactive Q&A.

## Stack

- **Monorepo tool**: pnpm workspaces
- **Node.js version**: 24
- **Package manager**: pnpm
- **TypeScript version**: 5.9
- **Frontend**: React + Vite (artifacts/newswave-ai)
- **API framework**: Express 5 (artifacts/api-server)
- **Database**: PostgreSQL + Drizzle ORM
- **Validation**: Zod (zod/v4), drizzle-zod
- **API codegen**: Orval (from OpenAPI spec)
- **UI**: Tailwind CSS, shadcn/ui components, framer-motion, lucide-react
- **Voice**: Web Speech API (speechSynthesis) with Murf AI integration hooks
- **Build**: esbuild (CJS bundle)

## Artifacts

- **artifacts/newswave-ai** — React + Vite frontend at `/` (port 22813)
- **artifacts/api-server** — Express 5 API server at `/api` (port 8080)

## Structure

```
artifacts/
├── newswave-ai/          # React frontend
│   └── src/
│       ├── pages/Landing.tsx      # Marketing landing page
│       ├── pages/AppDashboard.tsx # Main news dashboard
│       ├── components/NewsCard.tsx
│       ├── components/Waveform.tsx
│       ├── components/PremiumButton.tsx
│       └── hooks/use-voice.ts     # Voice playback hook
└── api-server/
    └── src/routes/
        ├── news.ts         # GET /news, POST /news/summarize, POST /news/ask
        └── preferences.ts  # GET/POST /preferences
lib/
├── api-spec/openapi.yaml   # OpenAPI contract
├── api-client-react/       # Generated React Query hooks
├── api-zod/                # Generated Zod schemas
└── db/src/schema/
    └── preferences.ts      # User preferences table
```

## Routes

- `/` — Landing page (marketing, problem statement, features)
- `/app` — Interactive news dashboard with voice briefings and AI Q&A

## API Endpoints

- `GET /api/news?topics=technology,business&limit=10` — Personalized news feed
- `POST /api/news/summarize` — AI voice-ready summaries
- `POST /api/news/ask` — Interactive Q&A about news
- `GET /api/preferences` — User topic preferences
- `POST /api/preferences` — Save preferences

## Key Features

- Voice-first daily briefings (Web Speech API + Murf AI badge)
- Personalized topic filtering (8 topics)
- AI Q&A on current news
- Animated waveform when speaking
- Mock news data with 12 realistic articles
- Dark, professional UI with framer-motion animations

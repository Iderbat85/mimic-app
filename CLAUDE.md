# Mimir

## What This Is
Manga-based English learning app for Mongolian kids. They read manga, learn English through context.

## Tech Stack
- **Frontend:** Vite + React + TypeScript (strict)
- **State:** Zustand
- **Database:** SQLite via Python API
- **Backend:** Python FastAPI (sam_server.py)
- **AI:** Gemini 3 Flash Preview
- **Styling:** Tailwind CSS v4

## Commands
```bash
# Frontend dev server
npm run dev -- --host

# Backend API server (required for database + bubble detection)
python sam_server.py

# Type check
npm run typecheck

# Build
npm run build
```

## Project Structure
```
src/
├── features/           # Feature modules
│   └── [feature]/
│       ├── index.tsx   # Entry point
│       ├── types.ts    # Types
│       ├── store.ts    # Zustand store
│       ├── components/ # UI
│       ├── hooks/      # Logic
│       ├── services/   # API calls
│       └── utils/      # Helpers
├── shared/             # Shared utilities
└── styles/             # Global CSS

# Python backend
sam_server.py           # FastAPI server
database.py             # SQLite operations
```

## Code Rules
1. **Max 250 lines per file** - Split if larger
2. **No `any` types** - Proper TypeScript always
3. **No premature optimization** - Simple first
4. **API URLs use `window.location.hostname`** - For LAN access

## Protected Files (DO NOT MODIFY without asking)
- `*-prompt.ts` - AI prompts
- `PROMPT_*.txt` - AI prompts
- `PROMPT_*.md` - AI prompts

## Database
All data persists to SQLite (`mimir.db`). API endpoints:
- `GET/POST /api/chapters`
- `GET/PUT/DELETE /api/chapters/{id}`
- `POST /api/pages`
- `PUT/DELETE /api/pages/{id}`
- `POST/PUT/DELETE /api/bubbles/{id}`
- `POST /detect-bubbles` - YOLO+SAM bubble detection

## For Product Vision
See `DESIGN.md` for game mechanics, learning philosophy, and pipeline details.

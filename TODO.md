# Plant Bot — TODO

AI garden helper for my home garden in Netanya.
Goal: learn full-stack development, data, APIs, and AI/agents — and build a strong portfolio project.
Target: full-stack web developer roles with AI knowledge.

## 📍 Current focus

- Phase 1: Backend core — learning the branch and PR flow, then the first tables.

---

## Phase 0: Setup

- [x] Install Homebrew
- [x] Install Git (and set name + email, default branch `main`)
- [x] Node.js 22 (via nvm)
- [x] pnpm (Homebrew, linked; old npm-global copy no longer used)
- [x] VS Code + `code` command
- [x] GitHub, Supabase, Vercel accounts
- [x] Create the monorepo folder and push it to GitHub
- [x] Create `packages/shared` (@plant-bot/shared)
- [x] Create the Next.js website + API in `apps/web` (@plant-bot/web)
- [x] Fold `apps/web` into the main workspace (one lockfile)
- [x] Deploy to Vercel (Root Directory = apps/web, Node 22.x)
- [x] Create the Supabase project (user_id + privacy rules from day one)
- [x] Move TODO.md into the repo; write CLAUDE.md and README.md
- [x] Link the GitHub repo to the Claude project
- [ ] Fill in the plant spreadsheet (name, variety, ground or pot, gets rain, planting date, fertilizing/sulfur intervals) — can wait until the Phase 1 tables

## Phase 1: Backend core

- [ ] Start working with branches + pull requests (no more committing straight to main)
- [ ] Tables: plants, care_rules, activity_log
- [ ] Database migrations saved in Git
- [ ] Shared types + Zod schemas in @plant-bot/shared
- [ ] API: list, add, edit plants
- [ ] API: log an activity
- [ ] Input validation (Zod)
- [ ] Login (Supabase Auth)
- [ ] Enter my real plants

## Phase 2: Website core (responsive, works on phone + desktop)

- [ ] Login page
- [ ] Plant list page
- [ ] Plant details + history page (view + edit)
- [ ] One-tap quick-log (works well on a phone screen)
- [ ] Photo upload from the garden (Supabase Storage)
- [ ] Installable on the phone home screen (PWA)

🎯 Milestone: usable in the garden every day

## Phase 3: Weather & tasks

- [ ] Weather adapter (Open-Meteo)
- [ ] Daily scheduled job
- [ ] Rules engine for tasks (fertilizing, sulfur, netting, heat alerts)
- [ ] Rain-aware watering (rainfall + evapotranspiration)
- [ ] "Today" page: weather + tasks

## Phase 4: AI level 1

- [ ] AI adapter (Gemini first, switchable)
- [ ] Daily AI brief (generated once a day and saved)
- [ ] Web push notifications (brief + weather alerts)

🎯 Milestone: CV-ready — deployed full-stack app with AI, good README

## Phase 5: Map

- [ ] Yard outline and reference points
- [ ] Walls with heights
- [ ] Plant positions: place on the map, use phone browser GPS as a starting point, then drag to adjust

## Phase 6: Sun & daylight

- [ ] Shadow calculation (SunCalc)
- [ ] Sun-hours heatmap by month
- [ ] Daylight tracker: tap sun/shade per spot
- [ ] Predicted vs observed comparison

## Phase 7: AI level 2 (Python AI service)

- [ ] Learn Python basics (just enough for this phase)
- [ ] Create a Python AI service (FastAPI) in `services/ai`
- [ ] Next.js API calls the Python service through an adapter
- [ ] Deploy the Python service
- [ ] Camera diagnosis + follow-up tasks
- [ ] New plant flow: AI looks up needs → code scores spots → AI explains best spots
- [ ] RAG: search my logs and notes by meaning (pgvector in Supabase)
- [ ] Build an agent loop by hand first (before using an SDK)
- [ ] Garden agent: chat with tools (my API); suggests actions I approve
- [ ] Background agent: weekly garden review that proposes tasks
- [ ] Small multi-agent handoff: diagnosis agent → planning agent
- [ ] Tracing: record every agent step
- [ ] Prompt-injection protection basics

## Phase 8: Polish

- [ ] Offline mode (log without signal, sync later — PWA)
- [ ] Hebrew/English with RTL

## Phase 9: Portfolio

- [ ] Web showcase mode (demo garden, pre-recorded AI, live weather)
- [ ] AI evaluations (photo test set, diagnosis accuracy)
- [ ] MCP server for garden data
- [ ] AI cost and usage dashboard
- [ ] Tests + CI on GitHub
- [ ] README with architecture diagram
- [ ] Decision records
- [ ] Case-study page
- [ ] Demo video

## Optional: Native phone app (only if target roles or features need it)

- [ ] Expo app in `apps/mobile` (Expo Go is already installed on my phone)
- [ ] Development build for native features
- [ ] Home-screen widget (today's tasks)
- [ ] Android light sensor for the daylight tracker
- [ ] Compass for pinning plant positions
- [ ] Optional: Google Play internal testing

## Stretch goals

- [ ] AR sun path
- [ ] Soil moisture sensors (ESP32)
- [ ] Smart irrigation (alerts first, automatic later)
- [ ] Telegram bot (morning brief + one-tap "done")

---

## 💡 Ideas for later

- (add new ideas here so they don't derail the current phase)
- Upgrades (ESLint 10, TypeScript 7) on purpose, one at a time, on a separate branch

## 🧭 Decisions made

- Website first: responsive Next.js site that works on desktop and phone, installable as a PWA
- Native phone app (Expo) is optional, near the end
- One Next.js project (`apps/web`) serves both the website pages and the API routes (one deploy, one domain, simpler login); API code kept in its own feature folders so it could be split out later
- Supabase (PostgreSQL + Auth + Storage)
- One monorepo with pnpm workspaces: `apps/` (things that run) and `packages/` (shared code); Python service later in `services/ai` (not managed by pnpm)
- Package names scoped with `@plant-bot/`
- One lockfile at the main folder; pnpm settings (like allowBuilds) only in the main pnpm-workspace.yaml
- Modular design: feature folders, small shared core, adapters for outside services
- Rules decide tasks; AI explains and suggests
- Daily AI brief generated once a day, not on every page load
- Gemini first (free tier), behind an adapter so it can be switched
- Multi-user ready from day one (user_id on every table + privacy rules)
- Plant positions from a map, not raw phone GPS
- 3D map skipped
- Real-world development practices (branches, pull requests, linting, environment variables, tests, CI); Conventional Commits for messages (feat:, fix:, chore:)
- Python AI service (FastAPI) for agents, RAG and evaluations; the rest stays TypeScript
- Angular not used here; maybe a small Angular project later if job listings require it

## 📝 Session log

- 2026-11-10 — Checked Mac tools (Homebrew, Git, Node via nvm, pnpm, VS Code). Fixed pnpm to use the Homebrew copy. Changed plan to web-first. Built the monorepo root (Git, package.json, pnpm-workspace.yaml, .gitignore), created @plant-bot/shared and @plant-bot/web (Next.js 16), folded web into the workspace (one lockfile), pushed to GitHub, deployed to Vercel. Learned: monorepo purpose, workspaces, lockfiles, install-script security (allowBuilds), scoped package names, hydration warnings from browser extensions, Conventional Commits. Then created the Supabase project; env vars in .env.local and Vercel (publishable key as Config); added README, .env.example, .nvmrc, CLAUDE.md; linked the repo to the Claude project. Learned: environment variables, NEXT*PUBLIC* prefix, publishable vs secret keys, .gitignore exceptions (!).

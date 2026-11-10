# Plant Bot

Plant Bot is an AI garden helper I'm building for my home garden. It tracks my plants and their care history, combines weather data with care rules to plan daily tasks, and uses AI to explain what to do and why.

🚧 Work in progress - currently in early setup.

Live: plant-bot-iota.vercel.app

## Stack

- Next.js (website + API) in `apps/web`
- Supabase (database, login, storage)
- pnpm workspaces monorepo

## Run locally

1. `git clone https://github.com/beeeen498/plant-bot.git && cd plant-bot`
2. `pnpm install`
3. Create `apps/web/.env.local` with your Supabase URL and publishable key
4. `pnpm --filter @plant-bot/web dev`

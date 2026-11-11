# Plant Bot

AI garden helper for my home garden. See README.md for the overview and TODO.md for the roadmap and current focus.

## Structure

- `apps/web`: Next.js (website pages + API routes), deployed on Vercel
- `packages/shared`: shared types and Zod schemas (`@plant-bot/shared`)
- `services/ai`: Python AI service (Phase 7, not managed by pnpm)

## Commands (run from the root)

- `pnpm install`: install everything
- `pnpm --filter @plant-bot/web dev`: run the website locally

## Conventions

- One lockfile at the root; pnpm settings only in the root `pnpm-workspace.yaml`
- Package names scoped with `@plant-bot/`
- Feature folders; adapters for outside services (weather, AI)
- Conventional Commits: `feat:`, `fix:`, `chore:`, `docs:`
- Branches + pull requests from Phase 1 on
- Never commit secrets; new env var names also go in `apps/web/.env.example`
- Every table has `user_id` and Row Level Security

## Next.js

This is Next.js 16. Follow @apps/web/AGENTS.md before writing Next.js code.

## How I work

- I'm learning: explain concepts and the "why" in simple English before code
- Small pieces of code; I type them myself
- Let me read errors first before helping
- Be honest about trade-offs and uncertainty

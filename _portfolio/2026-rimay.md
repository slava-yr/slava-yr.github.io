---
title: "Rimay"
collection: portfolio
permalink: /portfolio/2026-rimay
excerpt: "A no-code AI customer-service agent for food SMEs — upload your menu, set rules in plain language, and start answering customers on web and Telegram."
date: 2026-01-02
link: "https://www.youtube.com/watch?v=V0gKkWqEYWE"
tags:
  - AI
  - Full-Stack
  - AWS
---

## Overview

**Rimay** (*"to speak"* in Quechua) is a no-code AI customer-service agent built for food SMEs in Latin America. In Peru alone there are more than 13,000 rotisserie chicken shops, and small teams juggle simultaneous orders across WhatsApp, Instagram, Facebook, and web — losing ready-to-buy customers they simply can't answer in time, while delivery apps charge commissions of up to 30%.

Rimay lets any small business stand up its own AI agent without writing a line of code: the owner uploads a photo of their menu (the AI extracts products and prices automatically), defines business rules in plain Spanish, and the agent starts handling conversations over a web widget and Telegram. It answers strictly from the real catalog — no hallucinated products or prices — and escalates to a human operator within seconds when a case falls outside the rules.

## Highlights

- **No-code setup:** menu photo → automatic product/price extraction; business rules written in natural language.
- **Grounded responses:** catalog replies are forced into strict JSON schemas validated against the database, so the AI never invents items or prices.
- **Multi-channel:** embeddable web widget plus a native Telegram bot.
- **Human-in-the-loop:** automatic fallback to a human operator on uncovered cases or AI timeouts/anomalies.
- **Insight Engine:** analyzes friction in conversations and suggests new business rules the owner can approve in one click.

## Tools & Technologies

- **Frontend/Backend:** Next.js 14 (App Router) + TypeScript
- **Data:** multi-tenant PostgreSQL via Prisma, hosted on Neon (serverless)
- **AI:** swappable LLMs — Gemini Flash or OpenAI GPT-4o-mini, configurable per environment
- **Channels:** embeddable web widget + Telegram bot (native webhooks)
- **Infra:** AWS Amplify Hosting (Next.js SSR) with CI/CD from GitHub
- Built end-to-end with **Kiro**, using its structured specs and steering files

## Links

- ▶️ **Presentation video:** [Watch on YouTube](https://www.youtube.com/watch?v=V0gKkWqEYWE)
- 🔗 **Live demo:** [Rimay web app](https://main.d39xfi82w5dpxo.amplifyapp.com)
- 💻 **Source code:** [github.com/CarlosGY13/rimay-app](https://github.com/CarlosGY13/rimay-app)

# AskMaan

![AskMaan](banner.png)

**Live at [askmaan.dev](https://askmaan.dev)**

AskMaan is my personal website, built as an AI chatbot instead of a static portfolio. The assistant's name is Twin: a digital twin of me that visitors (recruiters, colleagues, anyone curious) can ask about my background, education, projects, skills, and experience, and it answers in a structured, conversational way, like talking to an assistant who knows my work inside out.

## What it does

- Answers questions about me from a curated knowledge base. It doesn't invent facts, and anything it doesn't know gets redirected to my LinkedIn
- Adapts its reply format to the question: short prose, bullet points, or numbered lists, with key facts bolded
- Stays on-topic and resists prompt-injection attempts through layered defenses
- Speaks both English and Arabic, with a one-tap language toggle in the header. The Arabic side has the exact same knowledge, rules, and way of talking

Twin is still learning and is still being fed information, so it keeps getting better over time.

## How it works

The whole site is a single self-contained `index.html` with markup, styles, logic, fonts, and images all inlined. No build step, no dependencies to install, no framework boilerplate to maintain.

The site is fully bilingual: a one-tap toggle in the header switches the entire interface and Twin's answers between English and Arabic, including a proper right-to-left layout in Arabic.

The chat is powered by **Google Gemini 2.5 Flash**. The browser never talks to Google directly: requests go through a **Cloudflare Worker** proxy that only accepts requests originating from askmaan.dev.

```
Browser (askmaan.dev)  →  Cloudflare Worker  →  Gemini API
```

## Tech stack

- **Frontend:** Single-file HTML/CSS/JS with a React-based runtime, fully inlined
- **AI model:** Google Gemini 2.5 Flash via the `generateContent` REST API
- **API proxy:** Cloudflare Worker (free tier) with origin allowlisting
- **Hosting:** GitHub Pages (free), deployed straight from this repo
- **Domain:** askmaan.dev, registered on Namecheap, connected via DNS A records + the `CNAME` file in this repo

## Design

- **Typography:** Thmanyah Serif Display (headings, logo, favicon) and Thmanyah Sans (UI and body text), both embedded as web fonts
- **Palette (dark mode):** background `#0A0A0B`, panel `#111113`, text `#D9D9D6`, bright text `#F0F0EE`, borders `#1D1D1F` / `#303034`, muted `#66666A`
- Switchable accent themes and a subtle animated emoji backdrop

## Repo contents

- `index.html`: the entire site
- `banner.png`: the README banner
- `CNAME`: custom domain config for GitHub Pages
- `README.md`: this file

## Updating

I regenerate the site as a single file and replace `index.html` here. GitHub Pages redeploys automatically within about a minute.

## Why the code is public

This site was a fun experiment from my end, and I'm keeping the tech stack and code viewable, so if you're curious how it works, check it out and learn from it.

---

**By: Maan Almakhlifi 👨‍💻**

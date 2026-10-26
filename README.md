# Hi, I'm Puneeth V 👋

Backend-focused developer | B.Tech CSE student at PES University

I build and ship systems end to end: database schema, API, background workers, containerized local environments and cloud deployment. I'm especially interested in infrastructure automation, reliability and AI-assisted troubleshooting, and I'm keen to grow into cloud and Kubernetes platform engineering.

<p align="left">
  <a href="https://github.com/PuneethV333/"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/puneeth-v-756832366/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
  <a href="https://puneeth-v.vercel.app/"><img src="https://img.shields.io/badge/Portfolio-000000?style=for-the-badge&logo=vercel&logoColor=white" /></a>
  <a href="https://www.npmjs.com/package/vima-clt"><img src="https://img.shields.io/badge/npm-vima--clt-CB3837?style=for-the-badge&logo=npm&logoColor=white" /></a>
  <a href="https://www.instagram.com/333_appu_x/"><img src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white" /></a>
</p>

---

## 📊 GitHub Analytics

<p align="center">
  <!-- <img src="https://github-readme-stats.vercel.app/api?username=PuneethV333&show_icons=true&theme=tokyonight&hide_border=true&count_private=true" height="165" /> -->
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=PuneethV333&theme=tokyonight&hide_border=true" height="165" />
</p>

<p align="center">
  <!-- <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=PuneethV333&layout=compact&theme=tokyonight&hide_border=true" height="165" /> -->
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=PuneethV333&theme=tokyo-night&hide_border=true" />
</p>

---

## 🚀 Projects

### 🆘 bSafe: Silent SOS Emergency Web App
A full-stack alert system delivered across a monorepo, from schema design to production in 12 planned phases.

- **Stack:** NestJS, React, PostgreSQL, Redis, Docker
- **Real-time and queues:** Streams live location over Socket.IO and dispatches SMS and email notifications through BullMQ queue workers, with an admin dashboard for monitoring and retrying failed deliveries
- **Hardening:** Firebase ID-token verification guards, Redis-backed per-route rate limiting and caching, request validation, and a health endpoint that reports service and Redis status
- **Infra and docs:** Local database via Docker Compose, consistent lint, typecheck and build scripts across workspaces, plus a production deployment runbook, PRD, ER diagram and API route documentation
- **Deployment:** Vercel (web), Render (API), Neon (PostgreSQL), Upstash (Redis)

**GitHub:** [github.com/PuneethV333/bsafe](https://github.com/PuneethV333/bsafe)
**Live:** [bsafe-zeta.vercel.app](https://bsafe-zeta.vercel.app/)

### 🧪 Vima Tester
A web-based Postman alternative for testing APIs running on your own `localhost`. Browsers can't read `localhost` responses because of CORS, so requests never originate in the browser: a relay server hands each job to a local agent on your machine, which makes the real HTTP call.

- **Stack:** NestJS, React + Vite, Prisma, PostgreSQL, TanStack Query, Zod, TypeScript npm-workspaces monorepo
- **Architecture:** Browser → HTTPS → relay server → WebSocket → local agent (`vima-tunneler`) → HTTP → `localhost`
- **Relay:** NestJS server with agent pairing codes (rate limited), a WebSocket gateway for agents, a job dispatch API and a health endpoint that returns 503 when the database is unreachable
- **Agent (`vima-tunneler`):** published npm CLI with `pair`, `start`, `status` and `logout` commands, automatic reconnect with jittered backoff, and at-least-once result delivery using sequence numbers, acks and replay
- **Security:** Firebase auth (Google and email/password) verified by the relay, jobs only go to the user's own paired agent, loopback-only targets, no redirect following, and restricted token file permissions
- **Quality and deployment:** shared protocol package with Vitest, Jest and node:test suites, GitHub Actions CI for the agent, and the web app deployed on Vercel

**GitHub:** [github.com/vima-tester/vima-tester](https://github.com/vima-tester/vima-tester)
**Agent:** [github.com/vima-tester/vima-tunneler](https://github.com/vima-tester/vima-tunneler)
**Live:** [vima-tester-web.vercel.app](https://vima-tester-web.vercel.app/)
**npm:** [npmjs.com/package/vima-tunneler](https://www.npmjs.com/package/vima-tunneler)

### 📚 Chapter Tracker (bookmark-manager)
A service that imports browser bookmark exports, scrapes the latest chapter from supported sites and highlights new releases in a per-user library.

- **Stack:** NestJS, Prisma, PostgreSQL, Redis, React
- **Caching and scraping:** Redis caching with a 10-minute TTL and safe per-site concurrency limits to cut redundant scraping and respect source rate limits
- **Auth and deployment:** Firebase auth with token verification in the NestJS API; frontend on Vercel, API on Render, with Neon PostgreSQL and Upstash Redis
- **Open source:** GitHub Actions workflows and contribution guidelines for adding new site scrapers with tests and fixtures

**GitHub:** [github.com/PuneethV333/bookmark-manager](https://github.com/PuneethV333/bookmark-manager)
**Live:** [bookmark-manager-zeta.vercel.app](https://bookmark-manager-zeta.vercel.app/)

### ⚡ VIMA CLI
A Node.js-based scaffolding tool that creates scalable frontend and backend projects with multiple variants, supporting React + Vite, Express APIs, MongoDB, Prisma, Firebase, and SQL setups.

- **Scaffolding:** Spins up production-ready project structures in seconds instead of hand-rolling boilerplate each time
- **Variants:** Mix and match frontend (React + Vite) and backend (Express) setups with your choice of database layer: MongoDB, Prisma, Firebase, or SQL
- **Published as a package:** Installable and usable directly via npm

**GitHub:** [github.com/PuneethV333/Vima-Clt-tool](https://github.com/PuneethV333/Vima-Clt-tool)
**Live:** [vima-clt-tool.vercel.app](https://vima-clt-tool.vercel.app/)
**npm:** [npmjs.com/package/vima-clt](https://www.npmjs.com/package/vima-clt)

### 🏠 Co-Living Platform
A full-stack co-living marketplace connecting tenants and property owners, built with semantic matching under the hood.

- **Frontend:** React/TypeScript, Firebase Auth, TanStack Query, Tailwind CSS
- **Backend:** Node.js, MongoDB, Redis caching, Qdrant (vector DB) with Google Gemini embeddings for semantic property and roommate matching
- **Features:** Multi-step onboarding for tenants and owners, property browsing and detail pages, a create-property wizard, a roommate preference survey, and an owner dashboard

**GitHub:** [github.com/PuneethV333/Co-Living](https://github.com/PuneethV333/Co-Living)
**Live:** [co-living-two.vercel.app](https://co-living-two.vercel.app/)

### 🏘️ Hometown Hub
A community platform with hometown-based feeds, events with RSVP, announcements and notifications, plus an admin dashboard with platform KPIs and a moderation queue.

- **Stack:** MERN, TypeScript, Tailwind CSS, TanStack Query
- **Backend:** Mongoose data models and a typed Express REST API
- **Docs:** PRD and technical documentation, with a deployment-ready build

**GitHub:** [github.com/PuneethV333/Hometown_Hub](https://github.com/PuneethV333/Hometown_Hub)
**Live:** [hometown-hub-five.vercel.app](https://hometown-hub-five.vercel.app/)

### 💙 Trust Care
A monorepo application with a React + Vite frontend and a NestJS API backed by PostgreSQL through Prisma migrations, deployed on Vercel.

- **Stack:** NestJS, Prisma, PostgreSQL, React, TypeScript

**GitHub:** [github.com/PuneethV333/Trust-care](https://github.com/PuneethV333/Trust-care)
**Live:** [trust-care-sage.vercel.app](https://trust-care-sage.vercel.app/)

---

## 💼 Experience

**MERN Stack Intern — Unified Mentor Private Limited** (6 months)

- Built backend services and REST APIs on the MERN stack (MongoDB, Express, React, Node.js) for a production-style co-living platform
- Designed data models and API contracts, and collaborated on the integration between the React frontend and Node.js services
- Worked in a team workflow with Git and delivered features end to end, from schema design to a deployed application

---

## 🛠️ Skills

**Languages**

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white)
![C](https://img.shields.io/badge/C-A8B9CC?style=for-the-badge&logo=c&logoColor=black)
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)

**Backend and Automation**

![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)
![Express](https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white)
![NestJS](https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi&logoColor=white)
![Socket.IO](https://img.shields.io/badge/Socket.IO-010101?style=for-the-badge&logo=socketdotio&logoColor=white)
![BullMQ](https://img.shields.io/badge/BullMQ-DC382D?style=for-the-badge)

**DevOps and Cloud**

![Docker](https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)
![Vercel](https://img.shields.io/badge/Vercel-000000?style=for-the-badge&logo=vercel&logoColor=white)
![Render](https://img.shields.io/badge/Render-46E3B7?style=for-the-badge&logo=render&logoColor=black)
![Neon](https://img.shields.io/badge/Neon-00E599?style=for-the-badge&logoColor=black)
![Upstash](https://img.shields.io/badge/Upstash-00E9A3?style=for-the-badge&logoColor=black)

**Databases and Caching**

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-DC382D?style=for-the-badge&logo=redis&logoColor=white)
![Qdrant](https://img.shields.io/badge/Qdrant-DC244C?style=for-the-badge&logoColor=white)
![Prisma](https://img.shields.io/badge/Prisma-2D3748?style=for-the-badge&logo=prisma&logoColor=white)

**AI and Auth**

![Ollama](https://img.shields.io/badge/Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white)
![Gemini](https://img.shields.io/badge/Gemini_Embeddings-8E75B2?style=for-the-badge&logo=googlegemini&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase_Auth-FFCA28?style=for-the-badge&logo=firebase&logoColor=black)

**Frontend**

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![React Native](https://img.shields.io/badge/React_Native-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)
![TanStack Query](https://img.shields.io/badge/TanStack_Query-FF4154?style=for-the-badge&logo=reactquery&logoColor=white)
![Three.js](https://img.shields.io/badge/Three.js-000000?style=for-the-badge&logo=threedotjs&logoColor=white)
![GSAP](https://img.shields.io/badge/GSAP-88CE02?style=for-the-badge&logo=greensock&logoColor=white)

---

## 🎓 Education
**B.Tech in Computer Science and Engineering** — PES University, Bengaluru

---

## 🏆 Achievements and Certifications

- **National-Level CTF Competition** — Cyovault, PES University (2026): secured 20th place in a national-level Capture The Flag (CTF) cybersecurity competition
- **React Certificate** — HackerRank

---

## 🔭 Learning Focus
Linux administration and GitOps, Infrastructure as Code, and GenAI tools for troubleshooting and workflow automation.

---

## 🌐 Portfolio
[puneeth-v.vercel.app](https://puneeth-v.vercel.app/)

---

## 📫 Get in touch
Feel free to explore my repos or reach out. I'm always happy to talk about backend architecture, infrastructure, or anything I'm building.

[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/PuneethV333/)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/puneeth-v-756832366/)
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/333_appu_x/)

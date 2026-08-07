<h1 align="center">Hi, I'm Burak Şahinkaya 👋</h1>

<p align="center">
  <b>AI Engineer · Production RAG, Agents & LLM Systems</b><br>
  Founder & sole engineer of <a href="https://sapenor.com">Sapenor</a>, a legal-tech platform for Turkish lawyers.
</p>

<p align="center">
  <a href="https://linkedin.com/in/burak-sahinkaya"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:burak.avaz.69@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://sapenor.com"><img src="https://img.shields.io/badge/Sapenor-4F46E5?style=for-the-badge&logo=vercel&logoColor=white" alt="Sapenor"></a>
</p>

---

## 🧠 About Me

- 🤖 AI engineer and founder of **Sapenor**, a production legal-AI platform for Turkish lawyers
- 🏗️ I **build the infrastructure** — a self-hosted RAG stack written without an orchestration framework, not an API I call
- 📏 I **measure before I ship**: an eval harness and deterministic checks decide what goes to production, including what doesn't
- 🎮 Before AI: founded a game studio and shipped **3 apps** to the App Store and Play Store
- 🎓 B.Eng. Mathematical Engineering, Yıldız Technical University

## 🛠️ Tech Stack

<p align="center">
  <img src="https://skillicons.dev/icons?i=python,fastapi,ts,js,nodejs,nextjs,react,tailwind,rust&perline=9" alt="stack row 1"><br>
  <img src="https://skillicons.dev/icons?i=postgres,supabase,firebase,flutter,dart,cs,unity,git,vercel&perline=9" alt="stack row 2">
</p>

<p align="center"><sub>
RAG · vector search · bge-m3 · HNSW · tool-calling agents · LLM evaluation · citation verification · model routing · pgvector · Chrome Extensions (MV3) · Row-Level Security
</sub></p>

## ⚖️ Sapenor — production legal AI

An end-to-end platform for Turkish lawyers: retrieval-augmented research, drafting, document analysis, litigation simulation, and integration with the national court system (UYAP). Designed, built and operated solo — a product in production, not a prototype.

- **Self-hosted RAG, no framework.** A Python/FastAPI retrieval service on `bge-m3`, two-stage vector search — binary-quantized HNSW candidates re-ranked by cosine on `halfvec(1024)` — over PostgreSQL + `pgvector`.
- **Measured retrieval.** Reciprocal rank **0.38 → 0.92**; empty-result queries **4/8 → 0/8**, driven by deterministic legal-abbreviation expansion and query distillation.
- **Reliability first.** A three-layer eval harness, and **deterministic citation verification without an LLM** — decision numbers in an answer matched against the chunks actually retrieved, so hallucinations are caught at zero API cost.
- **Cost engineering.** A hybrid router sends simple questions to a model ~13× cheaper (fail-open, env kill-switch), plus prompt caching and delta-only case memory → **~67%** lower inference cost per question.
- **Shipped.** Next.js 16 · React 19 · TypeScript · Supabase (Auth + RLS) · streaming chat · a Manifest V3 Chrome extension for UYAP import · three LLM providers behind a registry whitelist.

## 🚀 Featured Projects

| Project | Description | Stack |
| --- | --- | --- |
| [**circlio-split-bills**](https://github.com/burakSahinkaya/circlio-split-bills) | Shared-expense app — groups, live balances, settlement suggestions. Shipped to the App Store and Play Store. | Flutter · Firebase · Riverpod |
| [**KeyClickSoundApp**](https://github.com/burakSahinkaya/KeyClickSoundApp) | A click on every keystroke, system-wide. A listen-only keyboard hook that never records what you type. | Tauri · Rust · React |
| [**pdf-book-translator**](https://github.com/burakSahinkaya/pdf-book-translator) | Translates English book PDFs into Turkish, keeping chapters and images. Two-tier OCR, free offline first. | Python · PySide6 · PyMuPDF |
| [**CarpetWebsite2**](https://github.com/burakSahinkaya/CarpetWebsite2) | A carpet-showroom storefront — filterable catalogue, no framework, no build step. [Live »](https://buraksahinkaya.github.io/CarpetWebsite2/) | HTML · CSS · JS |

## 🔥 GitHub Streak

<p align="center">
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=burakSahinkaya&theme=tokyonight&hide_border=true" alt="GitHub streak">
</p>

<p align="center"><sub>Most of my day-to-day is in Sapenor's private repository — the graph here shows only the public side.</sub></p>

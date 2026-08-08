<h1 align="center">Hi, I'm Burak Şahinkaya 👋</h1>

<p align="center">
  <b>Software Engineer</b> · full-stack, RAG/LLM systems & mobile<br>
  Founder & sole engineer of <a href="https://sapenor.com">Sapenor</a> (legal-tech) · founder of <a href="https://bishamongames.com">Bishamon Games</a> (mobile studio)
</p>

<p align="center">
  <a href="https://linkedin.com/in/burak-sahinkaya"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="mailto:burak.avaz.69@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://sapenor.com"><img src="https://img.shields.io/badge/Sapenor-4F46E5?style=for-the-badge&logo=vercel&logoColor=white" alt="Sapenor"></a>
  <a href="https://bishamongames.com/portfolio"><img src="https://img.shields.io/badge/Bishamon_Games-111827?style=for-the-badge&logo=itchdotio&logoColor=white" alt="Bishamon Games"></a>
</p>

---

## 🧠 About Me

- 💻 Software engineer; founder of **Sapenor** (legal-tech) and **Bishamon Games** (mobile studio)
- 🏗️ I **build the infrastructure** — I built and run my own RAG stack from scratch, instead of calling a hosted one
- 📏 I **measure before I ship**: an eval harness and deterministic checks decide what goes to production, including what doesn't
- 📱 Shipped several apps to the **App Store and Play Store**, and built the [Bishamon Games](https://bishamongames.com) studio site
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

## 🚀 Open-source projects

Source is on GitHub — each one built to run, not to demo.

| Project | Description | Stack |
| --- | --- | --- |
| [**circlio-split-bills**](https://github.com/burakSahinkaya/circlio-split-bills) | Shared-expense app — groups, live balances, settlement suggestions. [On the App Store »](https://apps.apple.com/us/app/circlio-split-bills/id6761620867) | Flutter · Firebase · Riverpod |
| [**KeyClickSoundApp**](https://github.com/burakSahinkaya/KeyClickSoundApp) | A click on every keystroke, system-wide. A listen-only keyboard hook that never records what you type. | Tauri · Rust · React |
| [**pdf-book-translator**](https://github.com/burakSahinkaya/pdf-book-translator) | Translates English book PDFs into Turkish, keeping chapters and images. Two-tier OCR, free offline first. | Python · PySide6 · PyMuPDF |
| [**CarpetWebsite2**](https://github.com/burakSahinkaya/CarpetWebsite2) | A carpet-showroom storefront — filterable catalogue, no framework, no build step. [Live »](https://buraksahinkaya.github.io/CarpetWebsite2/) | HTML · CSS · JS |

## 📱 Shipped to the stores

Products live on the App Store and Google Play. More at the [Bishamon Games portfolio »](https://bishamongames.com/portfolio)

| App | Description | Stack |
| --- | --- | --- |
| [**Circlio**](https://apps.apple.com/us/app/circlio-split-bills/id6761620867) | Split shared expenses with groups, multi-currency and real-time sync. | Flutter · Firebase |
| [**PetlyFans**](https://apps.apple.com/us/app/petlyfans/id6755064104) | A social network for pets — real-time chat, feed, and swipe matching, on a full Firebase backend. | Unity · Firebase |
| [**Skeleton Survivors**](https://apps.apple.com/tr/app/skeleton-survivors/id6744177815) | A mobile roguelike, published end-to-end with in-app purchases and ads, tuned across a wide device range. | Unity · C# |
| [**Drive Quest**](https://apps.apple.com/tr/app/drive-quest-online-araba-oyunu/id6504999996) | An online racing game — gameplay mechanics, QA and localization. | Unity · C# |

I also led prototyping and optimization for **Car King**, a multiplayer mobile game published on iOS and Android, and built the **[Bishamon Games](https://bishamongames.com)** studio site itself.

<p align="center"><sub>Most of my day-to-day work lives in Sapenor's private repository.</sub></p>

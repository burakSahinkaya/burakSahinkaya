<h1 align="center">Burak Şahinkaya</h1>

<p align="center">
  <strong>AI engineer — production RAG, agents and LLM systems.</strong><br>
  Founder and sole engineer of <a href="https://sapenor.com">Sapenor</a>, a legal-tech platform for Turkish lawyers.
</p>

<p align="center">
  <a href="https://sapenor.com"><img alt="Sapenor" src="https://img.shields.io/badge/product-sapenor.com-4F46E5"></a>
  <a href="https://linkedin.com/in/burak-sahinkaya"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-burak--sahinkaya-0A66C2?logo=linkedin&logoColor=white"></a>
</p>

---

I build the infrastructure rather than call an API for it, and I measure before I ship. The two things I keep coming back to are **self-hosted retrieval** — a RAG stack written without an orchestration framework — and an **evaluation discipline** that decides what goes to production, including what doesn't.

## Sapenor — production legal AI

An end-to-end platform for Turkish lawyers: retrieval-augmented research, drafting, document analysis, litigation simulation, and integration with the national court system (UYAP). Designed, built and operated solo. Not a prototype — a product in production.

**Self-hosted RAG, no framework**
- A separate Python/FastAPI retrieval service on `bge-m3` embeddings.
- Two-stage vector search: candidate generation over a binary-quantized HNSW index (Hamming), then cosine re-ranking on `halfvec(1024)` — PostgreSQL + `pgvector`.
- A parity test guarding against corpus/query embedding drift (`cos ≥ 0.9999`) — easy to skip, quietly quality-destroying if you do.
- A Turkish legal corpus: Court of Cassation, Council of State, regional courts of appeal, the Constitutional Court, the ECtHR, the Public Procurement Authority, legislation, Official Gazette PDFs, EU law / CJEU, and international treaties.
- **Measured:** retrieval reciprocal rank **0.38 → 0.92**; empty-result queries **4/8 → 0/8**.

**Agents**
- Five agent surfaces — chat, document analysis, petition generation, litigation simulation, budgeted case-file reading — built on the Vercel AI SDK with `tool()` + zod schemas, orchestration and retry logic hand-rolled rather than taken from LangChain. A deliberate, documented architectural choice.
- A budgeted reader capped at 6 reads / 8 searches, so the model can't scan a file indefinitely. Web search via Tavily.

**Reliability and evaluation** — the part I care about most
- A three-layer eval harness: retrieval probes, LLM-as-judge answer scoring, and head-to-head model comparison (`npm run eval`).
- **Deterministic citation verification without an LLM:** decision numbers in an answer are matched against the chunks the agent actually retrieved and split into grounded / secondary / ungrounded. Hallucination detection at zero API cost, with a low-cost LLM semantic check as a second layer.
- The call to **not** promote a new frontier model was made on measured results, not a hunch.

**Cost**
- A hybrid router: a cheap classifier labels a question simple or complex, and simple ones drop to a model ~13× cheaper. Fail-open, with an environment kill-switch.
- Anthropic prompt caching; case memory that summarizes a file once and then sends only the delta.
- **Measured:** ~**67%** lower inference cost per question; petition generation **$0.95 → $0.65**.

**Application & infrastructure**
- Next.js 16 (App Router), React 19, TypeScript, Tailwind v4, streaming chat via the Vercel AI SDK.
- Supabase — PostgreSQL, Auth, Row-Level Security; 54 route handlers with correct HTTP semantics (quota → 402, rate limit → 429).
- A Manifest V3 Chrome extension that imports case files from UYAP under the lawyer's own session, with a durable job queue in the service worker (survives sleep/wake), backpressure handling, and an OCR queue.
- Three LLM providers behind a registry whitelist (OpenAI, Anthropic, DeepSeek); a document pipeline for PDF / DOCX / UYAP `.udf` (a closed ZIP+XML format I wrote a parser for) with provider-swappable OCR.

## Published projects

Smaller things, shipped end-to-end and public. Each one I built to run, not to demo.

| Project | What it is | Stack |
| --- | --- | --- |
| [**circlio-split-bills**](https://github.com/burakSahinkaya/circlio-split-bills) | Shared-expense app — groups, live balances, settlement suggestions. Shipped to the App Store and Play Store. | Flutter · Firebase · Riverpod |
| [**KeyClickSoundApp**](https://github.com/burakSahinkaya/KeyClickSoundApp) | A click sound on every keystroke, system-wide. A listen-only keyboard hook that never records what you type. | Tauri · Rust · React |
| [**pdf-book-translator**](https://github.com/burakSahinkaya/pdf-book-translator) | Translates English book PDFs into Turkish, keeping chapters and images. Two-tier OCR, free offline first. | Python · PySide6 · PyMuPDF |
| [**CarpetWebsite2**](https://github.com/burakSahinkaya/CarpetWebsite2) | A carpet-showroom storefront — filterable catalogue, no framework, no build step. [Live](https://buraksahinkaya.github.io/CarpetWebsite2/). | HTML · CSS · JS |

## Before AI: mobile and games

Founder of **Bishamon Games** (2025–), where I shipped three applications end-to-end to both stores — Circlio in Flutter, plus PetlyFans and Skeleton Survivors in Unity/Firebase with real-time features, monetization and publishing. Earlier: second lead developer on *Car King* (a multiplayer mobile game, iOS + Android) at Avo Games, gameplay work at Tridy Games, and functional QA at Testronic Labs.

## What I work with

**AI / LLM** — RAG architecture, vector search, `bge-m3` embeddings, binary quantization, HNSW, two-stage retrieval and re-ranking, tool-calling agents, prompt engineering, prompt caching, LLM-as-judge evaluation, building eval harnesses, guardrail design, citation verification, model routing, token/cost optimization, multimodal vision

**Languages & frameworks** — Python, FastAPI, TypeScript, Node.js, Next.js, React, Tailwind, Vercel AI SDK, zod, Dart/Flutter, C#/Unity, Rust *(desktop, via Tauri)*

**Data & backend** — PostgreSQL, `pgvector`, Supabase, SQL, REST API design, async queue/worker architectures, backpressure and rate limiting, PDF/DOCX/OCR pipelines

**Also** — Chrome extensions (Manifest V3), Firebase, Git, Auth and Row-Level Security, security hardening, KVKK/GDPR compliance, App Store / Play Store publishing

<sub>B.Eng. Mathematical Engineering, Yıldız Technical University · Istanbul, Turkey</sub>

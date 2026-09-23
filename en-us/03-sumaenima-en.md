---
tags: [meta, docs, personal]
---

# 🚀 Sumænimá Hub v3.1.0

**Private, Local-First Intelligence & Ethnographic Data Capture Platform**

[sumaenima.chimaera-heptatonic.ts.net](https://sumaenima.chimaera-heptatonic.ts.net) | [github.com/ceduardorodrig](https://github.com/ceduardorodrig)

---

## 🎯 Overview

**Founder & Product Owner:** Carlos Eduardo Rodrigues

Sumænimá is my life project. It has existed for nearly 10 years as an independent creative entity, running alongside formal employment throughout my entire career. It was born from a conviction: qualitative research — especially with traditional communities, Indigenous peoples, and vulnerable groups — should never depend on big tech infrastructure. What began as an independent research practice has matured into **Sumænimá Hub v3.1.0**: a unified monorepo running a 100% native Rust backend (`stenio-server` Axum 0.8 / Tokio / SQLx) paired with a high-refresh React 19 client accelerated by in-browser Rust WebAssembly DSP.

The core mission is to operate a sovereign **Data Bureau** with an anthropological soul: an institutional engine producing projects like *Tô no Mapa*, territorial datasets, and ethnographic research at scale — uniting science, territory, and systems engineering in a deterministic, private way.

The foundation of the entire ecosystem is **StenioSentinel v3.1.0** — our open-source AI agent governance sentinel written in pure **Rust 2024** (now publicly available at `ceduardorodrig/STENIO-SENTINEL`). It enforces strict architectural rules in sub-milliseconds (<1ms to <500ms), provides automated violation rollback, and guarantees that autonomous coding agents adhere to deterministic quality gates (Rule 0).

The entire Sumænimá ecosystem totals **~8M+ lines and growing** (includes source code, documentation, and multimodal assets) — across 1,227+ tightly governed files across our 5-node homelab infrastructure.

---

## 🖥️ Design & Experience

The Sumænimá Hub interface follows **Material Design 3** with glassmorphism, Lexend typography, and dynamic theming — fully responsive across every device.

| Mobile · iPhone SE | Tablet · iPad Pro | Desktop |
|:---:|:---:|:---:|
| <img src="../assets/hub-mobile.png" width="220" alt="Mobile" /> | <img src="../assets/hub-tablet.png" width="280" alt="Tablet" /> | <img src="../assets/hub-desktop.png" width="400" alt="Desktop" /> |

---

## ❓ The Problem

Researchers, NGOs, and institutions working with sensitive data face a dilemma:
- Cloud services (Google, OpenAI, AWS) are expensive and require sending proprietary audio and transcripts to foreign corporate servers
- Local alternatives are fragmented, poorly documented, and require deep technical expertise
- LGPD, GDPR, and ethics committees increasingly restrict cloud solutions for deliberative research and community records

Sumænimá Hub solves this by offering an integrated, sovereign platform — local, private, and deterministic.

---

## 💡 The Solution — Sumænimá Hub v3.1.0

### 🏛️ Bureau Sumænimá

#### 🎙️ StênioREC — Real-Time Transcription Cockpit
**Status:** 🟢 **Production** — Fully validated in high-stakes field and governmental reporting

<p align="center">
  <img src="../assets/hub-rec.png" width="600" alt="StênioREC — Transcription Cockpit" />
</p>

Real-time transcription cockpit with 100% local inference. Captures audio via browser `AudioWorklet` with in-browser Rust WebAssembly acoustic RMS (VAD), transcribes with whisper.cpp accelerated natively by CUDA 13 on NVIDIA RTX 5050 (Blackwell sm_120), and purifies with Gemma 3 IT in a parallel pipeline — 100% local processing; transcripts synced on demand to Google Docs with per-user OAuth authentication.

**✨ Highlights:**
- 🧠 Dual-stage Neural Flow pipeline: Whisper draft sub-500ms + parallel Gemma 3 purification
- 🔒 ~2h offline buffer (57MB RAM + 171MB IndexedDB), designed to prevent audio loss without network
- 📝 Automatic Google Doc creation per user with own credentials
- 🎛️ Real-time cockpit: GPU temp, VRAM, drift, entropy, network status
- 📱 Wake Lock API — recording doesn't suspend on mobile
- ⚡ Auto-unloads VRAM on context unlock

**🎯 For:** Ethnographic reporting, qualitative interviews, public hearings, corporate minutes.

### 🗂️ StênioPANEL — Workshop Scanner
**Status:** 🔴 Concept — architecture defined, code implemented, awaiting resources

<p align="center">
  <img src="../assets/hub-panel.png" width="600" alt="StênioPANEL — Post-It Scanner" />
</p>

Transforms photos of physical panels (post-its, whiteboards, flip charts) into native Obsidian `.canvas` files — with 100% local computer vision. 4-stage pipeline: zero-shot detection (GroundingDINO + SAM 2), dual OCR with automatic fallback (PaddleOCR 93.5% / EasyOCR 89.2%), DBSCAN + edge organizer, and official Obsidian Canvas spec validator.

**✨ Highlights:**
- 🎯 Zero-shot detection: no fine-tuning needed for any event
- 🔍 Dual OCR with automatic fallback between PaddleOCR and EasyOCR
- 🧩 Generates 100% Obsidian-compatible `.canvas` files
- 📸 Processes up to 50MP photos with tiling algorithm
- 🧠 Optional Gemma 3 semantic review pass
- 🔄 VRAM Mutex: prioritizes GPU with StênioREC; smart Valkey queue if GPU busy
- 🗑️ Source images shredded after processing — only metadata persists

**🎯 For:** Workshop facilitators, design thinking practitioners, Agile coaches, ethnographers.

### 🔍 StênioDIVE — Semantic Mining
**Status:** 🔴 Concept — architecture defined, search engine implemented, awaiting resources

<p align="center">
  <img src="../assets/hub-dive.png" width="600" alt="StênioDIVE — Knowledge Graph" />
</p>

Unified semantic search engine mining REC transcripts, PANEL boards, Obsidian notes, and public images into a single interactive graph. Combines BM25 lexical search with vector cosine similarity via 384-d ONNX embeddings (CPU, no GPU required), fused by Reciprocal Rank Fusion (RRF).

**✨ Highlights:**
- 🔎 Hybrid BM25 + vector cosine search with RRF fusion
- 📄 Indexes 4 simultaneous sources: Google Docs, Canvas Boards, Obsidian, images
- 🧠 384-d ONNX embeddings 100% CPU, no GPU dependency
- ⚙️ Async pipeline with SHA-256 cache and OCR cache
- 🎛️ Source filters: transcripts, panels, notes
- 🔗 Interactive graph of wikilinks, tags, and semantic connections

**🎯 For:** Researchers, analysts, knowledge managers — anyone needing cross-dataset search across ethnographic data.

### 🌡️ DataVis — Climate Visualizations
**Status:** 🔴 Concept — PM2.5 visualization unstable; remaining modules in early stage

<p align="center">
  <img src="../assets/hub-datavis.png" width="600" alt="DataVis — PM2.5 Particles" />
</p>

Generative climate visualizations in real time. Particles react to real air quality data (PM2.5), wind speed, and direction — turning numbers into interactive art. Particle color shifts by severity (amber to smoky red), turbulence follows real wind, and the mouse creates force fields on the canvas.

**✨ Highlights:**
- 🎨 Generative canvas with up to 300 particles reacting to real data
- 🌬️ Real wind speed and direction integrated: turbulence proportional to velocity
- 🖱️ Particles interact with mouse cursor (120px force field)
- 🏥 5-level WHO classification with dynamic gauge
- 🔄 Dual data sources: WAQI and OpenAQ (swappable)
- ⚡ Adaptive cache: 30s to 15min by popularity
- 🧊 Microservice architecture — runs on ybyra edge node (Oracle, 1GB RAM)

**🎯 For:** Environmental researchers, climate activists, data journalists, general public.

### ⚙️ Admin — Platform Management
**Status:** 🟡 Partial — dashboard, auth, and contacts OK; basic ERP; image library and CMS in development

<p align="center">
  <img src="../assets/hub-admin.png" width="600" alt="Admin — Dashboard" />
</p>

Central platform administration dashboard: metrics, users, contacts, images, and full ERP (organizations, leads, contracts, invoices, projects). 5-tab navigation with Material Design 3, glassmorphism, and LGPD compliance.

**✨ Highlights:**
- 📊 Live dashboard with 7 metrics: users, WS sessions, projects, revenue, characters, audio, tokens
- 🗂️ Full ERP: organizations, Kanban leads, contracts, invoices, projects with task board
- 👤 User management with admin badge protected by env var (single owner)
- 🔒 LGPD compliance: email masking, IP audit logs, consent banner, terms versioning
- 📈 Embedded Umami Analytics with dynamic CSP
- 🖼️ Image library and CMS with TipTap WYSIWYG editor
- 📬 Contact CRUD with 3 states: unread, read, archived
- 🛡️ Protected route — only env-var-configured owner accesses admin

**🎯 For:** Platform administrator, system operator, business manager.

### Cross-Cutting Features

- SaaS with Mercado Pago subscription billing, Google OAuth with encrypted tokens
- CMS with TipTap WYSIWYG editor and image library
- ERP: organizations, members, leads, contracts, invoices, projects
- Observability: Grafana + Loki + Promtail

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|-----------|
| **Backend** | 100% Rust (`stenio-server`) · Axum 0.8 · Tokio Work-Stealing · SQLx · whisper.cpp |
| **Frontend** | React 19 · Vite · TypeScript 6 · Rust WebAssembly (AudioWorklet DSP) · Tailwind |
| **Database** | PostgreSQL 16 (pgvector) · SQLx (compile-time checked queries & migrations) |
| **Cache/State** | Valkey 8 (in-memory state, pub/sub, real-time queues) |
| **AI Audio** | whisper.cpp CUDA 13 (NVIDIA RTX 5050 sm_120) · Gemma 3 IT |
| **Infra** | Docker Swarm (kavure manager, psicopompo worker) · Tailscale WireGuard Mesh |
| **Network** | Tailscale Funnel Gateway (`ybyra`) · Nginx reverse proxy |
| **Observability** | Prometheus · Grafana · Loki · Promtail · Alertmanager · ntfy |
| **Governance** | StenioSentinel v3.1.0 (pure Rust 2024 static audit engine, sub-millisecond execution) |
| **Ecosystem** | **~8M+ lines and growing** · 1,227+ files · 10 yr (project) · ~2.5 yr (active engineering) |

---

## 🛡️ StenioSentinel v3.1.0 — Static Governance Sentinel

This is Sumænimá's deepest engineering foundation. StenioSentinel is an open-source static analysis and architectural governance sentinel written in pure **Rust 2024** (`ceduardorodrig/STENIO-SENTINEL`). It is designed to govern human-AI pair programming and autonomous coding agents across the entire lifecycle: code, documentation, infrastructure, and agent behavior itself.

- **Pure Rust 2024 Architecture:** Sub-millisecond static auditing (<1ms to <500ms) leveraging Rayon multi-threading.
- **Rule 0 Quality Gate:** Mandatory, non-bypassable pre-commit verification. Zero tolerance for unverified code or bypass attempts (`// @ts-ignore`, `.unwrap()` in production Rust).
- **Sectorized Scopes:** Granular auditing for `hub` (Rust backend, React 19 frontend), `homelab` (infrastructure, systemd, mounts), and `vault` (Obsidian tags and links).
- **Automated Self-Remediation (`--fix`):** Line-level automated repairs with rollback to prevent regressions.

### 🛡️ Anti-Bypass Architecture (10 Layers)

| Layer | Mechanism | What It Prevents |
|-------|-----------|------------------|
| 1. **Pre-Commit Hooks** | `pre-commit-config.yaml` — gates P0+sec+doc | Commit without static checks |
| 2. **Bypass Guard** | `sec_ai_bypass_guard` — P0 driver | `--no-verify`, `\|\| true`, `2>/dev/null`, CI `continue-on-error` |
| 3. **No-Bypass Ops** | `sec_no_bypass` — P0 driver | Manual `rsync+ssh`, `docker compose`, `npm run build`, `pg_dump` |
| 4. **Scope Guard** | `sec_scope_guard` — P0 driver | Partial runs that hide failures (`--only`, `--tag`, `--scope`) |
| 5. **Kernel Immutability** | SHA256 hashes of critical files | Agents modifying the kernel itself |
| 6. **Agent Laws Integrity** | SHA256 hash of AGENTS.md Laws | Agents altering or removing rules |
| 7. **Knowledge Protocol** | Mandatory handoff inheritance | Agents ignoring context from previous sessions |
| 8. **Repetition → Rule** | Promotes repeated instructions | Recurring instructions staying ad-hoc |
| 9. **A Teia (The Web)** | `pm_omniscience` — universal jurisdiction | Any file escaping governance |
| 10. **Warning Promotion** | `__main__.py` promotes P0/sec WARN→FAIL | Agents dismissing critical warnings |
| + **Re-Signing Blockade** | TTY+API-key detection | Automated agents re-signing security baselines |

### 🔧 Automated Repair with Rollback

The Healer doesn't just report violations — it autonomously fixes them:
1. Extracts `filepath:line` from violation strings
2. Queries the **Knowledge Graph** (docs/external + registry + git log) for candidate fixes
3. Checks the **Negative Registry** (`.steniocheck-negative-registry.json`) to skip previously failed attempts
4. Applies the fix with line-level precision
5. Re-executes the check in real context to verify
6. On pass: `git add + git commit` automatically, adds to permanent registry
7. On fail: reverts, records failure in negative registry, tries next candidate

### 📊 Trend Analysis

The kernel doesn't just report current failures — it identifies patterns across recent runs:
- **Trend detection**: linear regression on violation counts over the last 10 runs
- **Auto-suppress**: suppresses warnings persisting for N consecutive runs (adaptive threshold)
- **Baseline comparison**: `.steniocheck-baseline.json` for noise reduction
- **Flakiness detection**: identifies checks that oscillate between pass/fail
- **Canary promotion**: auto-promotes drivers with >80% pass rate over 5+ runs

### 🧠 Memory & Learning

- **History persistence** (`.steniocheck-history.json`): caches results, tracks file hashes, records durations
- **Continuous learning**: `--learn`, `--learn --interactive`, `--learn-auto` (auto-detects corrections from `git diff`)
- **Registry**: curated bug patterns with `id`, `title`, `pattern`, `fix`, `auto_fix_commands`
- **Proactive suggestions**: `--suggest <fingerprint>` queries registry for known solutions
- **Knowledge Graph**: indexes `docs/external/` (MD3, Tailwind, MWC, FastAPI), registry patterns, and git history for similarity-based correction

### 📚 Documentation as a Product

- **185 documentation files**, **~74,000 lines**
- **DocBot**: auto-downloads READMEs from GitHub/GitLab, archives unused docs, reindexes Knowledge Graph

### 🔄 Resilience

- **Living FMEA**: documented failure nodes with real-time logging and LLM auditing
- **Audio WAL**: Write-Ahead Log with AES-GCM 256 encryption + IndexedDB, 3-layer failure detection, silent network resilience
- **Adaptive circuit breaker** via Valkey for Google Docs, Mercado Pago, OAuth, and Umami
- **Neural Flow**: dual-stage Whisper (sub-500ms draft) + Gemma (refinement) with cross-verification hallucination mitigation
- **Cross-worker handoff**: session state persisted in Valkey with 8h TTL, any worker can restore context

### 🔍 Self-Diagnosis

The kernel audits itself:
- `--blame`: traces every violation to the specific commit, author, and date via `git blame`
- `--self-test`: self-tests validating driver imports, registry format, Knowledge Graph, healer, history cycle
- `--guardian`: self-audit that detects hash drift, registry gaps, suspicious violation drops, canary candidates, performance degradation, timeout anomalies
- `.steniocheck-driver-hashes.json`: cryptographically seals every driver file against unauthorized modification

---

## 🖥️ Infrastructure — Mnemocine Homelab

The **Mnemocine Homelab** is the **Sumænimá** infrastructure. They are indistinguishable — proof of concept running on real hardware with minimal cloud dependency (non-sensitive edge services only).

| Node | Hardware | Role |
|------|----------|------|
| **psicopompo** 🧠 | Dell Frankenstein · Xeon E-2246G 6C/12T · RTX 5050 · 46GB RAM · CachyOS (Arch) | Core — AI Workers, PostgreSQL, Valkey, API. **Sensitive data.** |
| **ybyra** 🌐 | Oracle Cloud · 1GB RAM | Primary edge — nginx, SPA frontend, Umami |
| **ybytu** ☁️ | Oracle Cloud · 1GB RAM | DNS (AdGuard), Homepage dashboard, Syncthing |
| **kuaray** ♻️ | Repurposed Dell laptop · i5-4200U · 6GB RAM · Linux Mint | Standby edge — warm failover + media |

> 🔒 **Data sovereignty**: Oracle nodes (ybyra/ybytu) run **only** non-sensitive edge services. AI inference, storage, and community data are 100% local on psicopompo and kuaray.

- **Tailscale** mesh network as backbone · CGNAT bypass · Public funnels
- **30+ containers** in production · PostgreSQL 16 · Valkey 8 · Nginx
- Monitoring: **Grafana + Loki + Promtail**
- Automated backups: Borg + pg_dump
- Core↔Edge latency: **19–70ms** via Tailscale
- GPU Management: VRAM mutex, circuit breaker, auto-exit after 180s idle

---

## 📊 Ecosystem Scale

| Metric | Value |
|--------|-------|
| Total lines of code | ~8M+ and growing |
| Files | 1,227+ |
| Life project years | 10 |
| Active development | ~2 |
| StênioKernel modules | 22 |
| Check drivers | 132 |
| Anti-bypass layers | 10 |
| Documentation files | 185 |
| Containers in production | 30+ |
| Homelab nodes | 4 |

---

## 👤 Founder

**Carlos Eduardo Rodrigues** · Anthropologist (UnB), founder, PO, and StênioKernel architect.

Nearly a decade combining ethnographic research, technology, and data — with Sumænimá as the thread running through everything he builds. Built the **Tô no Mapa Platform** (integrated with Brazil's Federal Public Ministry) while at ISPN — official data represented only 28% of traditional communities in the Cerrado; the platform was born from ethnography and product discovery to fill that gap. Designed the **StênioKernel** — a proprietary AI Agent Governance Kernel that governs every AI agent on the project through 10 security layers, automated repair, cryptographic integrity, and trend analysis. Experienced firsthand the transformative potential of technology in the socio-environmental space — and also the burnout of using communication in service of others.

His fieldwork at **Fazenda Canadá** (Cavalcante-GO) connected him with **André Aquino** (Lead Environmental Specialist, World Bank) and **Daniel Ferreira** (Itamaraty diplomat), owners of the **Reserva Natural Veredas dos Buritis** — inside the thesis area. He worked with them on the **Participatory Fauna Monitoring Network**. This experience defined his hybrid perspective.

**Thesis:** *"Uma Assemblage de Projetos de Vida"* (UnB, 2023). **Co-author** in Land Use Policy (Elsevier, 2026). **Article** in JOTA — *"Doenças são sintomas de uma crise cultural e ambiental"* (2026). **Mercosur Scientific Journalism Award** winner. Documentary filmmaker ("RUA PARA QUE(M)?"). Architect of the **Mnemocine Homelab** and the **StênioKernel**.

**Master's in Anthropology:** chose to leave in pursuit of data, product design, and systems architecture.

A hybrid by nature — able to translate qualitative research needs into system requirements, and technical architecture into socio-environmental impact. One who builds the governance systems that make AI agents reliable, auditable, and accountable.

---

## 📋 Next Steps

1. Finalize StênioBOT beta for partner institution testing
2. Accelerator program for scale
3. Expand DataVis module with Cerrado and Amazon climate datasets
4. Mobile version for offline-first field collection
5. Marketplace of specialized AI models for qualitative research

---

**Contact:** [ceduardorodrig@gmail.com](mailto:ceduardorodrig@gmail.com) · +55 (61) 9-9803-3546
**Sumænimá:** [sumaenima.chimaera-heptatonic.ts.net](https://sumaenima.chimaera-heptatonic.ts.net)

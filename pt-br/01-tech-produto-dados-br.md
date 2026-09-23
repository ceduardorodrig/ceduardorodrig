---
tags: [meta, docs, personal]
---

# 👤 Carlos Eduardo Rodrigues

**Arquiteto de Dados & Produto** | Antropologia + Engenharia de IA Local

[ceduardorodrig@gmail.com](mailto:ceduardorodrig@gmail.com) | +55 (61) 9-9803-3546 | Brasília-DF

[linkedin.com/in/c-eduardo-rodrigues](https://linkedin.com/in/c-eduardo-rodrigues) | [github.com/ceduardorodrig](https://github.com/ceduardorodrig) | [sumaenima.chimaera-heptatonic.ts.net](https://sumaenima.chimaera-heptatonic.ts.net)

---

## 👤 Perfil

Arquiteto de dados e produto que constrói pontes entre tecnologia open-source e pesquisa qualitativa. Experiência comprovada em projetar pipelines de IA local (Whisper, LLMs, GroundingDINO, SAM 2), orquestrar clusters Docker Swarm multi-nó e gerenciar produtos de dados completos, do conceito à entrega. Uso engenhoso de hardware reaproveitado e software livre para entregar soluções de IA privadas, offline e economicamente viáveis — sem depender de infraestrutura de big tech. Projetou o StênioKernel — um Kernel proprietário de Governança para Agentes de IA (21.435 linhas, 132 drivers, 10 camadas anti-bypass) que governa o comportamento de agentes por meio de integridade criptográfica, correção automatizada com rollback e análise de tendências. Formação em Antropologia pela UnB como base para design de produto centrado em humanos.

---

## 💼 Experiência

### 🚀 Sumænimá — Fundador & Product Owner
*2016 — presente · Brasília-DF / Remoto*

Sumænimá é meu projeto de vida. Existe há quase 10 anos como entidade criativa independente, atravessando toda minha carreira em paralelo aos empregos formais. O que me mantém é o sonho de um dia captar recursos para ter equipe e construir um **Bureau de Dados** com alma antropológica.

**Sumænimá Hub v3.1.0** (2024–presente): Plataforma de inteligência e captura de dados local-first de nível corporativo, com backend 100% nativo em Rust (`stenio-server` Axum 0.8 / Tokio / SQLx) e frontend React 19 / TypeScript 6 acelerado por DSP em Rust WebAssembly (`AudioWorklet`) no navegador. Três pilares operacionais:

- **Bureau Sumænimá (StênioREC & Biblioteca):** Cockpit de transcrição em tempo real (whisper.cpp com aceleração nativa CUDA 13 na NVIDIA RTX 5050 sm_120, Gemma 3 IT, Anti-Loop Shield, Local Agreement, drenagem contínua para Google Docs) e CMS institucional em Markdown (TipTap, tags dinâmicas, controle de rascunhos) — **em produção**, validado em relatorias institucionais de alto escalão
- **Arandu TCG Platform:** Plataforma de análise atômica de cartas e trocas sociais para Magic: The Gathering com heurísticas sub-milissegundo (`arandu-engine` em Rust), pasta 3x3 virtual, wishlist, radar de trocas P2P e PostgreSQL 16 + pgvector — **em produção**
- **Asciline Engine:** Streamer procedural ASCII em tempo real transmitindo animações e fractais matemáticos via Axum WebSockets com zero overhead de CPU — **em produção**

Ganhos arquiteturais (v3.0 / 100% Rust): Eliminação completa de runtimes dinâmicos em Python/FastAPI, memória em repouso reduzida de ~2.5 GB para **~25–35 MB**, imagem Docker reduzida de ~20 GB para **~500 MB**, cold start acelerado de ~20s para **<100ms** e concorrência multithread real com Tokio work-stealing.

**StenioSentinel v3.1.0 — Sentinela de Governança Estática & Anti-Bypass:**
- Sentinela de auditoria estática ultrarrápida e integridade arquitetural escrito em **Rust 2024** puro, auditando o ecossistema completo em sub-milissegundos (<1ms a <500ms)
- Arquitetura anti-bypass em 10 camadas: Quality gates pre-commit (Regra 0), bypass guard, scope guard, imutabilidade do motor, leis de agentes assinadas criptograficamente, promoção repetição→regra, jurisdição universal de arquivos, rollback com negative registry e autocorreção (`--fix`)
- Escala do ecossistema: **~8M+ linhas** de código com curadoria, documentação e assets multimodais governados por regras determinísticas em 5 nós do homelab

**Relatoria & Sistematização de Dados** (paralelo à StênioBOT):
- Consultor independente em relatoria, sistematização de dados e planejamento estratégico
- Relatoria da **Semana da Sociobiodiversidade (2025)** — **3º Encontro Nacional da Juventude das Populações Extrativistas e Tradicionais** (IEB/CNS/MCM/CONFREM). Realizada com **Stênio v1** — primeira versão operacional da plataforma em produção
- Relatoria do **Módulo II — "Formar Protagonistas"** (IEB/APAFE/Rainforest Trust): imersão de 39 lideranças da FLONA de Tefé em Brasília
- **Encontro de Planejamento Estratégico do IPEA** (2026) — relatoria dos Movimentos 5 (Integração, comunidade e colaboração) e 7 (Gestão da Informação) com transcrição em tempo real via StênioREC e observação etnográfica. Evento de 3 dias no ParlaMundi da LBV e sede do IPEA, contratado via **Imagine Gestão Social**, resultando na agenda estratégica 2026–2027 do instituto
- **CNPCT (Conselho Nacional dos Povos e Comunidades Tradicionais):** Acompanhamento e relatoria das reuniões desde 2025, incluindo a 22ª Reunião Ordinária (mar/2026) com devolutiva do Decreto de Regularização Fundiária no Palácio do Planalto e fala de abertura da Ministra Marina Silva — transcrição em tempo real via StênioREC
- **III Encontro do Coletivo da Castanha (OCA)** (mai/2026) — Relatoria com transcrição em tempo real via StênioREC. Evento do IEB sobre fortalecimento da cadeia da castanha e mobilização de comunidades extrativistas na Amazônia

### 🗺️ ISPN — Instituto Sociedade, População e Natureza
*2017 — 2021 · Brasília-DF*

**Assessor Técnico Júnior** (2019–2021) · **Estagiário** (2017–2019)

- **Tô no Mapa**: Dados oficiais do governo representavam apenas 28% das comunidades tradicionais no Cerrado — uma lacuna crítica que as tornava "invisíveis". Participei da pesquisa etnográfica em campo e da fase de discovery do produto, ajudando a definir o problema central e as necessidades dos usuários. O resultado foi a **Plataforma Tô no Mapa** — um aplicativo de automapeamento que hoje está integrada ao **Ministério Público Federal**, empoderando milhares de comunidades tradicionais a gerar seus próprios dados e se colocar no mapa
- Criei a primeira estratégia de comunicação pública do Instituto em anos
- Produzi mapas (QGIS), relatórios e cobertura fotográfica em expedições de campo
- Apoio técnico a eventos socioambientais de grande porte: Acampamento Terra Livre, Encontro e Feira dos Povos do Cerrado, Congresso Latino-Americano de Agroecologia

### 🦎 Rede de Monitoria Participativa da Fauna
*2020 — 2022 · Cavalcante-GO*

**Stakeholder Facilitator**

Trabalhei diretamente com **André Rodrigues de Aquino** (Lead Environmental Specialist do World Bank, então gerente sênior de recursos naturais) e **Daniel Ferreira** (diplomata do Itamaraty), proprietários da **Reserva Natural Veredas dos Buritis** — que fica **dentro** da Fazenda Canadá, área do meu TCC. Apoiei a facilitação da reunião inaugural da Rede de Monitoria, que buscava criar um corredor ecológico entre o Parque Nacional da Chapada dos Veadeiros e o Sítio Histórico Kalunga, reunindo ICMBio, UnB, ONGs e proprietários rurais. Produzi relatório executivo completo (concepção, redação, fotografia, diagramação).

### 🌳 IPAM — Instituto de Pesquisa Ambiental da Amazônia
*2022 — 2025 · Brasília-DF*

**Líder de Produto Digital** (2024–2025) · **Assistente de Comunicação** (2023–2024) · **Estagiário** (2022–2023)

**Case: Scaling Digital Engagement — +143% de crescimento em comunicação científica climática**

Tratei os canais sociais do IPAM como produtos digitais: segmentei audiências (Instagram: público jovem; Facebook: audiência consolidada), testei formatos como features (infográficos, storytelling visual, posts interativos) e integrei campanhas orgânicas e pagas.

**📈 Resultados:**
- **+143,3%** de seguidores no Facebook, **+100%** no Instagram
- **2+ milhões** de alcance consolidado (1,6M nos canais principais)
- **66,7K** interações no Instagram — canal validado como principal para engajamento de alto valor

Outras entregas:
- Implementei Agile/Scrum como Scrum Master, estruturando sprints e métricas de entrega
- Gerenciei Google Ad Grants (US$ 10K/mês) e Meta Ads com segmentação e otimização contínua
- Codiretor do documentário **"Manaus Extrema"** — publicado pelo IPAM. Estreia no INPA / PROTEJA Talks 2024
- Apoio à organização e comunicação institucional do **evento do SOMUC na UFAC** (2024), sobre monitoramento de Unidades de Conservação na Amazônia, com participação de servidores do ICMBio e pesquisadores
- **Prêmio Mercosul de Jornalismo e Divulgação Científica — 1º lugar, categoria Redes Sociais** (2024)
- Presidi a CIPA por dois mandatos

---

## 🎓 Formação

**Universidade de Brasília (UnB)** — Bacharelado em Ciências Sociais / Antropologia (2016–2023)

- **Monografia:** *"Uma Assemblage de Projetos de Vida: mudanças organizacionais na Fazenda Canadá, Cavalcante-GO"* (2023). Orientação: Prof. Henyo Trindade Barretto Filho. Etnografia sobre o fracionamento de terras, memória e projetos de vida na Chapada dos Veadeiros. A pesquisa de campo foi realizada na mesma região onde ficam a Reserva Veredas dos Buritis e a Rede de Monitoria — tudo interligado.

**Mestrado em Antropologia** — Universidade de Brasília (2024–2025)
Dois semestres concluídos. Escolhi sair do mestrado para me dedicar integralmente a dados, design de produto e arquitetura de sistemas. Esta decisão definiu minha transição de carreira.

---

## 📡 Infraestrutura — Sumænimá & Mnemocine

O **Homelab Mnemocine** é a infraestrutura da **Sumænimá**. São indistinguíveis — um cluster multi-nó orquestrado via Docker Swarm que provê serviços de IA, banco, cache, DNS, monitoramento e borda web.

| Nó | Hardware | Papel |
|----|----------|-------|
| **psicopompo** 🧠 | Dell Frankenstein · Xeon E-2246G 6C/12T · RTX 5050 · 46GB RAM · CachyOS (Arch) | Core — IA, banco, Swarm manager. **Dados sensíveis ficam aqui.** |
| **ybyra** 🌐 | Oracle Cloud · 1GB RAM | Edge primário — nginx, SPA front-end, Umami analytics |
| **ybytu** ☁️ | Oracle Cloud · 1GB RAM | DNS (AdGuard), dashboard Homepage, sincronização Syncthing |
| **kuaray** ♻️ | Dell notebook reaproveitado · i5-4200U · 6GB RAM · Linux Mint | Edge standby — failover warm + multimídia |

> 🔒 **Soberania de dados**: os nós Oracle (ybyra/ybytu) rodam **apenas** serviços de borda não-sensíveis (nginx, DNS, analytics). Processamento de dados, inferência de IA e armazenamento são 100% locais em psicopompo e kuaray. Dados de comunidades nunca saem do seu controle.

- Rede mesh **Tailscale** como backbone (bypass de CGNAT, funnels públicos)
- **30+ containers** em produção (PostgreSQL, Valkey, nginx, AdGuard, Home Assistant, *arr stack)
- Monitoramento com **Grafana + Loki + Promtail**, backups Borg + pg_dump
- Desktop principal: Arch Linux (CachyOS) — daily driver

---

## 📚 Publicações

- **Coautor** — Moser, P.; de Castro Silva, I.; Benedetti Figueiredo, I.; Favilla, K.; Bustamante, M.; Macedo, M.N.; de Araújo, R.F.; Shimbo, J.Z.; Varela, V.; **Rodrigues, C.E.**; Alencar, A.A. *"Institutional Invisibility Threatens the Lands and Livelihoods of Traditional Communities in the Northern Brazilian Cerrado"* — Submetido a **Land Use Policy** (Elsevier, 2026). A pesquisa de campo que fundamenta o artigo foi realizada durante minha graduação em Antropologia na UnB.
- **Artigo** — Rodrigues, C.E. *"Doenças são sintomas de uma crise cultural e ambiental"* — JOTA, Em Clima de Justiça (2026). [Ler](https://www.jota.info/opiniao-e-analise/colunas/em-clima-de-justica/doencas-sao-sintomas-de-uma-crise-cultural-e-ambiental)
- **Documentário** — *RUA PARA QUE(M)?* (85min, 2020) — Direção, fotografia, edição. Etnografia visual do movimento neo-fanfarrista de Brasília. Publicado pela Sumænimá.
- **Documentário** — *Manaus Extrema* (2024) — Codireção. Mudanças climáticas na Amazônia urbana. Publicado pelo IPAM. Estreia no INPA / PROTEJA Talks 2024.

---

## 🛠️ Habilidades

| Categoria | Tecnologias |
|-----------|-------------|
| **Backend** | Rust (Axum 0.8, Tokio, SQLx, whisper.cpp), Python, WebSockets, REST APIs |
| **Front-end** | React 19, TypeScript, Rust WebAssembly (AudioWorklet DSP), Vite, Tailwind |
| **Banco de Dados** | PostgreSQL 16 (pgvector), migrações SQLx, Valkey 8 / Redis, modelagem |
| **Infraestrutura** | Docker Swarm, Nginx, Malha Tailscale WireGuard, CachyOS (Arch Linux), Ubuntu 24.04 LTS |
| **AI/ML & DSP** | Whisper CUDA 13 (sm_120 / RTX 5050), Gemma 3 IT, DSP de áudio WebAssembly no cliente, embeddings |
| **Governança & QA** | StenioSentinel v3.1.0 (motor de auditoria estática em Rust 2024), ADRs, Regra 0 anti-bypass |
| **Observabilidade** | Prometheus, Grafana, Loki, Promtail, Alertmanager, ntfy |
| **Métodos** | Agile/Scrum (Scrum Master), pesquisa etnográfica, UX Research, OKRs |
| **Ferramentas** | Git, Cargo, Suite moderna de CLI em Rust (rg, fd, eza, bat, delta), QGIS |

---

## 🌐 Idiomas

- **Português** — Nativo
- **Inglês** — Fluente (leitura, escrita, conversação técnica e acadêmica)

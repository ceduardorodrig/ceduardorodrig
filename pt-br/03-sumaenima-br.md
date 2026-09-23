---
tags: [meta, docs, personal]
---

# 🚀 Sumænimá Hub v3.1.0

**Plataforma de Inteligência e Captura de Dados Local-First & Etnográfica**

[sumaenima.chimaera-heptatonic.ts.net](https://sumaenima.chimaera-heptatonic.ts.net) | [github.com/ceduardorodrig](https://github.com/ceduardorodrig)

---

## 🎯 Visão Geral

**Fundador & Product Owner:** Carlos Eduardo Rodrigues

Sumænimá é meu projeto de vida. Existe há quase 10 anos como entidade criativa independente, atravessando toda minha carreira em paralelo aos empregos formais. Nasceu de uma convicção: pesquisa qualitativa — especialmente com comunidades tradicionais, indígenas e grupos vulneráveis — não deveria depender de infraestrutura de big tech para processar dados sensíveis. O que começou como uma prática de pesquisa independente amadureceu no **Sumænimá Hub v3.1.0**: um monorepo unificado com backend 100% nativo em Rust (`stenio-server` Axum 0.8 / Tokio / SQLx) integrado a um frontend React 19 acelerado por processamento DSP em Rust WebAssembly no navegador.

A missão central é operar um **Bureau de Dados** com alma antropológica: uma estrutura institucional que produza projetos como o *Tô no Mapa*, bases territoriais e pesquisa etnográfica em escala — unindo ciência, território e engenharia de software de forma determinística e privada.

A fundação do ecossistema é o **StenioSentinel v3.1.0** — nosso sentinela open-source de governança para agentes de IA escrito em **Rust 2024** puro (agora público em `ceduardorodrig/STENIO-SENTINEL`). Ele fiscaliza regras arquiteturais em sub-milissegundos (<1ms a <500ms), aplica correções cirúrgicas automatizadas e garante que agentes de código adiram a quality gates determinísticos (Regra 0).

Ao todo, o ecossistema Sumænimá soma **~8M+ linhas e crescendo** (inclui código fonte, documentação e assets multimodais) — distribuídas em 1.227+ arquivos estritamente governados em nossa infraestrutura de 5 nós do homelab.

---

## 🖥️ Design & Experiência

A interface do Sumænimá Hub segue **Material Design 3** com glassmorfismo, tipografia Lexend e tema dinâmico — responsiva em todos os dispositivos.

| Mobile · iPhone SE | Tablet · iPad Pro | Desktop |
|:---:|:---:|:---:|
| <img src="../assets/hub-mobile.png" width="220" alt="Mobile" /> | <img src="../assets/hub-tablet.png" width="280" alt="Tablet" /> | <img src="../assets/hub-desktop.png" width="400" alt="Desktop" /> |

---

## ❓ O Problema

Pesquisadores, ONGs e instituições que trabalham com dados sensíveis enfrentam um dilema:
- Serviços cloud (Google, OpenAI, AWS) são caros e exigem envio de áudios e transcrições confidenciais para servidores estrangeiros
- Alternativas locais são fragmentadas, mal documentadas e exigem conhecimento técnico profundo
- LGPD, GDPR e comitês de ética restringem cada vez mais o uso de soluções cloud para dados de deliberação institucional e comunitária

O Sumænimá Hub soluciona esse impasse oferecendo uma plataforma soberana integrada — local, privada e determinística.

---

## 💡 A Solução — Sumænimá Hub v3.1.0

### 🏛️ Bureau Sumænimá

#### 🎙️ StênioREC — Cockpit de Transcrição & Relatoria
**Status:** 🟢 **Em produção** — Validado em instâncias máximas de governo e relatorias de campo

<p align="center">
  <img src="../assets/hub-rec.png" width="600" alt="StênioREC — Cockpit de Transcrição" />
</p>

Cockpit de transcrição em tempo real com inferência 100% local. Captura áudio via `AudioWorklet` no navegador com detecção acústica RMS (VAD) em Rust WebAssembly, transcreve com whisper.cpp acelerado nativamente por CUDA 13 na NVIDIA RTX 5050 (Blackwell sm_120) e purifica com Gemma 3 IT em pipeline neural paralelo — 100% processamento local; transcrições sincronizadas sob demanda via Google Docs com autenticação OAuth por usuário.

**✨ Destaques:**
- 🧠 Pipeline Neural Flow dual-stage: Whisper draft sub-500ms + Gemma 3 purificação paralela
- 🔒 Buffer offline de ~2h (57MB RAM + 171MB IndexedDB), projetado para evitar perda de áudio sem rede
- 📝 Criação automática de Google Doc por usuário com credenciais próprias
- 🎛️ Cockpit em tempo real: GPU temp, VRAM, drift, entropia, status da rede
- 📱 Wake Lock API — gravação não suspende no celular
- ⚡ Descarrega VRAM automaticamente ao destravar contexto

**🎯 Para:** Relatoria etnográfica, entrevistas qualitativas, audiências públicas, atas corporativas.

### 🗂️ StênioPANEL — Scanner de Workshops
**Status:** 🔴 Concepção — arquitetura definida, código implementado, aguardando recursos

<p align="center">
  <img src="../assets/hub-panel.png" width="600" alt="StênioPANEL — Scanner de Post-Its" />
</p>

Transforma fotos de painéis físicos (post-its, whiteboards, cartolinas) em arquivos `.canvas` nativos do Obsidian — com visão computacional 100% local. Pipeline de 4 estágios: detecção zero-shot (GroundingDINO + SAM 2), OCR duplo com fallback automático (PaddleOCR 93.5% / EasyOCR 89.2%), organizador por DBSCAN + arestas, e validador do spec oficial do Obsidian Canvas.

**✨ Destaques:**
- 🎯 Detecção zero-shot: não precisa de fine-tuning para nenhum evento
- 🔍 OCR duplo com fallback automático entre PaddleOCR e EasyOCR
- 🧩 Gera arquivos `.canvas` 100% compatíveis com Obsidian
- 📸 Processa fotos de até 50MP com algoritmo de tiling
- 🧠 Revisão semântica opcional com Gemma 3
- 🔄 VRAM Mutex: prioriza GPU com StênioREC; fila inteligente no Valkey se GPU ocupada
- 🗑️ Imagens destruídas após processamento — só metadados persistem

**🎯 Para:** Facilitadores de workshops, design thinking, agile coaches, etnógrafos.

### 🔍 StênioDIVE — Mineração Semântica
**Status:** 🔴 Concepção — arquitetura definida, motor de busca implementado, aguardando recursos

<p align="center">
  <img src="../assets/hub-dive.png" width="600" alt="StênioDIVE — Grafo de Conhecimento" />
</p>

Mecanismo de busca semântica unificada que minera transcrições do REC, boards do PANEL, notas do Obsidian e imagens públicas em um único grafo interativo. Combina busca lexical BM25 com similaridade vetorial via embeddings ONNX 384-d (CPU, sem GPU necessária), fusionados por Reciprocal Rank Fusion (RRF).

**✨ Destaques:**
- 🔎 Busca híbrida BM25 + cosseno vetorial com fusão RRF
- 📄 Indexa 4 fontes simultâneas: Google Docs, Canvas Boards, Obsidian, imagens
- 🧠 Embeddings ONNX 384-d 100% CPU, sem dependência de GPU
- ⚙️ Pipeline assíncrono com cache SHA-256 e cache OCR
- 🎛️ Filtros por fonte: transcrições, painéis, notas
- 🔗 Grafo interativo de wikilinks, tags e conexões semânticas

**🎯 Para:** Pesquisadores, analistas, gestores de conhecimento.

### 🌡️ DataVis — Visualizações Climáticas
**Status:** 🔴 Concepção — visualização PM2.5 instável; demais módulos em estágio inicial

<p align="center">
  <img src="../assets/hub-datavis.png" width="600" alt="DataVis — Partículas PM2.5" />
</p>

Visualizações climáticas generativas em tempo real. Partículas reagem a dados reais de qualidade do ar (PM2.5), vento e direção — transformando números em arte interativa. Partículas mudam de cor conforme severidade (âmbar → vermelho fuligem), turbulência acompanha vento real, e o mouse cria campos de força no canvas.

**✨ Destaques:**
- 🎨 Canvas generativo com até 300 partículas reagindo a dados reais
- 🌬️ Vento e direção reais integrados: turbulência proporcional à velocidade
- 🖱️ Partículas interagem com o mouse (campo de força 120px)
- 🏥 Classificação OMS em 5 níveis com gauge dinâmico
- 🔄 Duas fontes de dados: WAQI e OpenAQ (alternável)
- ⚡ Cache adaptativo: 30s a 15min conforme popularidade
- 🧊 Arquitetura de microsserviço — roda no nó edge ybyra (Oracle, 1GB RAM)

**🎯 Para:** Pesquisadores ambientais, ativistas climáticos, data journalists, público geral.

### ⚙️ Admin — Gestão da Plataforma
**Status:** 🟡 Parcial — dashboard, auth e contatos OK; ERP básico; image library e CMS em desenvolvimento

<p align="center">
  <img src="../assets/hub-admin.png" width="600" alt="Admin — Painel Administrativo" />
</p>

Painel central de administração da plataforma: métricas, usuários, contatos, imagens e ERP completo (organizações, leads, contratos, faturas, projetos). Navegação em 5 abas com Material Design 3, glassmorfismo e compliance LGPD.

**✨ Destaques:**
- 📊 Dashboard com 7 métricas ao vivo: usuários, sessões WS, projetos, receita, caracteres, áudio, tokens
- 🗂️ ERP completo: organizações, Kanban de leads, contratos, faturas, projetos com board de tarefas
- 👤 Gestão de usuários com badge de admin protegido por env var (único owner)
- 🔒 Compliance LGPD: masking de email, IP em audit logs, banner de consentimento, versão de termos
- 📈 Umami Analytics embutido com CSP dinâmico
- 🖼️ Biblioteca de imagens e CMS com editor TipTap WYSIWYG
- 📬 CRUD de contatos com 3 estados: não lido, lido, arquivado
- 🛡️ Rota protegida — apenas o owner configurado por env var acessa o admin

**🎯 Para:** Administrador da plataforma, operador do sistema, gestor de negócio.

### Funcionalidades Transversais

- SaaS com assinaturas via Mercado Pago, Google OAuth com tokens criptografados
- CMS com editor TipTap WYSIWYG e biblioteca de imagens
- ERP: organizações, membros, leads, contratos, faturas, projetos
- Observabilidade: Grafana + Loki + Promtail

---

## ⚙️ Stack Tecnológica

| Camada | Tecnologia |
|--------|-----------|
| **Backend** | 100% Rust (`stenio-server`) · Axum 0.8 · Tokio Work-Stealing · SQLx · whisper.cpp |
| **Front-end** | React 19 · Vite · TypeScript 6 · Rust WebAssembly (AudioWorklet DSP) · Tailwind |
| **Banco** | PostgreSQL 16 (pgvector) · SQLx (consultas checadas em compilação & migrações) |
| **Cache/Estado** | Valkey 8 (estado em memória, pub/sub, filas em tempo real) |
| **AI Áudio** | whisper.cpp CUDA 13 (NVIDIA RTX 5050 sm_120) · Gemma 3 IT |
| **Infra** | Docker Swarm (kavure manager, psicopompo worker) · Malha Tailscale WireGuard |
| **Rede** | Gateway Tailscale Funnel (`ybyra`) · Proxy reverso Nginx |
| **Observabilidade** | Prometheus · Grafana · Loki · Promtail · Alertmanager · ntfy |
| **Governança** | StenioSentinel v3.1.0 (motor de auditoria estática em Rust 2024, execução sub-milissegundo) |
| **Ecossistema** | **~8M+ linhas e crescendo** · 1.227+ arquivos · 10 anos (projeto) · ~2.5 anos (ativo) |

---

## 🛡️ StenioSentinel v3.1.0 — Sentinela de Governança Estática

Esta é a fundação de engenharia mais profunda da Sumænimá. O StenioSentinel é um sentinela open-source de análise estática e governança arquitetural escrito em **Rust 2024** puro (`ceduardorodrig/STENIO-SENTINEL`). Foi concebido para governar o pareamento humano-IA e agentes de código em todo o ciclo de vida do software: código, documentação, infraestrutura e o próprio comportamento dos agentes.

- **Arquitetura 100% Rust 2024:** Auditoria estática em sub-milissegundos (<1ms a <500ms) aproveitando paralelismo via Rayon.
- **Regra 0 & Quality Gate:** Verificação pré-commit obrigatória e inegociável. Tolerância zero para código não auditado ou tentativas de bypass (`// @ts-ignore`, `.unwrap()` em Rust de produção).
- **Escopos Setorizados:** Auditoria granular para `hub` (backend Rust, frontend React 19), `homelab` (infraestrutura, systemd, mounts) e `vault` (tags e links Obsidian).
- **Autocorreção Cirúrgica (`--fix`):** Correções automatizadas linha a linha com rollback preventivo contra regressões.

### 🛡️ Arquitetura Anti-Bypass (10 Camadas)

| Camada | Mecanismo | O Que Impede |
|--------|-----------|--------------|
| 1. **Pre-Commit Hooks** | `pre-commit-config.yaml` — gate P0+sec+doc | Commit sem checagens estáticas |
| 2. **Bypass Guard** | `sec_ai_bypass_guard` — driver P0 | `--no-verify`, `\|\| true`, `2>/dev/null`, CI `continue-on-error` |
| 3. **No-Bypass Ops** | `sec_no_bypass` — driver P0 | `rsync+ssh` manual, `docker compose`, `npm run build`, `pg_dump` |
| 4. **Scope Guard** | `sec_scope_guard` — driver P0 | Runs parciais que escondem falhas (`--only`, `--tag`, `--scope`) |
| 5. **Imutabilidade do Kernel** | Hashes SHA256 de arquivos críticos | Agentes modificando o próprio kernel |
| 6. **Integridade das Leis** | Hash SHA256 das Leis do AGENTS.md | Agentes alterando ou removendo regras |
| 7. **Protocolo de Conhecimento** | Herança de handoff obrigatória | Agentes ignorando contexto de sessões anteriores |
| 8. **Repetição → Regra** | Promove instruções repetidas | Instruções recorrentes ficando ad-hoc |
| 9. **A Teia** | `pm_omniscience` — jurisdição universal | Qualquer arquivo escapando da governança |
| 10. **Promoção de Warnings** | `__main__.py` promove P0/sec WARN→FAIL | Agentes ignorando warnings críticos |
| + **Bloqueio de Reassinatura** | Detecção de TTY + chaves de API | Agentes reassinando baselines de segurança |

### 🔧 Correção Automatizada com Rollback

O Healer não apenas reporta violações — ele as corrige autonomamente:
1. Extrai `arquivo:linha` das strings de violação
2. Consulta o **Knowledge Graph** (docs/external + registry + git log) por correções candidatas
3. Verifica o **Negative Registry** (`.steniocheck-negative-registry.json`) para pular tentativas já falhas
4. Aplica a correção com precisão de linha
5. Re-executa o check no contexto real para verificar
6. Se passar: `git add + git commit` automático, adiciona ao registry permanente
7. Se falhar: reverte, registra falha no negative registry, tenta próximo candidato

### 📊 Análise de Tendências

O kernel não apenas reporta falhas atuais — ele identifica padrões nas execuções recentes:
- **Detecção de tendências**: regressão linear sobre contagens de violações nas últimas 10 execuções
- **Auto-suppress**: suprime warnings persistentes por N execuções consecutivas (limiar adaptativo)
- **Comparação com baseline**: `.steniocheck-baseline.json` para redução de ruído
- **Detecção de flakiness**: identifica checks que oscilam entre pass/fail
- **Promoção de canary**: promove automaticamente drivers com >80% de aprovação em 5+ execuções

### 🧠 Memória e Aprendizado

- **Persistência de histórico** (`.steniocheck-history.json`): armazena resultados em cache, rastreia hashes de arquivos, registra durações
- **Aprendizado contínuo**: `--learn`, `--learn --interactive`, `--learn-auto` (detecta correções do `git diff`)
- **Registry**: padrões de bug curados com `id`, `title`, `pattern`, `fix`, `auto_fix_commands`
- **Sugestões proativas**: `--suggest <fingerprint>` consulta o registry por soluções conhecidas
- **Knowledge Graph**: indexa `docs/external/` (MD3, Tailwind, MWC, FastAPI), padrões do registry e histórico git para correção por similaridade

### 📚 Documentação como Produto

- **185 arquivos** de documentação, **~74.000 linhas**
- **DocBot**: baixa automaticamente READMEs do GitHub/GitLab, arquiva docs não utilizadas, reindexa o Knowledge Graph

### 🔄 Resiliência

- **FMEA vivo**: nós de falha documentados com logging em tempo real e auditoria via LLM
- **Audio WAL**: Write-Ahead Log com criptografia AES-GCM 256 + IndexedDB, detecção de falha em 3 camadas, resiliência silenciosa a quedas de rede
- **Circuit breaker adaptativo** via Valkey para Google Docs, Mercado Pago, OAuth e Umami
- **Neural Flow**: pipeline dual-stage Whisper (draft sub-500ms) + Gemma (refinamento) com mitigação de alucinações via verificação cruzada
- **Cross-worker handoff**: sessão persistida em Valkey com TTL de 8h, qualquer worker pode retomar contexto

### 🔍 Autodiagnóstico

O kernel audita a si mesmo:
- `--blame`: rastreia cada violação até o commit, autor e data específicos via `git blame`
- `--self-test`: auto-testes validando imports dos drivers, formato do registry, Knowledge Graph, healer, ciclo de histórico
- `--guardian`: auto-auditoria que detecta desvio de hash, gaps no registry, quedas suspeitas de violações, candidatos canary, degradação de performance, anomalias de timeout
- `.steniocheck-driver-hashes.json`: sela criptograficamente cada arquivo de driver contra modificação não autorizada

---

## 🖥️ Infraestrutura — Homelab Mnemocine

O **Homelab Mnemocine** é a infraestrutura da **Sumænimá**. São indistinguíveis — prova de conceito rodando em hardware real, com dependência mínima de nuvem (serviços de borda não-sensíveis apenas).

| Nó | Hardware | Função |
|----|----------|--------|
| **psicopompo** 🧠 | Dell Frankenstein · Xeon E-2246G 6C/12T · RTX 5050 · 46GB RAM · CachyOS (Arch) | Core — Workers IA, PostgreSQL, Valkey, API. **Dados sensíveis.** |
| **ybyra** 🌐 | Oracle Cloud · 1GB RAM | Edge primário — nginx, SPA front-end, Umami |
| **ybytu** ☁️ | Oracle Cloud · 1GB RAM | DNS (AdGuard), dashboard (Homepage), Syncthing |
| **kuaray** ♻️ | Dell notebook reaproveitado · i5-4200U · 6GB RAM · Linux Mint | Edge standby — failover warm + multimídia |

> 🔒 **Soberania de dados**: nós Oracle (ybyra/ybytu) rodam **apenas** serviços de borda não-sensíveis. Inferência de IA, armazenamento e dados de comunidades são 100% locais em psicopompo e kuaray.

- Rede mesh **Tailscale** como backbone · CGNAT bypass · Funnels públicos
- **30+ containers** em produção · PostgreSQL 16 · Valkey 8 · Nginx
- Monitoramento: **Grafana + Loki + Promtail**
- Backup automatizado: Borg + pg_dump
- Latência Core↔Edge: **19–70ms** via Tailscale
- GPU Management: VRAM mutex, circuit breaker, auto-exit após 180s idle

---

## 📊 Escala do Ecossistema

| Métrica | Valor |
|---------|-------|
| Linhas de código totais | ~8M+ e crescendo |
| Arquivos | 1.227+ |
| Anos como projeto de vida | 10 |
| Desenvolvimento ativo | ~2 |
| Módulos do StênioKernel | 22 |
| Drivers de verificação | 132 |
| Camadas anti-bypass | 10 |
| Arquivos de documentação | 185 |
| Containers em produção | 30+ |
| Nós no Homelab | 4 |

---

## 👤 Fundador

**Carlos Eduardo Rodrigues** · Antropólogo (UnB), founder, PO e arquiteto do StênioKernel.

Há quase 10 anos combinando pesquisa etnográfica, tecnologia e dados — com a Sumænimá como fio condutor. Construiu a **Plataforma Tô no Mapa** (integrada ao MPF) enquanto estava no ISPN — dados oficiais representavam apenas 28% das comunidades tradicionais no Cerrado; a plataforma nasceu da etnografia e do discovery de produto para preencher essa lacuna. Projetou o **StênioKernel** — um Kernel proprietário de Governança para Agentes de IA que governa todos os agentes de IA do projeto com 10 camadas de segurança, correção automatizada, integridade criptográfica e análise de tendências. Viveu na pele o potencial transformador da tecnologia no socioambiental — e também o burnout de usar comunicação a serviço de terceiros.

Sua pesquisa de campo na **Fazenda Canadá** (Cavalcante-GO) o conectou com **André Aquino** (Lead Environmental Specialist, World Bank) e **Daniel Ferreira** (diplomata, Itamaraty), proprietários da **Reserva Natural Veredas dos Buritis** — dentro da área do seu TCC. Trabalhou com eles na **Rede de Monitoria Participativa da Fauna**. Essa experiência definiu seu olhar híbrido.

**Monografia:** *"Uma Assemblage de Projetos de Vida"* (UnB, 2023). **Coautor** em Land Use Policy (Elsevier, 2026). **Artigo** no JOTA — *"Doenças são sintomas de uma crise cultural e ambiental"* (2026). **Prêmio Mercosul** de Jornalismo Científico. Documentarista ("RUA PARA QUE(M)?"). Arquiteto do **Homelab Mnemocine** e do **StênioKernel**.

**Mestrado em Antropologia:** optou por sair para se dedicar a dados, design de produto e arquitetura de sistemas.

Híbrido por natureza — capaz de traduzir necessidades de pesquisa qualitativa em requisitos de sistema, e arquitetura técnica em impacto socioambiental. Alguém que constrói os sistemas de governança que tornam agentes de IA confiáveis, auditáveis e responsáveis.

---

## 📋 Próximos Passos

1. Finalizar beta da StênioBOT para testes com instituições parceiras
2. Programa de aceleração para escala
3. Expansão do módulo DataVis com datasets climáticos do Cerrado e Amazônia
4. Versão mobile para coleta em campo offline-first
5. Marketplace de modelos de IA especializados para pesquisa qualitativa

---

**Contato:** [ceduardorodrig@gmail.com](mailto:ceduardorodrig@gmail.com) · +55 (61) 9-9803-3546
**Sumænimá:** [sumaenima.chimaera-heptatonic.ts.net](https://sumaenima.chimaera-heptatonic.ts.net)

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0a0a0f,50:0044cc,100:00aaff&height=200&section=header&text=Mohomed%20Akeel&fontSize=52&fontColor=ffffff&fontAlignY=40&desc=Applied%20AI%20Engineer%20%7C%20LLM%20Systems%20%7C%20RAG%20Pipelines%20%7C%20Agentic%20AI&descSize=16&descAlignY=62&animation=fadeIn" width="100%"/>

<a href="https://git.io/typing-svg">
  <img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=20&duration=3000&pause=1000&color=0099FF&center=true&vCenter=true&repeat=true&width=620&height=45&lines=AI+Engineer;LLM+Systems+Builder;RAG+Pipeline+Architect;Data+Intelligence+Engineer;Based+in+Colombo%2C+thinking+globally." alt="Typing SVG" />
</a>

<br/>

<img src="https://img.shields.io/badge/Location-Colombo%2C%20Sri%20Lanka-0044cc?style=for-the-badge&logo=googlemaps&logoColor=white"/>
<img src="https://img.shields.io/badge/Role-Applied%20AI%20Engineer-0077ff?style=for-the-badge&logo=openai&logoColor=white"/>
<img src="https://img.shields.io/badge/Status-Building%20in%20Production-00cc77?style=for-the-badge&logo=vercel&logoColor=white"/>

</div>

---

I build AI systems that solve real operational problems — combining software engineering, retrieval architectures, and thoughtful evaluation. My focus is on systems that remain reliable long after the prototype stage: hardened backends, measurable retrieval quality, and agents that fail gracefully rather than silently.

---

## `> whoami`

```python
class Engineer:
    name         = "Mohomed Akeel"
    handle       = "AakilMoh"
    location     = "Colombo, Sri Lanka 🇱🇰"
    current      = "Applied AI & LLMs Engineer @ Cedar Financial USA"
    education    = "BSc CS (Hons) — GC University Lahore | Allama Iqbal Scholar"
    focus        = ["Production LLM Systems", "RAG Pipelines", "Agentic AI", "FastAPI Backends"]
    building     = ["AuditIQ — Multi-Agent FDCPA Compliance SaaS", "IQRAT — AI-Powered EdTech Platform"]
    philosophy   = "Deterministic logic before LLM reasoning. Always."
```

---

## `> ls featured/`

<div align="center">

| | Project | What it does |
|---|---|---|
| ⚖️ | **AuditIQ**| Multi-agent FDCPA compliance auditing engine. Dual-LLM pipeline with hybrid RAG, speaker segmentation, and rubric-based grading. |
| 🎓 | **IQRAT** | AI-powered academic management platform. Async FastAPI backend, Redis caching, WebSockets, LangGraph agents (Phase 3). |

</div>

---

## `> cat auditiq/overview.md`

**AuditIQ** is a production-grade AI compliance auditing system built for debt collection agencies operating under the FDCPA. It ingests call recordings and produces a structured compliance verdict with a downloadable PDF report — replacing manual QA that is slow, expensive, and legally inconsistent.

**The engineering decisions that matter:**

- **Deterministic pre-detection before the LLM** — regex catches arrest threats, third-party disclosures, and Mini-Miranda violations with 100% precision. Clear-cut federal violations never go through a probabilistic model.
- **Speaker segmentation before pre-detection** — Whisper returns flat text. A custom linguistic pattern scorer splits turns into `[AGENT]` / `[DEBTOR]` so FDCPA rules only evaluate the collector, never the consumer's reactive language.
- **Dual-LLM architecture** — Llama 3.1 70B audits; DeepSeek V4 Pro grades on a 10-point rubric (Mini-Miranda handling, legal grounding, ID accuracy, score calibration). One model can't self-evaluate without confirmation bias.
- **Hybrid retrieval** — Dense (NVIDIA nv-embed-v1) + BM25 sparse + MiniLM cross-encoder reranking, with direct rule fetch for pre-detected violations so the LLM always has the law regardless of semantic rank.
- **Eval-first** — 5 structured cases across FDCPA violation categories. Grader's `prompt_improvement_suggestion` is logged every run and used to refine the audit prompt between cycles.

```
Eval Results (5 cases):
Case 1 — Compliant call          → ✅ PASS  10/10  Grader: 9/10
Case 2 — Arrest threat           → ✅ FAIL   1/10  Grader: 10/10
Case 3 — Third-party disclosure  → ✅ FAIL   1/10  Grader: 9/10
Case 4 — False balance + abuse   → ✅ FAIL   1/10  Grader: 8/10
Case 5 — No Mini-Miranda         → ✅ FAIL   2/10  Grader: 9/10
```

**Stack:** `FastAPI` `Llama 3.1 70B` `DeepSeek V4 Pro` `ChromaDB` `BM25` `MiniLM` `Groq Whisper` `NVIDIA NIM` `React 19` `ReportLab` `SQLite`

---

## `> cat iqrat/overview.md`

**IQRAT** is an AI-powered academic management platform being built production-first from the ground up — not retrofitted. Currently in Phase 1 (complete), moving toward LangGraph agent integration.

**The 5 engineering decisions that define this project:**

- **Async-first from the foundation** — `asyncpg` engine with explicit pool config, `AsyncSession` throughout, WebSocket endpoints for live QR attendance and real-time feed. No sync engine, no blocking calls.
- **Security hardened at Phase 0** — `Depends(get_current_user)` across all `/me/*` endpoints, OTP migrated to Redis with TTL, `slowapi` rate limiting with a custom `limiter.py` module (resolved circular import between `auth.py` and `main.py`), credentials externalized via `pydantic-settings`.
- **Cache-aside pattern with typed domain helpers** — `app/cache.py` with named TTL constants, domain-specific invalidation functions, and typed wrappers. Not just `redis.set()` scattered across endpoints.
- **N+1 eliminated at the source** — all nested queries refactored to bulk fetch patterns. No lazy loading surprises under load.
- **LangGraph + ChromaDB agent layer incoming** — At-Risk Early Warning · Academic Integrity · Onboarding Orchestrator · Student Study Assistant. Agents designed around deterministic guardrails, not open-ended LLM calls.

```
Phase Status:
[████████████] Phase 0 — Security Hardening     ✅ Complete
[████████████] Phase 1 — Async Refactor          ✅ Complete
[░░░░░░░░░░░░] Phase 2 — ML Dataset + Training   🔄 In Progress
[░░░░░░░░░░░░] Phase 3 — LangGraph Agents + RAG  ⏳ Planned
```

**Stack:** `FastAPI` `asyncpg` `PostgreSQL` `Redis` `LangGraph` `ChromaDB` `Cloudinary` `WebSockets` `SQLAlchemy` `Pydantic` `slowapi`

→ **Architecture.md** *(coming end of week with Phase 2)*

---

## `> git log --journey`

<div align="center">

```
2022 ──────────────────────────────────────────────────── 2026

🎓  Allama Iqbal Scholar · GC University Lahore · BSc CS (Hons)
    ══════════════════════════════════════════════════════════►

📊  MindBridge Lahore · BI & Data Engineering
    ══════════════════════════════════════════════════════════►

         🇸🇪 Voi Technologies      🇦🇪 Careem          🇵🇱 Revolut
           Jul – Oct 2024        Oct 2024 – May 2025   May – Aug 2025
           ══════════►           ══════════════════►   ══════════►

                    🏦 Cedar Financial · MIS Specialist
                       Aug 2025 ──────────────────────►

                             🤖 Cedar Financial · Applied AI & LLMs Engineer
                                Apr 2026 ─────────────────────────────────►
```

*Every role above ran in parallel with the degree. No gaps. No breaks.*

</div>

| Period | Role | Scope |
|---|---|---|
| 2022–2026 | BSc CS (Hons) · Allama Iqbal Scholar | Ran everything below this simultaneously |
| Jul–Oct 2024 | BI Engineer · Voi Technologies (via MindBridge) | Fleet analytics, micromobility data pipelines · Sweden |
| Oct 2024–May 2025 | BI Engineer · Careem (via MindBridge) | Ride-hailing intelligence, multi-region reporting · UAE/PK |
| May–Aug 2025 | MIS Analyst · Revolut (via MindBridge) | Fintech data systems, compliance reporting · Poland |
| Aug 2025–Apr 2026 | MIS Specialist · Cedar Financial | Debt recovery analytics, operational intelligence |
| Apr 2026–Present | **Applied AI & LLMs Engineer · Cedar Financial** | Production AI systems, LLM pipelines, agentic workflows |

<div align="center">

<img src="https://img.shields.io/badge/3%2B_Years-Experience-0044cc?style=flat-square&labelColor=0a0a0f"/>
<img src="https://img.shields.io/badge/Global_Products-Voi%20%E2%80%A2%20Careem%20%E2%80%A2%20Revolut%20%E2%80%A2%20Cedar-0077ff?style=flat-square&labelColor=0a0a0f"/>
<img src="https://img.shields.io/badge/2_Flagships-AuditIQ%20%E2%80%A2%20IQRAT-0099ff?style=flat-square&labelColor=0a0a0f"/>
<img src="https://img.shields.io/badge/∞_Lines-Debugged%20at%202am-004499?style=flat-square&labelColor=0a0a0f"/>

</div>

---

## `> cat philosophy.txt`

```
1. Deterministic logic before LLM reasoning — always.
2. Security is not a phase. It is the foundation.
3. Async is not optional in production AI systems.
4. A RAG pipeline is only as good as its evaluation.
5. The system prompt is an engineering artifact, not an afterthought.
6. Cache what you can. Validate everything. Log what matters.
```

---

## `> github-stats`

<div align="center">

<img src="https://github-readme-stats.vercel.app/api?username=AakilMoh&show_icons=true&theme=transparent&hide_border=true&title_color=0099ff&icon_color=0066ff&text_color=ccddff&bg_color=0a0a0f" height="160"/>
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=AakilMoh&layout=compact&theme=transparent&hide_border=true&title_color=0099ff&text_color=ccddff&bg_color=0a0a0f" height="160"/>

<img src="https://github-readme-streak-stats.herokuapp.com/?user=AakilMoh&theme=transparent&hide_border=true&ring=0099ff&fire=00aaff&currStreakLabel=0077dd&sideLabels=0066ff&dates=667788&background=0a0a0f" width="60%"/>

</div>

---

## `> connect`

<div align="center">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Mohomed%20Akeel-0044cc?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/akeel-tech/)
[![Portfolio](https://img.shields.io/badge/Portfolio-ak__dev-0077ff?style=for-the-badge&logo=vercel&logoColor=white)](https://github.com/AakilMoh)
[![GitHub](https://img.shields.io/badge/GitHub-AakilMoh-0099ff?style=for-the-badge&logo=github&logoColor=white)](https://github.com/AakilMoh)
[![Email](https://img.shields.io/badge/Email-Reach%20Out-00aaff?style=for-the-badge&logo=gmail&logoColor=white)](mailto:aakilmohommed@gmail.com)

<br/>

*Based in Colombo. Thinking globally. Building things that actually ship.*

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:00aaff,50:0044cc,100:0a0a0f&height=100&section=footer" width="100%"/>

</div>
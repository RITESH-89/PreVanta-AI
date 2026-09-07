# 🛡️ PreVanta AI

## Predictive Safety Intelligence & SIF Precursor Detection Platform

> From fragmented safety reports to explainable early-warning intelligence.

![Smart India Hackathon 2026](https://img.shields.io/badge/Smart%20India%20Hackathon-2026-ff9933)
![SIH26165](https://img.shields.io/badge/SIH26165-Software-1f6feb)
![React](https://img.shields.io/badge/React-Vite-61dafb)
![FastAPI](https://img.shields.io/badge/FastAPI-backend-009688)
![Status](https://img.shields.io/badge/Status-Prototype-f1c40f)

PreVanta AI is being developed for **Smart India Hackathon 2026**, Problem Statement **SIH26165**, for **Oil India Limited (OIL)**.

---

## 📌 Project Overview

PreVanta AI is a human-in-the-loop decision-support platform for turning fragmented **Unsafe Act**, **Unsafe Condition**, **Near Miss**, and related safety narratives into explainable early-warning intelligence. The intended outcome is identification of **Serious Injury and Fatality (SIF) precursor characteristics**, recurring patterns, control failures, and priority areas for safety review.

The repository currently contains a working industrial-safety prototype: sensor/permit risk assessment, safety-reference retrieval, structured incident-pattern utilities, a small plant knowledge graph, image hazard inspection, and audit logging. It **does not yet contain the SIH report-ingestion and SIF-narrative analysis pipeline**. Those capabilities are explicitly marked **Planned**.

PreVanta does not predict an exact fatality, an exact probability of death, or when a fatality will occur. It supports informed human safety decisions.

## 🎯 Smart India Hackathon 2026

| Item | Details |
|---|---|
| Problem Statement ID | SIH26165 |
| Problem Statement | AI/NLP Engine to Detect Serious Injury & Fatality (SIF) Precursors in OIL's Unsafe-Act/Unsafe-Condition and Near-Miss Reports |
| Organization | Oil India Limited (OIL) |
| Category | Software |
| Theme | Smart Automation |
| Project Name | PreVanta AI |
| Domain | Predictive safety intelligence and SIF precursor detection |

## 🚨 The Problem

Narrative safety reports can contain early signals of high-consequence scenarios, yet similar hazards are described in different words, information is fragmented, control failures may be implicit, and recurring patterns can be missed in manual review. SIH26165 requires explainable analysis that helps safety teams identify potentially important precursor characteristics, connect reports to corrective action, and prioritize review.

## 💡 Our Solution

~~~text
Safety Report → Preprocessing → NLP Understanding → Entity Extraction
→ SIF Precursor Detection → Precursor DNA → Semantic Similarity
→ Recurring Pattern Detection → Safety Knowledge Graph → Risk Priority
→ Explainability → Corrective Action → Tracking → Verification
→ Continuous Improvement
~~~

This is the PreVanta product direction. The current repository supplies reusable prototype components, rather than a complete report-NLP workflow.

## 🧠 What Is a SIF Precursor?

A SIF precursor is an observable characteristic or combination of circumstances that may indicate a potentially high-consequence safety scenario. It is a reason to investigate and strengthen controls—not a guarantee that a serious injury or fatality will happen.

## ⭐ Why PreVanta AI?

| Basic approach | PreVanta direction |
|---|---|
| Report → Classification | Report → Understand → Detect → Explain → Connect → Prioritize → Recommend → Track → Verify |

A label alone is not enough for a safety decision. PreVanta is intended to retain evidence, relate similar descriptions, expose relevant controls and failure signals, and keep a human reviewer in the decision loop.

## 🏗️ System Architecture

The architecture distinguishes current repository components from the planned SIH report-intelligence path.

~~~mermaid
flowchart TB
    A[Current inputs: sensor, permit, image, knowledge query] --> B[FastAPI backend]
    B --> C[Safety and compliance assessment]
    B --> D[Safety-reference retrieval]
    B --> E[Image hazard inspection]
    C --> F[Audit trail and current dashboard]
    D --> F
    E --> F
    P[Planned safety report narrative] --> Q[Planned preprocessing and NLP]
    Q --> R[Planned SIF precursor detection and Precursor DNA]
    R --> S[Planned similarity and report knowledge graph]
    S --> T[Planned explainable priority and action workflow]
    T --> U[Planned SIF dashboard]
~~~

### Current implementation

- FastAPI backend with React/Vite client.
- Deterministic sensor/permit risk and compliance assessment.
- ChromaDB retrieval over local safety-reference material using all-MiniLM-L6-v2, with extractive fallback and optional Gemini synthesis.
- NetworkX graph for prototype zone, equipment, permit, and elevated-gas relationships.
- Structured incident utility that ranks permit/root-cause patterns and retrieves records by permit, zone, gas, and oxygen fields.
- OpenCV image-hazard fallback, optional Gemini vision, and SHA-256 hash-chained JSONL audit logging.

### Planned for SIH26165

- Narrative report upload, preprocessing, entity extraction, SIF precursor detection, and Precursor DNA.
- Semantic report similarity, a report-oriented knowledge graph, corrective-action tracking, and verification.

## 🔄 End-to-End Workflow

~~~mermaid
flowchart LR
    A[REPORT] --> B[UNDERSTAND] --> C[EXTRACT] --> D[DETECT]
    D --> E[EXPLAIN] --> F[CONNECT] --> G[PRIORITIZE]
    G --> H[RECOMMEND] --> I[TRACK] --> J[VERIFY] --> K[IMPROVE]
~~~

All stages in this report-oriented flow are planned; the present repository contains prototype foundations, not an implementation of this end-to-end SIF flow.

## 🧹 1. Data Preprocessing

**Status: Planned.** No code currently accepts, cleans, normalizes, de-duplicates, or structures Unsafe-Act, Unsafe-Condition, Near-Miss, or other narrative reports. A production pipeline must use OIL-approved fields, terminology, retention, and access controls.

## 🧠 2. NLP & Semantic Understanding

**Status: Partial foundation.** The knowledge-base builder chunks local PDF, text, and Markdown safety-reference material and indexes it in ChromaDB. The knowledge agent uses all-MiniLM-L6-v2 for retrieval, with an extractive fallback and optional Gemini-grounded synthesis.

This is document question-answering, not narrative safety-report understanding. Report entity extraction, classification, and SIF semantic interpretation are planned.

## 🚨 3. SIF Precursor Detection

**Status: Planned.** No SIF report taxonomy or SIF precursor classifier exists in the repository. The proposed taxonomy is subject to validation against available OIL data and domain-expert requirements; it is not an official OIL taxonomy.

## 🧬 4. Precursor DNA

**Status: Planned.** Precursor DNA is the proposed structured safety-risk fingerprint for a report. It may capture potential consequence, exposure, hazard characteristics, control presence/use/failure, recurrence, context, and model confidence where applicable. It is not a probability of death; any example values are illustrative unless backed by approved data and methodology.

## 🎯 5. Risk Priority Score

**Status: Planned for report intelligence.** The repository implements a separate deterministic 0–100 **sensor/permit compound-risk score** in utils/risk_model.py. It is not a SIF narrative Risk Priority Score and must not be interpreted as fatality probability. The report-level **Risk Priority Score** or **SIF Priority** will be defined only after the report schema, expert-reviewed taxonomy, and evaluation protocol exist.

## 💡 6. Explainable AI

**Status: Partial foundation.** Current sensor results expose rule triggers, score contributions, compliance findings, confidence dimensions, and suggested interventions. Knowledge responses return source metadata and excerpts; the audit log records sanitized events.

~~~text
Evidence → Model Interpretation → Recommendation
~~~

Evidence must remain distinct from AI inference. Report-level factors, source passages, confidence, and recommendations are planned.

## 🔎 7. Semantic Similarity

**Status: Partial foundation.** Embedding retrieval is implemented for the local safety-reference corpus via ChromaDB and all-MiniLM-L6-v2. It is not yet used to compare safety-report narratives.

The structured incident utility uses permit overlap, zone match, gas proximity, and oxygen proximity—not semantic text embeddings. Narrative similarity is planned so “Forklift nearly hit worker,” “Pedestrian almost struck by vehicle,” and “Vehicle entered pedestrian zone” can be reviewed as potentially related patterns despite different wording.

## 📈 8. Recurring Precursor Detection

**Status: Partial.** utils/incident_intelligence.py groups the bundled structured incident corpus by hazardous permit, permit pair, and root cause, then ranks results using occurrence and configured severity weights. This is a prototype pattern utility, not narrative SIF recurrence detection.

The corpus in knowledge_base/incidents.json includes simulated examples; it is not represented as OIL operational data. Semantic grouping of real narrative reports is planned.

## 🕸️ 9. Safety Knowledge Graph

**Status: Partial.** The repository uses NetworkX, not Neo4j. Its implemented graph models prototype zone → equipment, permit → zone, and zone adjacency relationships, and flags permits near elevated-gas conditions.

The report-oriented relationship below is proposed:

~~~text
Report → Activity → Hazard → Control → Control Failure
       → Exposure → Potential Consequence → SIF Precursor
~~~

## 📊 10. Trend & Hotspot Analysis

**Status: Partial.** The current dashboard supports prototype sensor trends/forecasts, zone status, structured incident patterns, and a facility map. It does not provide report-based time, location, department, activity, equipment, hazard, precursor-category, or control-failure hotspot analysis. Those dimensions are planned.

## 🧩 11. Root Cause Intelligence

**Status: Partial foundation.** Bundled structured incident data includes a root_cause field, and the prototype pattern utility aggregates it. People, process, equipment, environment, and organizational-factor analysis for narrative reports is planned. AI can assist investigation; it never replaces a formal safety investigation.

## 🛡️ 12. Control Effectiveness Analysis

**Status: Planned.** The target intelligence layer distinguishes:

~~~text
Control Exists → Control Used → Control Effective
~~~

The current code can propose sensor/permit interventions but does not establish report-level control use or effectiveness.

## ⚡ 13. Corrective Action Intelligence

**Status: Planned for SIF reports.** The sensor prototype returns deterministic recommended interventions and simulated dispatch payloads, but it does not implement corrective-action owner assignment, due dates, status, or verification. These are planned human-managed features; no automated safety authority is claimed.

## 🤖 14. Safety Copilot

**Status: Partial.** The Knowledge view/API queries local safety-reference material through ChromaDB retrieval and returns sources. Optional Gemini synthesis is constrained by retrieved context when configured; otherwise an extractive fallback is used.

There is no report-aware copilot combining OIL reports, a report knowledge graph, approved safety knowledge, and corrective-action evidence. That capability is planned.

## 🎙️ 15. Voice Safety Reporting

**Status: Planned / Phase 2.** The repository includes browser text-to-speech for prototype briefings and static multilingual evacuation messages, but not speech-to-text intake for safety reports.

~~~text
Voice → Speech-to-Text → NLP → SIF Precursor Detection → Priority → Action
~~~

## 🌐 16. Multilingual Safety Reporting

**Status: Planned for reports.** The prototype has static evacuation templates for English, Hindi, Telugu, Tamil, Marathi, Kannada, Punjabi, Gujarati, Bengali, and Odia, plus browser speech output where a device voice is available. It does not implement multilingual report ingestion, translation validation, or multilingual SIF analysis.

## 🖼️ 17. Multimodal Safety Analysis

**Status: Partial foundation.** The Vision view accepts an image or camera capture and returns hazard labels from an OpenCV fallback or optional Gemini vision. It does not connect images to safety reports or SIF precursor detection. Multimodal report intelligence is Phase 2.

## 🔄 18. Closed-Loop Safety Intelligence

**Status: Planned.**

~~~text
Detect → Prioritize → Act → Verify → Review New Reports → Improve
~~~

The current hash-chained audit trail can support traceability, but report-level action tracking and verification are not implemented. No causal prevention outcome is claimed.

## 🖥️ Dashboard

The implemented React dashboard is a **sensor/permit prototype**, not a report-analysis dashboard. Its current views cover:

- Dashboard: sensor/permit controls, risk contributions, confidence, interventions, limits, and simulated live stream.
- Zone Map: Leaflet facility display, response-facility markers, permit-proximity findings, and a prototype graph.
- Vision: image upload or camera capture with hazard inspection.
- Knowledge: RAG questions over local safety references.
- Emergency and Safety Tools: simulated multilingual dispatch/briefing, exposure calculation, and nearby facilities.
- Intelligence and Benchmark: structured incident patterns, audit display, and prototype evaluation tooling.

## 📄 Report Analysis View

**Status: Planned.** The target interface will present original narrative, extracted safety entities, SIF precursor analysis, SIF Priority, Precursor DNA, explanation, similar reports, and corrective-action context. These report fields are not currently represented in the frontend or API.

## 🧠 AI / ML Strategy

| Area | Repository evidence | Status |
|---|---|---|
| Safety-reference retrieval | ChromaDB and all-MiniLM-L6-v2 | Implemented |
| Grounded answer synthesis | Optional Gemini; extractive fallback | Implemented |
| Sensor/permit scoring | Deterministic rules and graduated score | Implemented |
| Image hazard inspection | OpenCV fallback; optional Gemini; model artifacts/scripts | Implemented prototype |
| Narrative SIF classifier | No training or inference pipeline found | Planned |
| Report entity extraction | No implementation found | Planned |
| Narrative similarity | No implementation found | Planned |

No SIF training methodology, report classifier, model accuracy, benchmark, or OIL data experiment is claimed.

## 📚 Data Strategy

The repository contains local safety-reference material in knowledge_base/raw and a structured incident file at knowledge_base/incidents.json. Bundled incident descriptions include simulated examples and must be treated as prototype/demo data, not confidential OIL operational data.

Any OIL data used in future work requires appropriate authorization. Public, synthetic, expert-created, and operational data must remain clearly distinguishable.

## 🏷️ Data Annotation

**Status: Planned.** No final SIF report dataset schema or annotated OIL dataset is present. A proposed record may include report narrative, activity, hazard, exposure, controls, possible control failure, potential consequence, precursor characteristics, reviewer rationale, and adjudication status. This is proposed, not an OIL standard.

## 🧪 Evaluation Strategy

**Status: Planned for SIF reports.** The repository has prototype tests and sensor-oriented benchmark tooling, which are not evidence of SIF detection performance. A report evaluation should use expert-reviewed labels and measure precision, recall, F1, explanation usefulness, retrieval quality, and knowledge-graph validation. No SIF results are reported here.

## ⚠️ False Positives & False Negatives

False positives can burden reviewers and weaken trust; false negatives can hide an important precursor. Because this is safety decision support, potentially consequential false negatives require special attention, review protocols, and iterative calibration with domain experts. Human review remains mandatory.

## 🔐 Security & Privacy

Current controls include an environment-file pattern for the optional Gemini key and a sanitized, SHA-256 hash-chained JSONL audit trail. The prototype does **not** implement authentication, authorization, role-based access control, production API hardening, or a verified data-protection program; its API currently permits all CORS origins.

Production requirements include authentication, authorization, secure APIs, input validation, audit logging, secret management, encryption/secure storage, controlled access, and data-protection review.

## 🧰 Technology Stack

| Category | Technology | Status |
|---|---|---|
| Frontend | React, Vite, Leaflet, React Flow, browser Web Speech | Implemented |
| Backend | Python, FastAPI, Pydantic, Uvicorn | Implemented |
| Orchestration | LangGraph | Implemented |
| Knowledge retrieval | ChromaDB, sentence-transformers all-MiniLM-L6-v2 | Implemented |
| Knowledge graph | NetworkX prototype graph | Implemented |
| Vision | OpenCV; optional Gemini; PyTorch/Transformers artifacts/scripts | Implemented prototype |
| Local persistence | SQLite telemetry; JSON/JSONL prototype data and audit | Implemented |
| Report NLP / SIF model | Not present | Planned |
| Report vector search / graph | Not present | Planned |
| Containerization | No configuration found | Planned |

## 🗂️ Project Structure

~~~text
agents/          Current orchestration and safety-related agents
backend/         FastAPI application and MQTT listener
compliance/      JSON safety-rule data
data/            Prototype data, audit/evidence artifacts, and plant image
frontend/        React/Vite web client
knowledge_base/  Local safety-reference ingestion and incident corpus
models/          Vision-model training/download artifacts
tools/           Prototype demos, checks, and benchmark utilities
ui/              Streamlit prototype interface
utils/           Risk, retrieval, graph, audit, vision, and support utilities
tests/           Automated test suite
schema.py         Shared dataclass contract
~~~

## 🚀 MVP Scope

### Implemented / Core

- Sensor/permit safety assessment and prototype compliance checks.
- Safety-reference RAG with citations/source metadata.
- Structured incident recurrence and similar-record retrieval.
- Prototype plant knowledge graph and permit-proximity checks.
- Image hazard inspection, audit log, browser speech output, and static evacuation templates.

### Remaining MVP

- Safety-report upload/storage and validated report schema.
- Narrative preprocessing, entity extraction, and SIF precursor detection.
- Precursor DNA, report-level SIF Priority, semantic report similarity, and recurrence.
- Report-oriented graph, corrective-action ownership/tracking/verification, and report dashboard.

## 🔮 Phase 2

- Voice-report intake and speech-to-text.
- Multilingual report understanding with safety-review validation.
- Multimodal fusion of report narratives and images.
- Advanced grounded Safety Copilot, report hotspot analytics, and approved enterprise integrations.

## 🗓️ Development Roadmap

1. Define an OIL-approved report schema, annotation guide, and access process.
2. Build report ingestion, preprocessing, and reviewer workflow.
3. Validate a SIF precursor taxonomy with safety-domain experts.
4. Implement explainable report detection, Precursor DNA, and SIF Priority.
5. Add semantic recurrence, report graph links, corrective-action workflow, and verification.
6. Evaluate with expert-reviewed data before making performance claims.

## 🎬 SIH Demonstration Flow

| Step | Demonstration | Status |
|---:|---|---|
| 1 | Upload safety report | Planned |
| 2 | Process report | Planned |
| 3 | Extract safety entities | Planned |
| 4 | Detect SIF precursor characteristics | Planned |
| 5 | Generate Precursor DNA | Planned |
| 6 | Show SIF Priority | Planned |
| 7 | Show evidence-based explanation | Planned |
| 8 | Show similar reports | Planned |
| 9 | Show recurring pattern | Planned; structured prototype is not report similarity |
| 10 | Show report safety knowledge graph | Planned; current graph is sensor/permit oriented |
| 11 | Show corrective action | Planned |
| 12 | Track action | Planned |
| 13 | Verify action | Planned |

## 🏆 Innovation Highlights

| Concept | Status |
|---|---|
| Precursor DNA | Proposed |
| SIF-focused NLP | Planned |
| Semantic Recurrence Detection | Planned |
| Report Safety Knowledge Graph | Planned |
| Explainable Risk Prioritization | Planned for reports; sensor explanations exist |
| Control Effectiveness | Planned |
| Grounded Safety Copilot | Partial foundation via safety-reference RAG |
| Closed-Loop Prevention Workflow | Planned |

## 👥 Team Responsibilities

| Member | Focus |
|---|---|
| RITESH PAITHANKAR | AI/NLP: preprocessing, entity extraction, precursor modelling, evaluation |
| RUTUJA PAWAR | Knowledge Graph: ontology, evidence links, recurrence, graph validation |
| NIRAJ KHARAT | Backend: APIs, data contracts, retrieval, security, auditability |
| GANESH TAUR | Frontend: reviewer dashboard, explanations, action workflow, accessibility |
| SUMIT RATHOD | Integration / Research / Testing: data governance, research, QA, demo integration |
| SARTHAK KATORE | Integration / Research / Testing: data governance, research, QA, demo integration |

## ⚖️ Responsible AI

PreVanta does **not** claim exact fatality prediction, exact probability of death, guaranteed incident prevention, autonomous safety decisions, or replacement of safety professionals.

PreVanta provides SIF precursor detection, risk prioritization, evidence-based explanations, semantic report comparison, recurring-pattern identification, knowledge-graph relationships, corrective-action support, and human-in-the-loop decision support.

## 👨‍⚖️ Human-in-the-Loop

~~~text
AI → Analyze → Explain → Prioritize → Recommend
   → Human Safety Review → Decision → Action
~~~

The human reviewer validates evidence, considers context, owns the decision, and determines any action.

## 🔐 Responsible Data Usage

Confidential operational data must be used only with appropriate authorization. The target platform requires data minimization, controlled access, anonymization where appropriate, secure storage, retention controls, and auditable use.

## 📌 Project Positioning

> **PreVanta AI transforms fragmented safety reports into explainable early-warning intelligence for SIF precursor detection and preventive action.**

PreVanta AI is an AI/NLP-powered predictive safety intelligence platform being developed to analyze Unsafe-Act, Unsafe-Condition, and Near-Miss reports; identify SIF precursor characteristics; discover recurring patterns; connect hazards and controls through a Safety Knowledge Graph; explain risk priorities; and support corrective-action workflows.

## 🎤 SIH Pitch

PreVanta AI addresses SIH26165 by moving safety-report review from fragmented narratives toward explainable early-warning intelligence. The current prototype demonstrates reusable safety, retrieval, graph, vision, and audit foundations. The SIH MVP will add report-centric NLP, SIF precursor detection, evidence-led prioritization, and a human-reviewed corrective-action workflow.

## 📚 Research Foundation

The design direction is informed by OSHA and IOGP leading-indicator guidance, the NIST AI Risk Management Framework, NLP, transformer embeddings, knowledge graphs, retrieval-augmented generation, and explainable AI. These are conceptual foundations; no unverified papers, statistics, or OIL-specific validation are claimed.

## 📊 Claim & Evidence Policy

### Verified Fact

Supported by an authoritative source or the official SIH problem statement.

### Implemented Feature

Present in repository code and described above with its actual scope.

### Prototype Result

Measured by a documented project evaluation. No SIF prototype result is claimed here.

### Planned Feature

A future capability not represented as working implementation.

## 🚫 No Fabricated Results

This project will not fabricate accuracy, precision, recall, number of reports, prevention percentage, financial savings, ROI, fatality probability, benchmark results, or user-adoption statistics.

## 🧭 Implementation Status

| Capability | Status |
|---|---|
| Safety Report Analysis | Planned |
| NLP Preprocessing | Planned |
| Safety Entity Extraction | Planned |
| SIF Precursor Detection | Planned |
| Precursor DNA | Planned |
| Risk Priority | Planned for reports; separate sensor score implemented |
| Explainability | Partial |
| Semantic Similarity | Partial foundation |
| Recurring Precursor Detection | Partial structured prototype |
| Safety Knowledge Graph | Partial sensor/permit prototype |
| Corrective Action Workflow | Planned |
| Dashboard | Partial sensor/permit prototype |
| Voice Reporting | Phase 2 |
| Multilingual Reporting | Planned |
| Image Analysis | Implemented prototype |
| Safety Copilot | Partial safety-reference RAG |

## 🌱 Future Vision

~~~text
Today:  Safety Reports → SIF Precursor Detection → Explainable Prioritization
        → Pattern Intelligence → Corrective Actions
Future: Voice → Multilingual → Vision → Multimodal Safety Intelligence
~~~

## 🎯 Final Vision

~~~text
REACTIVE:  Report Review → Incident Understanding
PROACTIVE: Precursor Detection → Pattern Intelligence → Explainable Prioritization
           → Preventive Action → Verification
~~~

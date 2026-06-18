<div align="center">

<br/>

```
██╗   ██╗ █████╗ ██╗   ██╗██╗  ████████╗███╗   ███╗██╗███╗   ██╗██████╗
██║   ██║██╔══██╗██║   ██║██║  ╚══██╔══╝████╗ ████║██║████╗  ██║██╔══██╗
██║   ██║███████║██║   ██║██║     ██║   ██╔████╔██║██║██╔██╗ ██║██║  ██║
╚██╗ ██╔╝██╔══██║██║   ██║██║     ██║   ██║╚██╔╝██║██║██║╚██╗██║██║  ██║
 ╚████╔╝ ██║  ██║╚██████╔╝███████╗██║   ██║ ╚═╝ ██║██║██║ ╚████║██████╔╝
  ╚═══╝  ╚═╝  ╚═╝ ╚═════╝ ╚══════╝╚═╝   ╚═╝     ╚═╝╚═╝╚═╝  ╚═══╝╚═════╝
```

### **Early Warning System — Insider Fraud Detection for Banking**

<br/>

[![FastAPI](https://img.shields.io/badge/FastAPI-2.0.0-009688?style=flat-square&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat-square&logo=python&logoColor=white)](https://python.org)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-IsolationForest-F7931E?style=flat-square&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![NetworkX](https://img.shields.io/badge/NetworkX-Graph%20Analytics-blue?style=flat-square)](https://networkx.org/)
[![SQLite](https://img.shields.io/badge/SQLite-Database-003B57?style=flat-square&logo=sqlite&logoColor=white)](https://sqlite.org/)
[![WebSocket](https://img.shields.io/badge/WebSocket-Real--time%20Alerts-6B4FBB?style=flat-square)](https://developer.mozilla.org/en-US/docs/Web/API/WebSocket)

<br/>

> **VaultMind** is a real-time multi-agent fraud intelligence platform designed for financial institutions.  
> It detects insider threats by correlating behavioral anomalies, transaction patterns, and network signals  
> across **8 specialized AI agents** — firing alerts in under 3 seconds.

<br/>

</div>

---

## 🧠 What is VaultMind?

Traditional fraud systems rely on static rule thresholds that treat every employee the same. VaultMind takes a different approach: each employee gets their **own AI baseline**, and the system flags deviations from *their* normal — not a global average.

When Employee 4471 logs in at 2:47 AM from an unknown IP and downloads **4,847 records** (210× their baseline), VaultMind doesn't wait for a manager to notice. It fires a critical alert, freezes the account, generates a blockchain-hashed evidence package, and auto-files a Suspicious Transaction Report — all in under **3 seconds**.

```
Normal Day                     |  Fraud Scenario (EMP4471)
───────────────────────────────|──────────────────────────────────────────────
09:15 AM  Login — Mumbai       |  02:47 AM  LOGIN — Unknown IP 10.58.201.99
10:30 AM  23 records accessed  |  02:48 AM  4,847 RECORDS DOWNLOADING  [210×]
04:45 PM  4 txn — avg ₹85,000  |  02:49 AM  ₹47L SWIFT TRANSFER ATTEMPTED
06:30 PM  Normal logout        |  02:49:18  ⚡ VAULTMIND CRITICAL ALERT FIRED
          Score: ~12            |  02:49:19  🔒 ACCOUNT ACCESS FROZEN
                               |  02:49:20  🔗 BLOCKCHAIN HASH GENERATED
                               |            Score: 96/100 — CRITICAL
```

---

## ✨ Key Features

| Feature | Description |
|---|---|
| 🤖 **8 Specialized AI Agents** | Each agent focuses on a distinct fraud signal domain |
| 📊 **Unified Threat Score** | Weighted multi-agent score (0–100) with risk classification |
| ⚡ **Real-time WebSocket Alerts** | Live alert streaming with 5-second refresh cycles |
| 🔒 **Auto-Freeze at 80+** | Automatic account lockout on critical threat scores |
| 🔗 **Blockchain Evidence Hashing** | SHA-256 tamper-proof evidence packages for investigations |
| 📋 **Auto-STR Generation** | Suspicious Transaction Reports filed in 2.8 seconds |
| 🪤 **Deception Guard (Honeypot)** | Mirage accounts that trap bad actors probing the system |
| 🔍 **Explainable AI (XAI)** | Counterfactual sliders showing exactly why a score fired |
| 📡 **RBI Auto-Notification** | Regulatory body notified automatically at score ≥ 90 |

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────────┐
│                        VaultMind Platform                        │
│                                                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                     Frontend (Vanilla JS)                 │   │
│  │   Dashboard · Alerts · Employees · XAI · Deception Guard  │   │
│  └────────────────────────┬─────────────────────────────────┘   │
│                            │ REST + WebSocket                     │
│  ┌─────────────────────────▼────────────────────────────────┐   │
│  │               FastAPI Backend (main.py)                   │   │
│  │      /api/dashboard  /api/alerts  /api/employees          │   │
│  │      /api/evidence   /api/counterfactual  /ws/alerts      │   │
│  └─────────────────────────┬────────────────────────────────┘   │
│                             │                                     │
│  ┌──────────────────────────▼────────────────────────────────┐  │
│  │                  Orchestrator (Brain)                      │  │
│  │            Aggregates all 8 agent scores                   │  │
│  │         Applies weights → Unified Threat Score             │  │
│  │       Auto-freeze · Evidence · STR · RBI notify            │  │
│  └──┬──────┬──────┬──────┬──────┬──────┬──────┬─────────────┘  │
│     │      │      │      │      │      │      │                  │
│  ┌──▼──┐┌──▼──┐┌──▼──┐┌──▼──┐┌──▼──┐┌──▼──┐┌──▼──┐┌──────┐   │
│  │ B.W ││ F.F ││ V.G ││ C.S ││ N.I ││ R.C ││ E.B ││ D.G  │   │
│  └─────┘└─────┘└─────┘└─────┘└─────┘└─────┘└─────┘└──────┘   │
│                                                                   │
│  ┌──────────────────────────────────────────────────────────┐   │
│  │                    SQLite Database                        │   │
│  │  employees · behavior_logs · transactions · alerts        │   │
│  │  complaints · vendor_logs · mirage_accounts               │   │
│  └──────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────┘
```

---

## 🤖 The 8 Agents

### Agent 1 — BehaviorWatch `(Weight: 35%)`
> *"Does this match who this person is?"*

Trains a personal **Isolation Forest** model per employee using 60 days of historical behavior. Detects anomalies in login times, logout patterns, and records accessed — relative to *that individual's* baseline, not a global rule.

- Scikit-learn `IsolationForest` with `contamination=0.05`
- Flags off-hours logins, unknown IPs, and access volume spikes
- Most heavily weighted agent in the Unified Threat Score

---

### Agent 2 — FundFlow `(Weight: 25%)`
> *"Is money moving in suspicious patterns?"*

Builds a **directed transaction graph** using NetworkX and runs graph algorithms to detect financial crime patterns invisible to rule-based systems.

- Detects **circular transactions** (money laundering loops) via `nx.simple_cycles()`
- Identifies **structuring** — transactions just under ₹10L reporting threshold
- Flags **dormant account activations** — sudden activity on long-idle accounts

---

### Agent 3 — VendorGuard `(Weight: 8%)`
> *"Are vendor API calls behaving normally?"*

Monitors third-party vendor API endpoints for anomalous call volumes. Unusual patterns in vendor integrations can indicate data exfiltration or system probing.

---

### Agent 4 — ComplaintSignal `(Weight: 7%)`
> *"Are customers complaining about this employee?"*

Correlates customer complaint records linked to specific employees over a 30-day rolling window. Repeated complaints involving large amounts are a leading indicator of misconduct.

---

### Agent 5 — NetworkIntelligence `(Weight: 20%)`
> *"Who is this person connected to?"*

Analyzes social and professional network relationships for suspicious associations. Cross-references IP addresses, devices, and access patterns across employees to detect coordinated insider threats.

---

### Agent 6 — RegulatoryCompliance `(Weight: 5%)`
> *"Are any compliance rules being broken?"*

Checks transactions and behaviors against RBI regulatory rules. Triggers automatic Suspicious Transaction Report (STR) generation when violations are detected. Acts as the escalation trigger to the regulator.

---

### Agent 7 — EvidenceBuilder
> *"Build a court-ready evidence package."*

When Unified Threat Score ≥ 70, automatically compiles all agent findings into a tamper-proof evidence package. Generates a **SHA-256 blockchain hash** of the full incident record for audit and legal use.

---

### Agent 8 — DeceptionGuard (Honeypot)
> *"Let bad actors reveal themselves."*

Creates **mirage accounts** — fake high-value accounts visible only to employees with suspicious scores. Any access to these non-existent accounts is definitive evidence of malicious intent. Zero false positives.

---

## 📊 Unified Threat Score

The Orchestrator aggregates all agent scores using a weighted formula:

```python
WEIGHTS = {
    "behavior":    0.35,   # Personal AI baseline (heaviest signal)
    "fund_flow":   0.25,   # Transaction graph anomalies
    "network":     0.20,   # Network intelligence
    "vendor":      0.08,   # Vendor API patterns
    "complaint":   0.07,   # Customer complaint correlation
    "regulatory":  0.05    # Compliance violations
}

# Multi-agent boost: if 3+ agents score ≥60, score multiplied ×1.25
if agents_flagging >= 3:
    unified_score = min(100, unified_score * 1.25)
```

| Score Range | Risk Level | Automatic Action |
|---|---|---|
| 90 – 100 | 🔴 CRITICAL | Account frozen + RBI notified |
| 80 – 89 | 🔴 CRITICAL | Account frozen |
| 70 – 79 | 🟠 HIGH | Enhanced monitoring |
| 50 – 69 | 🟡 MEDIUM | Flagged for review |
| 0 – 49 | 🟢 LOW | Normal monitoring |

---

## 📁 Project Structure

```
Early-Warning-System-Fraud-Detection/
│
├── backend/
│   ├── main.py                  # FastAPI server — all REST endpoints + WebSocket
│   ├── generate_data.py         # Synthetic data generator for the SQLite DB
│   ├── requirements.txt         # Python dependencies
│   ├── vaultmind.db             # SQLite database (pre-seeded with demo data)
│   │
│   └── agents/
│       ├── behavior_watch.py    # Agent 1: Isolation Forest per-employee baseline
│       ├── fund_flow.py         # Agent 2: NetworkX transaction graph analytics
│       ├── other_agents.py      # Agents 3–8: VendorGuard, ComplaintSignal, etc.
│       └── orchestrator.py      # Brain: weighted score aggregation + auto-actions
│
├── frontend/
│   └── index.html               # Single-file SPA — dashboard, alerts, XAI explorer
│
├── patch.py                     # DB patch utility
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.10+
- pip

### 1. Clone the repository

```bash
git clone https://github.com/MilindLate/Early-Warning-System-Fraud-Detection.git
cd Early-Warning-System-Fraud-Detection
```

### 2. Install dependencies

```bash
pip install -r backend/requirements.txt
```

### 3. Start the backend server

```bash
cd backend
python main.py
```

The API will be available at:
- **API:** `http://localhost:8000`
- **Interactive Docs:** `http://localhost:8000/docs`
- **WebSocket:** `ws://localhost:8000/ws/alerts`

### 4. Open the frontend

Open `frontend/index.html` directly in your browser — no build step required.

---

## 📡 API Reference

| Method | Endpoint | Description |
|---|---|---|
| `GET` | `/api/dashboard` | Stats, top-risk employees, recent alerts, agent status |
| `GET` | `/api/alerts` | All alerts ordered by Unified Threat Score |
| `GET` | `/api/employees` | Employee list with risk scores |
| `GET` | `/api/employees/{id}` | Employee detail + 30-day behavior history |
| `GET` | `/api/evidence/{id}` | Evidence package with blockchain hash |
| `GET` | `/api/counterfactual/{id}` | Live score recalculation with custom inputs |
| `GET` | `/api/deception-guard` | Mirage account access status |
| `POST` | `/api/demo/trigger` | Trigger the Employee 4471 demo scenario |
| `POST` | `/api/deception-guard/simulate-access` | Simulate mirage account access |
| `WS` | `/ws/alerts` | Real-time alert stream (5-second push) |

---

## 🔍 Explainable AI — Counterfactual Explorer

VaultMind includes an interactive XAI module that answers: *"Why did this alert fire?"*

Adjust three sliders in real time to see how each variable contributes to the Unified Threat Score:

```
Login Time      [──────●────────────]  02:47 AM  → +38 points
Records Accessed [──────────────────●]  4,847      → +35 points
Transaction Amt  [────────────────●──]  ₹47,00,000 → +20 points
Unknown IP                              (fixed)    → +15 points
                                                   ─────────────
                                         SCORE:       96 / 100
```

This gives investigators an instant, human-readable explanation for every alert — critical for compliance, audit trails, and court submissions.

---

## 🪤 DeceptionGuard — Honeypot Accounts

Ten **mirage accounts** with realistic names and high balances are seeded in the system. They are completely fictitious and serve no legitimate banking purpose. Any employee who accesses them:

1. Has explicitly gone looking for accounts outside their workstream
2. Triggers an immediate high-confidence alert
3. Provides **irrefutable evidence** — there is no innocent explanation for accessing a mirage account

```python
MIRAGE_ACCOUNT_IDS = [f"MIRAGE_{i:04d}" for i in range(1, 11)]
# MIRAGE_0001 through MIRAGE_0010
# Visible only to employees with elevated risk scores
```

---

## 🔗 Blockchain Evidence

Every high-risk alert (score ≥ 70) generates a tamper-proof evidence package:

```json
{
  "alert_id": "ALERT_EMP4471_20250619024919",
  "unified_score": 96.0,
  "evidence_hash": "a3f8c2d1e4b6...",
  "blockchain_status": "CONFIRMED",
  "str_status": "AUTO_GENERATED",
  "generation_time": "2.8 seconds"
}
```

The SHA-256 hash covers the complete incident record — agent scores, reasons, timestamps, and employee data — making it cryptographically verifiable that the evidence was not altered after the alert fired.

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Backend Framework** | FastAPI 2.0 |
| **Behavioral AI** | scikit-learn `IsolationForest` |
| **Graph Analytics** | NetworkX directed graph algorithms |
| **Numerical Computing** | NumPy |
| **Database** | SQLite 3 |
| **Real-time** | WebSocket (native FastAPI) |
| **Evidence Integrity** | Python `hashlib` SHA-256 |
| **Frontend** | Vanilla HTML/CSS/JS (IBM Plex fonts) |

---

## 🏦 Built For

VaultMind is designed for **Indian banking institutions** operating under RBI guidelines. It speaks the domain's language:

- Transaction amounts in **₹ (INR)**
- Structured reporting thresholds at **₹10 Lakhs** (`STRUCTURING_THRESHOLD = 1,000,000`)
- **STR (Suspicious Transaction Report)** auto-generation per PMLA requirements
- **RBI auto-notification** on critical scores
- Branch-aware employee tracking across India

---

## 📄 License

This project is open for academic and educational use.  
See [LICENSE](LICENSE) for details.

---

<div align="center">

Built with ⚡ by [MilindLate](https://github.com/MilindLate)

*"Traditional fraud systems play checkers. VaultMind plays chess."*

</div>

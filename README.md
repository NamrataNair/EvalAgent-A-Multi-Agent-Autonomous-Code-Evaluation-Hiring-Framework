# EvalAgent-A-Multi-Agent-Autonomous-Code-Evaluation-Hiring-Framework
EvalAgent is a multi-agent AI framework that autonomously evaluates software engineering submissions using Docker sandbox execution, UI automation, and LLM-based rubric scoring with debate arbitration. It replaces manual technical review with structured, reproducible, and bias-aware evaluation.

## 🚀 Why This Project?

Traditional technical evaluations suffer from:

- Manual code inspection
- Inconsistent scoring
- Subjective bias
- Limited runtime validation
- No structured rubric enforcement

EvalAgent solves this by combining:

- 🐳 Docker sandbox execution
- 🌐 Playwright-based UI automation
- 🧠 Multi-agent LLM debate scoring
- 📊 Structured rubric enforcement
- 📁 Automated Excel reporting

---

## 🏗 Architecture Overview

The system follows a modular multi-agent architecture:
Candidate Repo
↓
Executor Agent (Docker Sandbox)
↓
Static + Feature Analysis
↓
UI Automation Agent (Playwright)
↓
Judge A (Strict)
Judge B (Pragmatic)
↓
Final Arbitration Judge
↓
Aggregator (Scale Enforcement)
↓
Excel Report

The system will:
1. Execute projects in sandbox
2. Evaluate features
3. Perform UI testing (if enabled)
4. Run multi-agent LLM scoring
5. Generate Excel report


## **🔐 Design Philosophy**
EvalAgent separates:
Judgement (LLMs)
Governance (Aggregator enforcement)
Execution (Docker sandbox)
Validation (Feature/UI agents)

This ensures robustness, fairness, and reproducibility.



## 🧠 Agents in the System

### 1️⃣ Executor Agent
- Runs candidate project inside Docker
- Installs dependencies
- Captures logs and runtime failures
- Prevents host contamination

### 2️⃣ Static & Feature Agent
- Extracts project structure
- Parses README
- Infers implemented features
- Detects missing core files

### 3️⃣ UI Agent (Optional)
- Launches browser using Playwright
- Captures screenshots
- Tests responsiveness
- Detects frontend failures

### 4️⃣ Multi-Agent Debate Scoring
Two LLM judges independently score:

- Problem Understanding (20)
- Architecture & Code Quality (30)
- Feature Completeness (30)
- UI/UX (20)

A final arbitration agent resolves scoring differences.

### 5️⃣ Aggregator Layer
- Enforces rubric scale constraints
- Clamps invalid scores
- Normalizes outputs
- Formats final structured report

---

## 📊 Output Format

Each candidate is evaluated as:

| Candidate Name | Problem (20) | Architecture (30) | Feature (30) | UI/UX (20) | Total (100) | Final (/10) | Remarks |
|---------------|--------------|-------------------|--------------|------------|-------------|-------------|---------|

Excel file: `evaluation_results.xlsx`

---
## **Author**
Namrata Nair
AI Engineer | Agent Systems | LLM Architect
Focused on autonomous systems, evaluation pipelines, and multimodal AI frameworks.

## ⚙️ Installation

### 1️⃣ Clone Repository

```bash
git clone <repo>
cd evalagent

python3 -m venv venv
source venv/bin/activate

pip install pandas openpyxl playwright ollama
playwright install

**## Install Docker**
Make sure Docker is installed and running.

Place candidate folders inside:
candidates/

python run_agentic_evaluation.py


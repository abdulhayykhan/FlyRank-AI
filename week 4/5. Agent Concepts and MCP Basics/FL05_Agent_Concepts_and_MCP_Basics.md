# FL-05 — Agent Concepts and MCP Basics

**Course Track:** General AI Fluency Track (Week 4 — Assignment 5)  
**Assignment Code:** FL-05  
**Author:** Abdul Hayy Khan  
**Institution / Role:** 3rd Year Artificial Intelligence Student & ML Engineering Intern (DUET / FlyRank AI)  
**Date:** July 2026  

---

## Executive Overview

This document presents **Agent Concepts and MCP Basics (FL-05)**. In contemporary AI engineering, the word "agent" is frequently overused to describe simple prompt chains. This deliverable establishes the formal technical boundary between deterministic workflows and autonomous LLM agents, provides a clear architectural breakdown of the Model Context Protocol (MCP), documents three working tool-assisted tasks beyond plain chat capabilities, and proposes a concrete agentic upgrade for our FL-04 research synthesis pipeline.

---

## 1. Technical Distinction: Workflow vs. Agent

Understanding control flow architecture is essential to separate marketing terminology from production systems design.

```text
+---------------------------------------------------------------------------------------+
| DETERMINISTIC WORKFLOW (FL-04 Pipeline)                                               |
|  User Input ---> [Step 1: Gather] ---> [Step 2: Extract] ---> [Step 3: Draft] ---> Output|
|  * Control flow is hardcoded. Fixed prompt hand-offs. Zero dynamic routing.           |
+---------------------------------------------------------------------------------------+

+---------------------------------------------------------------------------------------+
| AUTONOMOUS LLM AGENT                                                                 |
|  User Goal ---> [ LLM Decision Engine ] <---> [ MCP Tool Registry ]                  |
|                        |                             |                                |
|                        v                             v                                |
|               [ Evaluator Loop ] <-------- [ Environment Feedback ]                   |
|  * Control flow is dynamic. Agent decides tool choice, parameters, and retries.       |
+---------------------------------------------------------------------------------------+
```

### The Workflow (Hardcoded Control Flow)
A **workflow** is a deterministic system where the execution path is fixed at build time. Input data flows through pre-programmed steps (e.g., Step A $ightarrow$ Step B $ightarrow$ Step C). While individual steps may utilize LLMs for generation, the overall sequence, branching rules, and hand-offs are hardcoded.

### The Agent (Dynamic LLM Control Loop)
An **agent** is an autonomous system where an LLM functions as the central decision-making engine. Given a high-level goal, the model dynamically determines *which* tools to call, *what* parameters to pass, *how* to evaluate intermediate environment outputs, and *when* to retry or exit. The execution path is not predetermined—it emerges dynamically during execution.

### Classification of Our FL-04 Pipeline
Our **FL-04 pipeline is a Workflow**, NOT an agent.  
- *Why*: The 4-step sequence (NotebookLM Ingestion $ightarrow$ YAML Entity Extraction $ightarrow$ 3-Beats Case Drafting $ightarrow$ GFM Review) is fixed. The system cannot dynamically skip Step 2 or decide on its own to invoke an external web scraper if source data is missing. Control flow remains strictly deterministic.

---

## 2. Model Context Protocol (MCP) Architectural Primitives

The **Model Context Protocol (MCP)** is an open standard—often referred to as the *"USB-C standard for AI applications"*—that standardizes how LLMs interface with external data sources, local filesystems, and execution environments.

MCP defines three foundational primitives:

1. 🛠️ **Tools**: Executable functions exposed by MCP servers that allow an LLM to perform external computations or side-effects (e.g., running terminal commands, querying databases, writing files). Tools take structured arguments and return execution results.
2. 📄 **Resources**: Read-only data sources exposed via URI schemes (e.g., `file:///logs/metrics.json`, `db://production/search_tables`). Resources provide context directly to the model without requiring function calls.
3. 💬 **Prompts**: Pre-defined reusable templates and context shortcuts exposed by MCP servers to standardizing common interaction flows.

---

## 3. Three Working MCP Tasks (Beyond Plain Chat Capabilities)

Plain chat LLMs operate in an isolated sandbox with zero access to your local disk or live external networks. Using an active MCP client setup, three tasks were executed that plain chat alone could never perform:

### Task 1: Local Filesystem Inspection & Log Extraction
- **Capability**: Plain chat cannot read files stored on a local Windows SSD.
- **MCP Tool Invoked**: `view_file` / `grep_search` on `work/outputs/model_metrics.json`.
- **Execution Proof**:
  ```json
  // Invoked tool: view_file(AbsolutePath="c:/Users/.../model_metrics.json")
  {
    "model_name": "RandomForestClassifier",
    "precision_at_50": 0.740,
    "baseline_precision_at_50": 0.340,
    "directional_lift": "2.18x",
    "split_strategy": "GroupShuffleSplit(client_id)"
  }
  ```

### Task 2: Live Deployed Web Service Inspection
- **Capability**: Plain chat cannot fetch or inspect live HTTP deployment endpoints in real-time.
- **MCP Tool Invoked**: `read_url_content` fetching `https://abdulhayykhan.github.io/FlyRank-AI/`.
- **Execution Proof**:
  ```text
  // Invoked tool: read_url_content(Url="https://abdulhayykhan.github.io/FlyRank-AI/")
  HTTP 200 OK | Title: Search Intelligence Capstone Research Paper
  Parsed DOM elements: <h1>, <table id="benchmark-table">, 3D gradient CSS tokens.
  ```

### Task 3: Local Shell Build & Model Verification Execution
- **Capability**: Plain chat cannot execute local Python scripts or check OS exit codes.
- **MCP Tool Invoked**: `run_command` executing `python scratch/execute_capstone.py`.
- **Execution Proof**:
  ```powershell
  # Invoked tool: run_command(CommandLine="python scratch/execute_capstone.py")
  Command Output: Evaluated 79,214,105 rows. Precision@50 = 0.740. Process Exit Code: 0 (SUCCESS).
  ```

---

## 4. Concrete Agentic Upgrade Plan for FL-04

To transform our deterministic FL-04 workflow into a fully **Autonomous Research Agent**, we must replace fixed step hand-offs with an **Evaluator-Optimizer Loop** using MCP execution tools:

```text
+---------------------------------------------------------------------------------------+
| AGENTIC UPGRADE: AUTONOMOUS EVALUATOR-OPTIMIZER LOOP                                   |
|                                                                                       |
|  1. Goal: Achieve >= 0.750 Precision@50 with 0% target leakage.                       |
|  2. Agent Action: Read local capstone.ipynb via view_file.                            |
|  3. Agent Action: Run training script via run_command.                                |
|  4. Evaluation: Inspect model_metrics.json.                                            |
|  5. Decision Branching:                                                                |
|     - IF Precision@50 < 0.750: Agent modifies hyperparams (n_estimators) & retries.|
|     - IF Target Leakage Detected: Agent rewrites feature list & retries.              |
|     - IF Criteria Met: Agent auto-publishes research paper to GitHub Pages.            |
+---------------------------------------------------------------------------------------+
```

### Key Upgrades Required:
- **Autonomous Tool Access**: Grant the agent MCP tools (`run_command`, `replace_file_content`, `git_push`).
- **Dynamic Retry & Self-Correction**: The agent independently diagnoses model validation failures and iterates hyperparameters without human prompting.

---

## 5. Verification Checklist (Pass / Revise Self-Audit)

- [x] **Workflow vs Agent distinction applied**: Accurately defined and correctly classified FL-04 as a deterministic workflow.
- [x] **MCP primitives explained**: Tools, Resources, and Prompts clearly documented.
- [x] **Connector demonstrably working**: Output shows explicit tool calls (`view_file`, `read_url_content`, `run_command`).
- [x] **Three tasks beyond plain chat**: Local disk reading, live HTTP scraping, and OS script execution documented.
- [x] **Concrete agent upgrade named**: Evaluator-Optimizer loop with dynamic hyperparameter tuning proposed.

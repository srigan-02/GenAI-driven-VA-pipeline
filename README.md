**🚀 Automating Vulnerability Assessments with a Sequential Agent Pipeline**

AI-Driven Workflow Automation for Web Application Security

In today’s digital-first environment, web application security is non-negotiable. Organizations spend enormous time and effort managing Vulnerability Assessments (VA) — from proposal acceptance to testing, reporting, analytics, and managerial reviews. Manual workflows are slow, inconsistent, and difficult to scale.

To solve this, I built an Automated VA Pipeline using sequential AI agents.

🧩 Problem Statement

A complete Vulnerability Assessment involves multiple interdependent stages:

- Proposal Acceptance

- Gathering Data Requirements

- Conducting Vulnerability Tests

- Generating Reports

- Performing Analytics

- Managerial Approvals

- Final Review

Each step must be executed carefully and consistently. Traditional manual processes risk:

- Missed steps

- Human error

- Poor standardization

- Inefficiency

Automation improves reliability, repeatability and speed.

**🤖 Why Agents?**

AI Agents are modular autonomous components capable of executing defined tasks.
I mapped each VA step to a dedicated agent:

- Proposal Acceptance Agent – evaluates and approves proposals

- Data Requirement Agent – collects client inputs

- Testing Agent – performs vulnerability scans

- Reporting Agent – generates structured VA reports

- Analytics Agent – interprets results

- Manager Agent – handles approvals

- Review Agent – ensures final quality checks

By chaining these agents sequentially, we get a fully automated, deterministic workflow that can be debugged step-by-step.

**🏗️ What I Created**

I designed a Sequential Root Agent called va_pipeline that orchestrates all sub-agents.

Architecture Overview:

VA_Pipeline (Sequential Root Agent)
├── Proposal Acceptance Agent
├── Data Requirement Agent
├── Testing Agent
├── Reporting Agent
├── Analytics Agent
├── Manager Agent
└── Review Agent

**🔧 Helper Agent**

In addition to the main workflow:

- Validates data

- Fetches metadata

- Logs operations

- Suggests next steps

- Improves error handling

This makes the pipeline extensible, fault-tolerant, and modular.

**🎯 Demo**

Using Google ADK’s InMemoryRunner, I simulated an end-to-end VA workflow.

from google.adk.adapters.runner import InMemoryRunner

# Create runner for the root sequential agent
runner = InMemoryRunner(agent=root_agent)

# Run the pipeline with a prompt
response = await runner.run_debug(
    "Start a Vulnerability Assessment for the client's web application. "
    "Begin with proposal acceptance and follow the sequential workflow."
)

print("\n\n🔥 FINAL PIPELINE OUTPUT 🔥\n")
print(response)


The output clearly shows each step executed in sequence, fully automated.

**🛠️ How I Built It**

Framework:

- Google ADK Agent SDK

- Python

**Core Features:**

- Modular multi-agent architecture

- Sequential execution using SequentialAgent

- Debug-friendly with InMemoryRunner

- Clear separation of responsibilities

- Extensible helper-agent support

- Fully simulated end-to-end pipeline

**🌱 Future Enhancements**

- This system is designed to scale. Planned upgrades include:

- Integrating real scanners (Nmap, Burp, Nessus, OpenVAS)

- Automated evidence collection

- Approval gates and RBAC

- CI/CD integration

- Predictive vulnerability modeling

- Client portal for live tracking

- Comprehensive audit logs

This can evolve into a fully autonomous AI-powered VA/PT orchestration engine.

**📚 License**

This write-up is released under the
Attribution 4.0 International (CC BY 4.0) license.

**📘 Citation**

Sriram G (srigan_02). GenAI Driven VA Pipeline.
Kaggle Write-up, 2025.

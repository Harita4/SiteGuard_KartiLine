# SiteGuard_KartiLine
Overview

SiteGuard is an Agentic AI system that continuously monitors labour compliance, safety certifications, and regulatory deadlines for small and medium construction contractors in India.

Unlike traditional compliance software that only stores records or sends reminders, SiteGuard follows a complete agentic workflow:

**Perceive → Decide → Act → Observe**

The platform proactively identifies compliance risks, prioritizes them, initiates corrective actions, and tracks outcomes to help contractors avoid penalties and maintain regulatory compliance.

Built for the **KartiLine Agentic AI Hackathon**.

---

## Problem Statement

Construction contractors must manage multiple compliance obligations simultaneously, including:

* BOCW Worker Registration
* ESI Contributions
* EPF Contributions
* CLRA License Renewals
* Safety Officer Certifications
* Fire NOCs
* Labour Welfare Filings

Most SMEs rely on spreadsheets, manual tracking, or consultants, leading to missed deadlines and avoidable penalties.

SiteGuard acts as a digital compliance officer that works 24/7.

---

## How SiteGuard Works

### PERCEIVE

Collects information from:

* Contractor profiles
* Site records
* Worker databases
* Uploaded documents
* Government circulars
* WhatsApp submissions

### DECIDE

Uses AI reasoning to:

* Determine regulation applicability
* Assess compliance risk
* Prioritize deadlines
* Recommend actions

### ACT

Automatically:

* Sends WhatsApp alerts
* Generates compliance checklists
* Drafts escalation emails
* Updates dashboards

### OBSERVE

Tracks:

* Completion status
* User responses
* Missed deadlines
* Compliance outcomes

---

## Key Features

### Compliance Dashboard

Real-time view of compliance status across all sites.

### Regulatory Sentinel

Monitors government updates and identifies regulations relevant to each contractor.

### WhatsApp Compliance Assistant

Users can forward notices or certificates directly through WhatsApp.

### Agent Reasoning Log

Every AI decision is recorded with a transparent explanation.

### Escalation Engine

Automatically escalates unresolved compliance risks.

### ROI Tracker

Displays penalties prevented and estimated savings.

---

Tech Stack

| Layer           | Technology                 |
| --------------- | -------------------------- |
| Frontend        | Next.js 14, Tailwind CSS   |
| Backend         | FastAPI (Python)           |
| Database        | PostgreSQL, Supabase       |
| Agent Framework | LangGraph                  |
| LLM             | Gemini 1.5 Flash           |
| OCR             | Google Vision API          |
| Messaging       | Twilio / WATI WhatsApp API |
| Email           | SendGrid                   |
| Scheduling      | APScheduler                |
| Deployment      | Railway / Render           |

---

## System Architecture

User Dashboard / WhatsApp

↓

FastAPI Backend

↓

LangGraph Agent Engine

↓

Gemini Reasoning Layer

↓

PostgreSQL Database

↓

Notification Services

↓

WhatsApp & Email Alerts

---

## Expected Impact

* Reduce compliance-related penalties
* Improve deadline adherence
* Automate regulatory monitoring
* Save administrative effort
* Increase audit readiness

---

## Future Scope

* Regional language support
* Voice-based compliance assistant
* Manufacturing compliance modules
* Logistics and warehousing compliance
* Government API integrations

---

## Why SiteGuard?

Traditional compliance tools remind.

**SiteGuard understands, decides, acts, and learns.**

By implementing a complete Perceive → Decide → Act → Observe cycle, SiteGuard demonstrates a practical and scalable use of Agentic AI for real-world business operations.

---

## Team

KartiLine Agentic AI Hackathon Submission

SiteGuard – Autonomous Compliance Intelligence for Construction SMEs

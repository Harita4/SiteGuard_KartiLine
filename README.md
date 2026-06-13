# SiteGuard_KartiLine
SiteGuard autonomously monitors labour compliance for SME construction contractors across India. It perceives deadlines, decides risk priority, acts via WhatsApp alerts and document checklists, and observes completion outcomes — eliminating ₹80,000+ in annual penalties through a genuine agentic loop.
SiteGuard is an agentic AI system that continuously monitors labour compliance, safety certificate status, and regulatory deadlines for small and medium construction contractors in India. It follows a strict Perceive → Decide → Act → Observe loop — it does not just remind, it acts.

Built for the KartiLine Agentic AI Hackathon.

The Problem
A construction contractor operating 3–7 sites with 60–180 daily workers faces between 14 and 23 distinct compliance obligations simultaneously — BOCW worker registrations, ESI/PF contributions, CLRA licence renewals, safety officer certificates, fire NOCs, and pollution board filings.

The average SME contractor pays ₹80,000+ in avoidable penalties per year because nobody is watching all of it at once.

SiteGuard watches all of it. Autonomously.

How the Agent Works
PERCEIVE → DECIDE → ACT → OBSERVE → REPEAT
Phase	What Happens
PERCEIVE	Reads contractor profile, worker records, compliance calendar, government portal updates, and WhatsApp-forwarded documents
DECIDE	LLM reasons over compliance rulebook to score urgency, classify regulatory updates as applicable or not, and select action strategy
ACT	Sends WhatsApp alerts, generates document checklists, drafts CA escalation emails, updates compliance dashboard
OBSERVE	Tracks completion confirmations, detects missed deadlines, parses penalty notices, adapts future urgency scoring
Features
Compliance Dashboard — live heatmap across all sites; items move green → amber → red as deadlines approach
Regulatory Sentinel — monitors government portals every 24 hours; classifies new circulars as applicable or not to each contractor profile
WhatsApp Intake — contractor forwards a notice photo; agent parses it via OCR, links it to the compliance record, updates dashboard within 20 seconds
Agent Reasoning Log — every decision explained in plain English; full audit trail
ROI Module — shows penalties prevented, penalty exposure remaining, subscription cost
Escalation Chain — missed deadline → supervisor alert → CA escalation email draft (one-tap approval before sending)
Tech Stack
Layer	Technology
Frontend	Next.js 14 + Tailwind CSS
Backend	FastAPI (Python)
Database	PostgreSQL via Supabase
Agent Framework	LangGraph
LLM	Gemini 1.5 Flash
WhatsApp	WATI / Twilio WhatsApp API
OCR	Google Vision API
Scheduling	APScheduler
Notifications	WATI (WhatsApp) + SendGrid (email)
Deployment	Railway / Rende
Database Schema (Core Tables)
contractors          — company profile, state, licence numbers
sites                — per-site metadata linked to contractor
workers              — worker register, certificate expiry dates
compliance_items     — each obligation with deadline + status
documents            — uploaded files with OCR output
regulation_updates   — scraped government portal changes
reasoning_logs       — every agent decision with full reasoning text
notification_events  — all outbound alerts + delivery status
Getting Started
Prerequisites
Python 3.11+
Node.js 18+
PostgreSQL (or Supabase project)
WATI sandbox account (apply before anything else — takes 24–48 hours)
Google AI Studio API key (Gemini)
Google Cloud project with Vision API enabled
1. Clone and configure
bash
git clone https://github.com/your-org/siteguard.git
cd siteguard
cp .env.example .env
# Fill in all values in .env before proceeding
2. Backend setup
bash
cd backend
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt

# Run database migrations
psql $DATABASE_URL < db/migrations/001_initial_schema.sql

# Start the API
uvicorn main:app --reload --port 8000
3. Frontend setup
bash
cd frontend
npm install
npm run dev                     # Runs on http://localhost:3000
4. Seed demo data
bash
cd backend
python -m scripts.seed_demo     # Loads Rajesh Constructions demo profile
5. Register WhatsApp webhook
Point your WATI webhook URL to:

https://your-deployment-url/api/webhooks/whatsapp
Environment Variables
env
# Database
DATABASE_URL=postgresql://user:password@host:5432/siteguard
SUPABASE_URL=
SUPABASE_ANON_KEY=

# LLM
GEMINI_API_KEY=

# WhatsApp
WATI_API_KEY=
WATI_PHONE_NUMBER=

# Notifications
SENDGRID_API_KEY=
FROM_EMAIL=alerts@siteguard.ai

# OCR
GOOGLE_VISION_API_KEY=

# App
SECRET_KEY=
ENVIRONMENT=development
The Demo (8-Minute Walkthrough)
The full demo script is in docs/demo_script.md. Key moments:

Compliance heatmap — 4 sites live, one red (BOCW lapse detected 48 hours ago)
Regulatory Sentinel trigger — new MoLE circular detected, classified as applicable, surfaced as action item in real time while judges watch
WhatsApp document intake — photograph a compliance notice on your phone, forward to SiteGuard WhatsApp number, watch it appear in the dashboard parsed and linked within 20 seconds
OBSERVE loop close — mark the lapse resolved, site flips red → green, reasoning log updated
ROI module — penalties prevented this quarter ₹1.1 lakh vs subscription ₹299/month
Compliance Coverage (MVP — 2 States)
Obligation	Applicability	Deadline Cadence
BOCW Worker Registration	All construction workers	Per worker, once
BOCW Levy Payment	Contractors > ₹10L contract value	Per project
ESI Contribution	Workers earning < ₹21,000/month	Monthly by 15th
EPF Contribution	Establishments with 20+ workers	Monthly by 15th
CLRA Contractor Licence	Principal employer + contractors	Annual renewal
Safety Officer Certificate	Sites with 500+ workers	Annual renewal
CLRA Form XIII (Muster Roll)	All contract labour sites	Maintained daily
Contributing
This project was built for the KartiLine Agentic AI Hackathon. After the hackathon, contributions are welcome for:

Additional state-specific compliance rulesets
New industry verticals (manufacturing, logistics)
Government portal scraper maintenance
WhatsApp conversation flow improvements
License
MIT License. See LICENSE for details.

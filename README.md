CarbonWise AI --- Measure → Optimize → Prove Sustainable AI
International hAIckathon 2025 Submission

CarbonWise AI was selected as the winner of the "Best Project Built with
ElevenLabs" prize at the International hAIckathon 2025. The project also
placed 6th overall out of more than 200 teams.

Theme: Reduced Inequalities & Climate Action

Overview CarbonWise AI is a lightweight system designed to make AI
sustainability measurable, actionable, and transparent. It includes a
Python SDK for tracking the energy and carbon footprint of AI workloads
and a React dashboard for visualizing improvements, identifying greener
compute regions, and exporting evidence of impact.

Why It Was Built AI workloads are increasingly energy-intensive, yet
most teams lack visibility into their carbon impact. CarbonWise AI makes
sustainability a measurable engineering metric, helping teams understand
and improve the environmental efficiency of their models.

Core Functions 1. Measure: A Python decorator to log runtime, energy
use, emissions, and SCI. 2. Optimize: Compare experimental variations
and evaluate efficiency gains. 3. Prove: Visualize performance changes
and export a PDF summary. 4. Advise: Recommend cloud regions using open
ASDI data. 5. Extend: Integrations with Hathora and ElevenLabs.

Technology Overview - Measurement: Python 3, CodeCarbon - Dashboard:
React + TypeScript (Lovable, Vite, Tailwind, Recharts) - Data Source:
ASDI (Amazon Sustainability Data Initiative) - Cloud Integration:
Hathora - Voice Narration: ElevenLabs API - Reporting: HTML-to-PDF -
Hosting: GitHub Pages, Vercel

Project Structure Backend (Python) - tracker.py: Core SDK -
examples_baseline.py / examples_optimized.py: Demo runs -
examples_hathora_client.py: Cloud inference example -
examples_eleven_tts.py: Voice summary generation - cw_report.py: Report
generation - region_advisor.py: Greener region recommendations -
requirements.txt: Dependencies - run_log.jsonl: Output log

Frontend (React) - Upload run logs - Compare energy, emissions, and
latency - Region Advisor insights - PDF report generation

Getting Started Dashboard: npm install npm run dev

Sample Data: Upload backend/sample_run_log.jsonl

Generate Logs: python examples_baseline.py python examples_optimized.py

Add‑Ons Hathora Cloud Integration: python
backend/examples_hathora_client.py

ElevenLabs Narration: python backend/examples_eleven_tts.py

SCI Metric SCI (Wh/request) = (energy_kwh × 1000) / max(requests, 1)

Architecture The system combines the Python SDK, run logs, a React
dashboard, ASDI data, and optional cloud or voice integrations.

Closing Thoughts CarbonWise AI demonstrates that AI sustainability
tracking can be simple, transparent, and measurable. The goal is to help
teams make informed, responsible engineering decisions.

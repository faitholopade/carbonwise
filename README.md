# CarbonWise AI --- Measure → Optimize → Prove Sustainable AI

### International hAIckathon 2025 Submission: https://www.global-haickathon.com/

CarbonWise AI was selected as the winner of the **Best Project Built
with ElevenLabs** prize at the International hAIckathon 2025. 
It also placed **6th overall** out of more than 200 global teams.

**Theme:** Reduced Inequalities & Climate Action

------------------------------------------------------------------------

## Overview

**CarbonWise AI** is a lightweight system designed to make AI
sustainability **measurable, actionable, and transparent**. 
It includes:

-   A **Python SDK** for tracking energy use, runtime, and carbon
    emissions 
-   A **React dashboard** for visualizing improvements, comparing runs,
    selecting greener regions, and exporting reports

------------------------------------------------------------------------

## Purpose

AI systems are increasingly energy-intensive, and most teams lack
visibility into their environmental impact.
CarbonWise AI reframes sustainability as an engineering metric, similar
to latency or accuracy.

------------------------------------------------------------------------

## Core Capabilities

### 1. Measure

The `@track` decorator logs: - Runtime
- Energy (kWh)
- CO₂e emissions
- Software Carbon Intensity (SCI)

### 2. Optimize

Run and compare variations such as: - Quantization
- Batching
- Alternative decoding strategies

### 3. Prove

Visualize before/after performance and export a **PDF report** that
summarises improvements.

### 4. Advise

Uses ASDI (Amazon Sustainability Data Initiative) to recommend cloud
regions with lower carbon intensity.

### 5. Extend

Hackathon integrations: - Hathora for cloud inference
- ElevenLabs for spoken sustainability summaries

------------------------------------------------------------------------

## Technology Stack

  Layer               Tools
  ------------------- ---------------------------------------------
  Measurement         Python 3, CodeCarbon
  Dashboard           Lovable
  Data Source         ASDI
  Cloud Integration   Hathora
  Voice Narration     ElevenLabs API
  Reporting           HTML-to-PDF
  Hosting             GitHub Pages, Vercel

------------------------------------------------------------------------

## Project Structure

### Backend (Python)

-   `tracker.py` --- Core SDK
-   `examples_baseline.py` & `examples_optimized.py` --- Example
    workload runs
-   `examples_hathora_client.py` --- Cloud inference example
-   `examples_eleven_tts.py` --- Voice summary generation
-   `cw_report.py` --- PDF + Markdown report generation
-   `region_advisor.py` --- Cloud region recommendations
-   `run_log.jsonl` --- Generated metrics log

### Frontend (React)

-   Upload metric logs
-   Compare energy, emissions, and latency
-   ASDI-based region recommendations
-   Exportable PDF summary

------------------------------------------------------------------------

## Getting Started

### Run the Dashboard

``` bash
npm install
npm run dev
```

### Load Sample Data

Upload:\
`backend/sample_run_log.jsonl`

### Generate New Logs

``` bash
cd backend
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt

python examples_baseline.py
python examples_optimized.py
```

------------------------------------------------------------------------

## Optional Extensions

### Hathora Cloud Integration

``` bash
python backend/examples_hathora_client.py
```

### ElevenLabs Voice Narration

``` bash
python backend/examples_eleven_tts.py
```

------------------------------------------------------------------------

## Software Carbon Intensity (SCI)

Formula:

    SCI (Wh per request) = (energy_kwh × 1000) / max(requests, 1)

Example log entry:

``` json
{
  "run_id": "uuid",
  "run_name": "optimized",
  "energy_kwh": 0.58,
  "co2e_kg": 0.27,
  "latency_ms": 710,
  "sci_wh_per_req": 580.0,
  "meta": {"precision":"int4","region":"europe-west9"}
}
```

------------------------------------------------------------------------

## Architecture

``` mermaid
flowchart TD
  A[User AI Code] --> B[CarbonWise SDK]
  B --> C[run_log.jsonl]
  C --> D[Dashboard]
  D --> E[Compare View]
  D --> F[Region Advisor]
  D --> G[Report Export]
  F --> H[ASDI Data]
  G --> I[PDF Report]
  A --> J[Hathora Cloud Models]
  J --> B
  G --> K[ElevenLabs Voice Summary]
```

------------------------------------------------------------------------

## Closing Notes

CarbonWise AI demonstrates that sustainable AI does not require heavy
infrastructure.

By making energy and emissions measurable, teams can make informed
engineering decisions and reduce environmental impact.

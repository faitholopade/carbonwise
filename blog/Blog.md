# 🌿 CarbonWise AI — Making AI Sustainability Visible

---

### 🎬 [Intro video placeholder]
*(Insert your opening clip here — quick overview or title animation)*

---

## 🧭 Introduction

Hi, I’m **Faith**, and this is **CarbonWise AI** — a project I built for the International hAIckathon 2025.

AI systems today are astonishingly capable, but they’re also astonishingly energy-hungry.  
Most developers can tell you their model’s accuracy or latency, but not its carbon footprint.

CarbonWise AI changes that.

It’s a **lightweight SDK and web dashboard** that helps teams **measure**, **optimize**, and **prove** the sustainability of their AI workloads — using open data, measurable metrics, and a focus on developer usability.

---

## 💡 The Problem

As models scale, their energy and carbon costs become invisible but significant.  
Without visibility, optimization doesn’t happen — and sustainability becomes a guessing game.  
Large companies can afford complex tracking tools, but most researchers, students, and small teams can’t.

---

## 🌍 The Solution

**CarbonWise AI** makes AI sustainability measurable and accessible.  
It does four things really well:

1. **Measure:** A Python decorator (`@track`) automatically logs energy (kWh), CO₂e, latency, and Software Carbon Intensity (SCI) for any AI run.  
2. **Optimize:** You can compare a “baseline” and an “optimized” configuration side-by-side to see the actual efficiency gains.  
3. **Advise:** A Region Advisor powered by **ASDI (Amazon Sustainability Data Initiative)** suggests greener cloud regions or time windows.  
4. **Prove:** You can export one-click PDF or audio reports — simple, visual proof of measurable improvement.

Everything runs locally, with optional integrations for **Hathora** (cloud inference) and **ElevenLabs** (voice summaries).

---

### 🎥 [Problem & Solution video placeholder]
*(Insert short clip summarizing the problem and showing the dashboard intro screen)*

---

## ⚙️ Showing the System in Action

### Step 1 — Running the Baseline and Optimized Scripts

To start, I run two scripts that simulate AI workloads:  
`examples_baseline.py` and `examples_optimized.py`.  
The baseline represents a typical unoptimized model, while the optimized version applies simulated efficiency techniques like quantization and speculative decoding.

These runs generate a single log file, `run_log.jsonl`, containing energy use, CO₂e, latency, and SCI metrics.

Each line in the file represents a recorded experiment.

---

### 🎥 [Baseline and Optimized scripts demo placeholder]
*(Insert screen recording of both scripts running and the terminal output)*

---

### Step 2 — Uploading and Comparing Results

Next, I open the **CarbonWise dashboard**, go to the **Upload** tab, and import `run_log.jsonl`.

The **Compare** view automatically displays side-by-side charts showing:
- Lower energy consumption  
- Reduced CO₂e  
- Shorter latency  
- And a noticeably lower SCI score

You can instantly see that the optimized configuration uses less energy per request — tangible proof that optimization efforts pay off.

---

### 🎥 [Dashboard comparison placeholder]
*(Show screen recording: upload log → charts update → SCI drop visible)*

---

## ☁️ Step 3 — Integrating Hathora (Cloud Models)

To demonstrate portability, I ran a batch of inference requests using **Hathora**, a cloud platform for low-latency AI deployments.

By wrapping those API calls with the same `@track` decorator, CarbonWise logs energy use and latency for cloud inference, right alongside local runs.

When I upload the new log file, the dashboard shows the additional “Hathora” run in the same comparison — demonstrating consistent, cross-environment tracking.

---

### 🎥 [Hathora run + new comparison placeholder]
*(Show console running Hathora script → upload new JSONL → dashboard comparison with three runs)*

---

## 🔊 Step 4 — Adding ElevenLabs Voice Narration

Finally, I wanted to make sustainability data more engaging and accessible.  
So I integrated **ElevenLabs** to generate a short spoken summary of the results — an audio version of the PDF report.

Running the ElevenLabs script produces an MP3 file, `carbonwise_summary.mp3`, which reads out the key findings.

---

### 🎥 [ElevenLabs run placeholder]
*(Show ElevenLabs script generating the MP3 and playback UI in the dashboard)*

---

### 🔉 [Audio playback placeholder]
*(Embed or link your audio file here — 5-10 seconds of playback)*

> “Baseline energy was 0.39 kilowatt-hours, optimized energy was 0.24 kilowatt-hours — a 38% reduction. Region Advisor recommends Paris as a 70% cleaner alternative.”

---

## 🧠 What’s Under the Hood

| Component | Role |
|------------|------|
| **Python SDK (`tracker.py`)** | Logs runtime, energy, CO₂e, latency, SCI |
| **React Dashboard** | Visualizes baseline vs optimized runs |
| **ASDI Data** | Supplies grid carbon intensity values for region comparison |
| **Report Engine** | Exports metrics to PDF |
| **Hathora Integration** | Tracks cloud inference workloads |
| **ElevenLabs Integration** | Generates AI-powered voice reports |

---

## 🧱 Architecture Overview

```mermaid
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

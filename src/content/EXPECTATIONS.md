# CarbonWise AI — Expectations (Hackathon)

**Problem**: Teams lack actionable, standardized feedback to reduce AI workload emissions.

**Solution**: CarbonWise AI — a lightweight SDK (Python) + React dashboard (Lovable) that measures energy/CO₂e (CodeCarbon), computes SCI, and recommends optimizations (quantization, speculative decoding, token caps) with a Region Advisor powered by ASDI.

**Scope (this weekend)**:
1) Python tracker producing `run_log.jsonl`
2) React dashboard: Compare view (kWh, CO₂e, latency), SCI, Region Advisor (ASDI), Report export (PDF), Simulate Mode
3) Public repo + 90s video

**Success criteria**:
- ≥30% reduction in kWh/CO₂e on demo (baseline vs optimized)
- <10 lines to instrument a function
- Clear SCI explanation + region suggestions
- Public GitHub + blog

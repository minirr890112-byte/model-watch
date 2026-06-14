---
name: model-watch
description: Benchmark AI API models over time and detect intelligence degradation. 7 standardized tests (Reasoning/Coding/Writing/Instruction/Hallucination), score history tracking, and automatic alerts when scores drop >10%.
version: 1.2.0
author: minirr890112-byte
license: MIT
metadata:
  hermes:
    tags: [AI, Benchmark, Monitoring, Degradation, LLM, Quality, Developer-Tools]
    homepage: https://github.com/minirr890112-byte/model-watch
---

# model-watch

## Problem → Solution

**The problem**: You're using an AI API for your product. One day, the responses feel off. Weaker reasoning. More hallucinations. Shorter code. Is it real or confirmation bias? You have no baseline to compare against. Your users notice before you do.

**The solution**: 7 standardized benchmark questions run against your model. Scores are stored locally and tracked over time. When recent scores drop more than 10% below historical average, you get an alert. Data-driven degradation detection — no more guessing.

## Quick Start

```bash
pip install git+https://github.com/minirr890112-byte/model-watch.git

model-watch demo              # View benchmark questions
model-watch submit '{"reasoning_1":"...", "coding_1":"..."}'
model-watch history           # Score trend over time
model-watch alert             # Check for degradation
```

## Real Output

```
$ model-watch history

📊 model-watch Score History
──────────────────────────────────
2026-05-01  92/100 █████████░ ✅
2026-05-08  89/100 ████████░░ ✅
2026-05-15  85/100 ████████░░ ⚠️
2026-05-22  78/100 ███████░░░ 🚨 DEGRADED

$ model-watch alert
🚨 DEGRADATION ALERT
   Model: gpt-4.1
   Current avg: 78/100
   Historical avg: 89/100
   Drop: 12.4% (>10% threshold)
   Recommendation: Switch to backup model
```

## 7 Benchmark Tests

| # | Category | Tests | Weight |
|---|----------|-------|--------|
| 1-2 | Reasoning | Logic puzzle, multi-step deduction | 2.0x |
| 3-4 | Coding | Algorithm, system design | 2.0x |
| 5 | Writing | Creative prose quality | 1.0x |
| 6 | Instruction | Following complex directions | 1.5x |
| 7 | Hallucination | Factual accuracy check | 2.5x |

---
⭐ **Star this repo if you want to know when your AI gets dumber**: [github.com/minirr890112-byte/model-watch](https://github.com/minirr890112-byte/model-watch)

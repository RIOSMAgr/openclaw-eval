# OpenClaw Free-Tier Model Evaluation

**Comprehensive benchmark of OpenRouter free-tier LLMs for practical applications**

[![GitHub](https://img.shields.io/badge/GitHub-bejranonda%2Fopenclaw--eval-blue?logo=github)](https://github.com/bejranonda/openclaw-eval)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![Models](https://img.shields.io/badge/Models-8_tested,_6_working-green)]()
[![Activities](https://img.shields.io/badge/Activities-11-green)]()

Last Updated: February 24, 2026

---

## Executive Summary

We evaluated **8 free-tier models** on OpenRouter across **11 practical activities** (2 models were discontinued during testing: DeepSeek R1, OpenRouter Free). Here are the results for the 6 working models.

### Key Findings

| Rank | Model | Score | Pass Rate | Speed | Best For |
|:----:|-------|:-----:|:---------:|:-----:|----------|
| 1 | **Nemotron 30B** | **8.60** | 10/11 | 0.5s | Overall best - fast, consistent, excellent all-rounder |
| 2 | **Step 3.5 Flash** | **8.57** | 11/11 | 2.9s | 100% reliability, best Thai support |
| 3 | **Trinity Mini** | **8.49** | 10/11 | 0.5s | Fastest, excellent coding & translation |
| 4 | Gemma 3 27B | 8.44 | 9/11 | 1.1s | Great translation & Thai writing |
| 5 | Nemotron VL 12B | 8.41 | 7/11 | 0.5s | Vision-capable, fast |
| 6 | Gemma 3 12B | 8.40 | 10/11 | 4.4s | Solid all-rounder, slower |

> ⚠️ **Discontinued Models:** DeepSeek R1 and OpenRouter Free were also tested but returned 404 errors (no longer available on free tier).

### Quick Recommendations

- **General Purpose:** Nemotron 30B (best balance of speed and quality)
- **Thai Language:** Step 3.5 Flash (best Thai support and reliability)
- **Coding Tasks:** Trinity Mini or Nemotron 30B (both score 9.0)
- **Speed-Critical:** Trinity Mini or Nemotron 30B (both ~0.5s response)
- **100% Reliability:** Step 3.5 Flash (only model passing all 11 tests)

---

## 🇹🇭 สรุปภาษาไทย

### OpenClaw คืออะไร?

**OpenClaw** เป็นโปรเจกต์ AI Gateway ส่วนบุคคลที่พัฒนาเพื่อทดสอบและเปรียบเทียบประสิทธิภาพของ Large Language Models (LLMs) บนแพลตฟอร์ม OpenRouter โดยเฉพาะ **Free-tier models** ที่ใช้งานได้ฟรี

### ผลการทดสอบโดยสรุป

เราทดสอบ **8 โมเดล** บน OpenRouter ฟรี ผ่าน **11 กิจกรรม** (2 โมเดล discontinued ระหว่างการทดสอบ) เพื่อหาโมเดลที่เหมาะกับแอปพลิเคชันของคุณ

| อันดับ | โมเดล | คะแนน | ความเร็ว | เหมาะสำหรับ |
|:------:|-------|:-----:|:--------:|-------------|
| 🥇 | **Nemotron 30B** | **8.60** | 0.5 วินาที | ใช้ทั่วไป ดีที่สุดแบบครบวงจร |
| 🥈 | **Step 3.5 Flash** | **8.57** | 2.9 วินาที | ภาษาไทย เสถียรที่สุด 100% |
| 🥉 | **Trinity Mini** | **8.49** | 0.5 วินาที | เร็วที่สุด เขียนโค้ด/แปลดีมาก |
| 4 | Gemma 3 27B | 8.44 | 1.1 วินาที | แปลภาษา เขียนไทยดี |
| 5 | Nemotron VL 12B | 8.41 | 0.5 วินาที | รองรับ Vision (รูปภาพ) |
| 6 | Gemma 3 12B | 8.40 | 4.4 วินาที | ใช้ได้ดี แต่ช้าที่สุด |

### แนะนำตามการใช้งาน

| การใช้งาน | โมเดลที่แนะนำ | เหตุผล |
|-----------|----------------|--------|
| **Chatbot ทั่วไป** | Nemotron 30B | ดีที่สุดโดยรวม ตอบเร็ว |
| **แอปภาษาไทย** | Step 3.5 Flash | รองรับภาษาไทยดีที่สุด เสถียร 100% |
| **Coding Assistant** | Trinity Mini | เร็วที่สุด เขียนโค้ดได้ดีมาก (9.0) |
| **ต้องการความเร็ว** | Trinity Mini / Nemotron 30B | ตอบใน 0.5 วินาที |
| **Production** | Step 3.5 Flash | ผ่านการทดสอบ 11/11 (100%) |

### ภาษาไทย

| โมเดล | สรุปข้อความ | เขียนสร้างสรรค์ | ทำตามคำสั่ง | เฉลี่ยไทย |
|-------|:-----------:|:--------------:|:-----------:|:---------:|
| **Step 3.5 Flash** | 7.60 | **8.50** | 8.80 | **8.30** |
| **Gemma 3 27B** | 7.60 | **8.50** | 8.80 | **8.30** |
| Nemotron 30B | 7.60 | ERR | 8.80 | 8.20 |
| Nemotron VL 12B | 6.90 | 8.30 | 8.80 | 8.00 |
| Gemma 3 12B | 7.10 | 8.10 | 8.60 | 7.93 |
| Trinity Mini | 6.35 | 7.90 | 8.80 | 7.68 |

> 💡 **สรุป:** ถ้าต้องการใช้งานภาษาไทย แนะนำ **Step 3.5 Flash** หรือ **Gemma 3 27B**

### วิธีการทดสอบ

- **ทดสอบผ่าน:** OpenRouter API (Free-tier)
- **กิจกรรม:** 11 กิจกรรม (อ่านเอกสาร, เขียนรายงาน, วิเคราะห์การเงิน, เขียนโค้ด, แปลภาษา, เขียนสร้างสรรค์, ภาษาไทย 3 กิจกรรม)
- **คะแนนเต็ม:** 10 (คำนวณจาก Accuracy 30%, Completeness 25%, Coherence 20%, Relevance 15%, Speed 10%)
- **ข้อมูลเพิ่มเติม:** [รายงานฉบับเต็ม](reports/2026-02-24-evaluation.md) | [ข้อมูลดิบ CSV](data/scoresheet.csv)

---

## Benchmark Results

### Overall Performance

```
Score Distribution (out of 10)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Nemotron 30B     ████████████████████░░  8.60
Step 3.5 Flash   ████████████████████░░  8.57
Trinity Mini     ███████████████████░░░  8.49
Gemma 3 27B      ███████████████████░░░  8.44
Nemotron VL 12B  ███████████████████░░░  8.41
Gemma 3 12B      ███████████████████░░░  8.40
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

### Activity-by-Activity Winners

| Activity | Winner | Score | Runner-Up | Score |
|----------|--------|:-----:|-----------|:-----:|
| Document Reading | Trinity Mini | 8.55 | Nemotron VL 12B | 8.15 |
| Document Writing | Trinity Mini | 9.00 | Step 3.5 Flash | 9.00 |
| Financial Analysis | Trinity Mini | 9.00 | Step 3.5 Flash | 9.00 |
| Text Analysis | Step 3.5 Flash | 8.75 | Nemotron VL 12B | 8.75 |
| Code Generation | Trinity Mini | 9.00 | Step 3.5 Flash | 9.00 |
| Translation (EN↔TH) | Trinity Mini | 9.00 | Gemma 3 27B | 8.80 |
| Creative Writing | Trinity Mini | 8.75 | Step 3.5 Flash | 8.75 |
| Instruction Following | Trinity Mini | 8.55 | Step 3.5 Flash | 8.55 |
| Thai Summarization | Step 3.5 Flash | 7.60 | Nemotron 30B | 7.60 |
| Thai Creative Writing | Step 3.5 Flash | 8.50 | Gemma 3 27B | 8.50 |
| Thai Instruction | Trinity Mini | 8.80 | Step 3.5 Flash | 8.80 |

---

## Methodology

### Evaluation Framework

Our evaluation uses a weighted scoring system designed for practical applications:

| Metric | Weight | Description |
|--------|:------:|-------------|
| **Accuracy** | 30% | Factual correctness, no hallucinations |
| **Completeness** | 25% | All requirements addressed |
| **Coherence** | 20% | Logical structure, readability |
| **Relevance** | 15% | Staying on-topic, no tangents |
| **Speed** | 10% | Response time (<5s = 10 points) |

### Test Conditions

- **API:** OpenRouter Chat Completions (text-only)
- **Temperature:** 0.3 (deterministic outputs)
- **Max Tokens:** 2048
- **Timeout:** 120 seconds
- **Rate Limiting:** 8-second delays between requests

### Test Activities

We designed 11 activities covering common LLM use cases:

| Category | Activities |
|----------|------------|
| **Document Processing** | Reading (summarization), Writing (business reports) |
| **Analysis** | Financial data, Text sentiment |
| **Code** | Algorithm implementation |
| **Language** | Translation (EN↔TH) |
| **Creative** | Story writing |
| **Compliance** | Instruction following |
| **Thai-Specific** | Summarization, Creative writing, Instruction following |

---

## Detailed Results

### Document Reading (Summarization)

| Model | Score | Time | Summary Quality |
|-------|:-----:|:----:|-----------------|
| Trinity Mini | 8.55 | 0.6s | Concise, accurate 2-sentence summary |
| Nemotron VL 12B | 8.15 | 0.7s | Good coverage of key elements |
| Nemotron 30B | 8.15 | 0.6s | Clear, captures main events |
| Gemma 3 27B | 8.15 | 1.4s | Accurate, well-structured |
| Gemma 3 12B | 8.15 | 3.6s | Complete but slower |
| Step 3.5 Flash | 7.95 | 6.5s | Good but verbose |

### Document Writing (Business Report)

| Model | Score | Time | Report Quality |
|-------|:-----:|:----:|----------------|
| Trinity Mini | 9.00 | 0.5s | Professional, well-structured |
| Step 3.5 Flash | 9.00 | 0.8s | Executive-ready format |
| Gemma 3 27B | 9.00 | 1.2s | Clear metrics and recommendations |
| Nemotron 30B | 9.00 | 0.6s | Polished business tone |
| Gemma 3 12B | 9.00 | 3.2s | Complete but slower |

### Financial Analysis

| Model | Score | Time | Analysis Quality |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 9.00 | 0.5s | Accurate calculations, clear insights |
| Step 3.5 Flash | 9.00 | 1.3s | Structured analysis with recommendations |
| Gemma 3 27B | 9.00 | 1.8s | Detailed breakdown |
| Nemotron 30B | 9.00 | 0.5s | Fast, accurate profit margin |
| Nemotron VL 12B | 9.00 | 1.8s | Complete quarterly analysis |

### Code Generation

| Model | Score | Time | Code Quality |
|-------|:-----:|:----:|--------------|
| Trinity Mini | 9.00 | 0.7s | Clean, typed, documented |
| Step 3.5 Flash | 9.00 | 2.9s | Complete with docstring |
| Nemotron 30B | 9.00 | 0.5s | Concise, well-typed |
| Gemma 3 12B | 9.00 | 3.4s | Full implementation |
| Nemotron VL 12B | 9.00 | 0.6s | Working solution |

### Translation (English ↔ Thai)

| Model | Score | Time | Translation Quality |
|-------|:-----:|:----:|---------------------|
| Trinity Mini | 9.00 | 0.4s | Natural, accurate both directions |
| Gemma 3 27B | 8.80 | 1.1s | Good nuance preservation |
| Nemotron 30B | 8.60 | 0.5s | Accurate, slight formality |
| Gemma 3 12B | 8.60 | 3.5s | Correct but slower |
| Step 3.5 Flash | 8.40 | 4.2s | Accurate, some awkward phrasing |

### Thai Language Tasks

| Model | Summarization | Creative Writing | Instructions | Thai Avg |
|-------|:-------------:|:----------------:|:------------:|:--------:|
| Step 3.5 Flash | 7.60 | 8.50 | 8.80 | **8.30** |
| Gemma 3 27B | 7.60 | 8.50 | 8.80 | **8.30** |
| Nemotron 30B | 7.60 | ERR | 8.80 | **8.20** |
| Nemotron VL 12B | 6.90 | 8.30 | 8.80 | **8.00** |
| Gemma 3 12B | 7.10 | 8.10 | 8.60 | **7.93** |
| Trinity Mini | 6.35 | 7.90 | 8.80 | **7.68** |

---

## Speed Comparison

```
Average Response Time
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Trinity Mini     ▏ 0.5s ████████████████████ FASTEST
Nemotron 30B     ▏ 0.5s ████████████████████
Nemotron VL 12B  ▏ 0.7s ███████████████████░
Gemma 3 27B      ▏ 1.1s ██████████████████░░
Step 3.5 Flash   ▏ 2.9s ████████████████░░░░
Gemma 3 12B      ▏ 4.4s █████████████░░░░░░░ SLOWEST
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```

---

## Reliability Analysis

| Model | Tests Passed | Failure Rate | Notable Failures |
|-------|:------------:|:------------:|------------------|
| Step 3.5 Flash | 11/11 (100%) | 0% | None - most reliable |
| Nemotron 30B | 10/11 (91%) | 9% | Thai Creative Writing |
| Trinity Mini | 10/11 (91%) | 9% | Text Analysis |
| Gemma 3 12B | 10/11 (91%) | 9% | Financial Analysis |
| Gemma 3 27B | 9/11 (82%) | 18% | Text Analysis, Code Gen |
| Nemotron VL 12B | 7/11 (64%) | 36% | Writing, Translation, Creative, Instructions |

---

## Conclusions

### Best Overall: Nemotron 30B
- Highest average score (8.60)
- Excellent speed (0.5s average)
- Strong across all categories
- Minor gap in Thai creative writing

### Most Reliable: Step 3.5 Flash
- Only model with 100% pass rate
- Best Thai language support
- Slightly slower (2.9s) but consistent
- Ideal for production workloads

### Best Value for Speed: Trinity Mini
- Tied for fastest (0.5s)
- Excellent coding and translation
- Best for English-centric tasks
- Thai summarization needs improvement

### Thai Language: Step 3.5 Flash or Gemma 3 27B
- Both excel at Thai creative writing (8.50)
- Strong instruction following (8.80)
- Better Thai summarization than others

---

## Repository Contents

```
openclaw-eval/
├── README.md                    # This file
├── reports/
│   └── 2026-02-24-evaluation.md # Full detailed report
├── data/
│   └── scoresheet.csv           # Raw scores data
└── methodology/
    └── rubric.md                # Evaluation criteria
```

---

## Citation

If you use this evaluation in your work, please cite:

```bibtex
@misc{openclaw-eval2026,
  title={OpenClaw Free-Tier Model Evaluation},
  author={OpenClaw Project},
  year={2026},
  url={https://github.com/bejranonda/openclaw-eval}
}
```

---

## License

This evaluation data is released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).

---

*Generated by OpenClaw Auto-Evaluator v2*

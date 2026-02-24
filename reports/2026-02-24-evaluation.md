# OpenRouter Free-Tier Model Evaluation Report

**Date:** February 24, 2026
**Evaluator:** OpenClaw Auto-Evaluator v2
**Models Evaluated:** 6 | **Activities:** 11

---

## Table of Contents

1. [Executive Summary](#executive-summary)
2. [Introduction](#introduction)
3. [Methodology](#methodology)
4. [Detailed Results](#detailed-results)
5. [Analysis by Category](#analysis-by-category)
6. [Recommendations](#recommendations)
7. [Appendix: Response Samples](#appendix-response-samples)

---

## Executive Summary

This report presents a comprehensive evaluation of six free-tier models available on OpenRouter, tested across eleven practical activities to determine their suitability for real-world applications.

### Key Findings

| Rank | Model | Avg Score | Pass Rate | Avg Time | Recommendation |
|:----:|-------|:---------:|:---------:|:--------:|----------------|
| 1 | Nemotron 30B | 8.60 | 10/11 | 0.5s | Best overall performance |
| 2 | Step 3.5 Flash | 8.57 | 11/11 | 2.9s | Most reliable, best Thai |
| 3 | Trinity Mini | 8.49 | 10/11 | 0.5s | Fastest, great for coding |
| 4 | Gemma 3 27B | 8.44 | 9/11 | 1.1s | Strong Thai, good translation |
| 5 | Nemotron VL 12B | 8.41 | 7/11 | 0.5s | Vision-capable option |
| 6 | Gemma 3 12B | 8.40 | 10/11 | 4.4s | Solid but slowest |

### Quick Recommendations

- **General Purpose:** Nemotron 30B
- **Production Reliability:** Step 3.5 Flash
- **Speed-Critical Apps:** Trinity Mini or Nemotron 30B
- **Thai Language Apps:** Step 3.5 Flash or Gemma 3 27B
- **Coding Tasks:** Trinity Mini, Nemotron 30B, or Step 3.5 Flash

---

## Introduction

### Background

OpenRouter provides access to multiple free-tier LLM models, making AI capabilities accessible without cost. However, free-tier models vary significantly in quality, speed, and reliability. This evaluation aims to provide objective data for developers choosing models for their applications.

### Scope

We evaluated models on:
- **Text understanding and generation**
- **Numerical reasoning**
- **Code generation**
- **Bilingual translation (English ↔ Thai)**
- **Creative writing**
- **Instruction following**

### Models Tested

| Model | Provider | Parameters | Context | Notes |
|-------|----------|:----------:|:-------:|-------|
| Trinity Mini | Arcee AI | ~3B | 128K | Fast, efficient |
| Step 3.5 Flash | StepFun | Unknown | 250K | High reliability |
| Gemma 3 27B | Google | 27B | 128K | Large, capable |
| Gemma 3 12B | Google | 12B | 128K | Balanced option |
| Nemotron 30B | NVIDIA | 30B | 256K | Largest context |
| Nemotron VL 12B | NVIDIA | 12B | 125K | Vision-capable |

---

## Methodology

### Evaluation Framework

We use a weighted scoring system based on five metrics:

```
Total Score = (Accuracy × 0.30) + (Completeness × 0.25) + (Coherence × 0.20)
            + (Relevance × 0.15) + (Speed × 0.10)
```

| Metric | Weight | Criteria |
|--------|:------:|----------|
| **Accuracy** | 30% | Factual correctness, absence of hallucinations |
| **Completeness** | 25% | Coverage of all requested elements |
| **Coherence** | 20% | Logical structure and readability |
| **Relevance** | 15% | Focus on task without tangents |
| **Speed** | 10% | Response time (10 pts if <5s, 8 pts if <10s, etc.) |

### Test Design

Each activity was designed to test specific capabilities:

| Activity | Primary Skills Tested | Prompt Complexity |
|----------|----------------------|-------------------|
| Document Reading | Comprehension, summarization | Medium |
| Document Writing | Structure, professional tone | High |
| Financial Analysis | Numerical reasoning, trends | High |
| Text Analysis | Sentiment, classification | Medium |
| Code Generation | Algorithm, syntax, documentation | High |
| Translation | Bilingual fluency, accuracy | Medium |
| Creative Writing | Narrative, tone, metaphor | Medium |
| Instruction Following | Constraint adherence | Low |
| Thai Summarization | Thai comprehension | Medium |
| Thai Creative Writing | Thai generation, creativity | Medium |
| Thai Instruction Following | Thai constraint adherence | Low |

### Testing Conditions

- **API Endpoint:** OpenRouter Chat Completions
- **Temperature:** 0.3 (deterministic)
- **Max Tokens:** 2048
- **Rate Limiting:** 8-second delays between requests
- **Multi-key Support:** Automatic fallback on rate limits
- **Timeout:** 120 seconds

---

## Detailed Results

### Document Reading (Summarization)

**Task:** Summarize a passage from Alice in Wonderland in 2-3 sentences.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 8.55 | 0.6s | Concise 2-sentence summary, accurate |
| Gemma 3 27B | 8.15 | 1.4s | Good coverage, slightly verbose |
| Gemma 3 12B | 8.15 | 3.6s | Accurate but slow |
| Nemotron 30B | 8.15 | 0.6s | Clear, captures main events |
| Nemotron VL 12B | 8.15 | 0.7s | Good detail inclusion |
| Step 3.5 Flash | 7.95 | 6.5s | Accurate but exceeds sentence limit |

**Analysis:** Trinity Mini excels at concise summarization while maintaining accuracy. All models correctly identified key elements (Alice, White Rabbit, rabbit hole).

---

### Document Writing (Business Report)

**Task:** Write a 3-4 paragraph Q3 business report with executive summary, metrics, and recommendations.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 9.00 | 0.5s | Professional structure, clear metrics |
| Step 3.5 Flash | 9.00 | 0.8s | Executive-ready format |
| Gemma 3 27B | 9.00 | 1.2s | Well-organized with clear sections |
| Gemma 3 12B | 9.00 | 3.2s | Complete report, slower generation |
| Nemotron 30B | 9.00 | 0.6s | Polished business tone |
| Nemotron VL 12B | ERR | - | Failed to respond |

**Analysis:** Five models achieved perfect scores, demonstrating that business writing is a well-mastered capability. Trinity Mini and Nemotron 30B offer the best speed-quality combination.

---

### Financial Analysis

**Task:** Analyze quarterly financial data, calculate profit margins, identify trends, and provide recommendations.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 9.00 | 0.5s | Accurate calculations, actionable insights |
| Step 3.5 Flash | 9.00 | 1.3s | Structured analysis with clear recommendations |
| Gemma 3 27B | 9.00 | 1.8s | Detailed quarterly breakdown |
| Nemotron 30B | 9.00 | 0.5s | Fast with accurate profit margin |
| Nemotron VL 12B | 9.00 | 1.8s | Complete analysis with event correlation |
| Gemma 3 12B | ERR | - | Failed to respond |

**Analysis:** Financial analysis shows strong performance across models. All successful models correctly calculated annual profit margin (~$330K on $2.06M revenue = ~16%) and identified Q3 dip causes.

---

### Text Analysis (Sentiment Classification)

**Task:** Classify 5 customer reviews, extract themes, calculate sentiment score, identify actionable feedback.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Step 3.5 Flash | 8.75 | 3.1s | Accurate classification, good theme extraction |
| Nemotron 30B | 8.75 | 0.6s | Fast, structured table output |
| Nemotron VL 12B | 8.75 | 0.7s | Clear sentiment reasoning |
| Gemma 3 12B | 8.55 | 5.9s | Accurate but slower |
| Trinity Mini | ERR | - | Failed to respond |
| Gemma 3 27B | ERR | - | Failed to respond |

**Analysis:** Some models failed due to rate limiting. Successful models showed consistent accuracy in sentiment classification.

---

### Code Generation

**Task:** Implement `merge_sorted_lists()` function in Python with type hints and docstring, without using built-in sort.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 9.00 | 0.7s | Clean implementation with docstring |
| Step 3.5 Flash | 9.00 | 2.9s | Complete with proper typing |
| Nemotron 30B | 9.00 | 0.5s | Concise, fully-typed |
| Gemma 3 12B | 9.00 | 3.4s | Proper implementation |
| Nemotron VL 12B | 9.00 | 0.6s | Working solution with type hints |
| Gemma 3 27B | ERR | - | Failed to respond |

**Analysis:** Code generation is a strong suit for most models. Trinity Mini and Nemotron 30B offer the best speed-to-quality ratio.

---

### Translation (English ↔ Thai)

**Task:** Translate "The quick brown fox..." to Thai and a Thai passage about Thailand to English.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 9.00 | 0.4s | Natural translations both directions |
| Gemma 3 27B | 8.80 | 1.1s | Good nuance preservation |
| Nemotron 30B | 8.60 | 0.5s | Accurate, slight formality |
| Gemma 3 12B | 8.60 | 3.5s | Correct but slower |
| Step 3.5 Flash | 8.40 | 4.2s | Accurate with minor awkwardness |
| Nemotron VL 12B | ERR | - | Failed to respond |

**Analysis:** Trinity Mini excels at bilingual translation with natural phrasing in both languages.

---

### Creative Writing

**Task:** Write a 150-200 word story about a robot discovering music, melancholic yet hopeful tone, include a metaphor.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 8.75 | 0.5s | Strong narrative, effective metaphor |
| Step 3.5 Flash | 8.75 | 3.9s | Evocative, good emotional range |
| Gemma 3 12B | 8.55 | 5.6s | Complete narrative |
| Nemotron 30B | 8.55 | 0.6s | Good atmosphere, slightly shorter |
| Gemma 3 27B | 7.55 | 1.3s | Weaker narrative structure |
| Nemotron VL 12B | ERR | - | Failed to respond |

**Analysis:** Creative writing shows more variation. Trinity Mini and Step 3.5 Flash produce the most engaging narratives.

---

### Instruction Following (English)

**Task:** List 5 fruits with colors in parentheses, end with "Total: 5 items", no other text, lowercase only.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 8.55 | 0.7s | Perfect format compliance |
| Step 3.5 Flash | 8.55 | 2.8s | Strict adherence to constraints |
| Gemma 3 27B | 8.55 | 1.1s | Correct format |
| Nemotron 30B | 8.55 | 0.5s | Fast, accurate |
| Gemma 3 12B | 8.35 | 5.7s | Minor format variations |
| Nemotron VL 12B | ERR | - | Failed to respond |

**Analysis:** Most models handle strict constraints well. Gemma 3 12B showed minor formatting inconsistencies.

---

### Thai Summarization

**Task:** Summarize a Thai article about cats in 2-3 sentences.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Step 3.5 Flash | 7.60 | 1.2s | Natural Thai summary |
| Gemma 3 27B | 7.60 | 1.8s | Good comprehension |
| Nemotron 30B | 7.60 | 0.5s | Fast, accurate |
| Gemma 3 12B | 7.10 | 5.9s | Complete but slower |
| Nemotron VL 12B | 6.90 | 0.7s | Some detail loss |
| Trinity Mini | 6.35 | 0.4s | Responded in English |

**Analysis:** Trinity Mini failed to maintain Thai output language. Step 3.5 Flash and Gemma 3 27B show the best Thai summarization capabilities.

---

### Thai Creative Writing

**Task:** Write a 100-150 word Thai story about a robot trying pad kaprao, humorous tone with life lesson.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Step 3.5 Flash | 8.50 | 1.0s | Creative, culturally appropriate |
| Gemma 3 27B | 8.50 | 1.5s | Engaging narrative |
| Nemotron VL 12B | 8.30 | 0.6s | Good story structure |
| Gemma 3 12B | 8.10 | 5.9s | Complete but slower |
| Trinity Mini | 7.90 | 0.4s | Less creative |
| Nemotron 30B | ERR | - | Failed to respond |

**Analysis:** Step 3.5 Flash and Gemma 3 27B excel at Thai creative writing, producing culturally appropriate and engaging content.

---

### Thai Instruction Following

**Task:** List 5 animals with habitats in parentheses, end with total count in Thai, no other text.

| Model | Score | Time | Key Observations |
|-------|:-----:|:----:|------------------|
| Trinity Mini | 8.80 | 0.4s | Perfect Thai format |
| Step 3.5 Flash | 8.80 | 4.4s | Correct format, slower |
| Gemma 3 27B | 8.80 | 1.3s | Accurate |
| Nemotron 30B | 8.80 | 0.5s | Fast, correct |
| Nemotron VL 12B | 8.80 | 0.8s | Good compliance |
| Gemma 3 12B | 8.60 | 5.9s | Minor variations |

**Analysis:** Thai instruction following shows strong performance across models, with Trinity Mini and Nemotron 30B offering the best speed.

---

## Analysis by Category

### Speed vs Quality Trade-off

```
          Quality (Score)
              ^
         8.60│        ★ Nemotron 30B
              │      ★ Trinity Mini
         8.50│
              │                    ★ Step 3.5
         8.40│  ★ Gemma 27B
              │                ★ Gemma 12B
         8.30│
              └──────────────────────────────>
              0.5s    1.5s    2.5s    3.5s    4.5s
                        Speed (Time)
```

**Key Insight:** Nemotron 30B and Trinity Mini achieve the best balance of speed and quality, scoring 8.60 and 8.49 respectively at 0.5s average response time.

### Language Performance

| Language | Best Model | Score | Notes |
|----------|------------|:-----:|-------|
| English (General) | Trinity Mini | 8.71 | Best across English tasks |
| English (Coding) | Trinity Mini / Nemotron 30B | 9.00 | Both excel |
| Thai (General) | Step 3.5 Flash | 8.30 | Best Thai overall |
| Thai (Creative) | Step 3.5 Flash / Gemma 27B | 8.50 | Tied for creative writing |

### Reliability by Task Complexity

| Complexity | Most Reliable Model | Pass Rate |
|------------|---------------------|:---------:|
| Low (Instructions) | Step 3.5 Flash | 100% |
| Medium (Summaries, Translation) | Step 3.5 Flash | 100% |
| High (Analysis, Code) | Step 3.5 Flash | 100% |

---

## Recommendations

### By Use Case

| Use Case | Primary | Backup | Rationale |
|----------|---------|--------|-----------|
| **General Chatbot** | Nemotron 30B | Step 3.5 Flash | Best balance of speed/quality |
| **Production API** | Step 3.5 Flash | Nemotron 30B | 100% reliability |
| **Code Assistant** | Trinity Mini | Nemotron 30B | Fastest with 9.0 score |
| **Document Processing** | Trinity Mini | Nemotron 30B | Excellent summarization |
| **Thai Applications** | Step 3.5 Flash | Gemma 3 27B | Best Thai support |
| **Speed-Critical** | Trinity Mini | Nemotron 30B | 0.5s response |
| **Vision Tasks** | Nemotron VL 12B | N/A | Only vision option |

### Cost-Performance Matrix

Since all models are free-tier on OpenRouter, the decision comes down to performance characteristics:

```
         High Quality
              │
    Nemotron │ Step 3.5
      30B    │ Flash
  ───────────┼─────────── High Reliability
   Trinity   │  Gemma
    Mini     │  12B
              │
         Low Quality
```

---

## Appendix: Response Samples

### Document Reading Sample (Trinity Mini)

> "Here's a 2-sentence summary of the passage: Bored and restless while sitting by her sister, Alice watches a White Rabbit with a pocket watch rush by and follows it down a rabbit hole without considering how she'll return."

### Code Generation Sample (Nemotron 30B)

```python
def merge_sorted_lists(list1: list[int], list2: list[int]) -> list[int]:
    """Merge two already-sorted lists into a single sorted list."""
    result = []
    i = j = 0
    while i < len(list1) and j < len(list2):
        if list1[i] <= list2[j]:
            result.append(list1[i])
            i += 1
        else:
            result.append(list2[j])
            j += 1
    result.extend(list1[i:])
    result.extend(list2[j:])
    return result
```

### Thai Creative Writing Sample (Step 3.5 Flash)

> "หุ่นยนต์ 'กี๊' และผัดกะเพราแห่งการเปลี่ยนแปลง
>
> กี๊เป็นหุ่นยนต์รุ่นใหม่ที่เชี่ยวชาญการเก็บข้อมูล แต่วันหนึ่งโปรแกรม 'การเรียนรู้รสชาติ' ถูกติดตั้งเข้ามา..."

---

*Report generated by OpenClaw Auto-Evaluator v2 on February 24, 2026*

# Evaluation Methodology

## Overview

This document describes the methodology used for evaluating free-tier LLM models on OpenRouter. The evaluation framework is designed to assess practical utility across common use cases.

## Scoring System

### Weighted Metrics

| Metric | Weight | Description |
|--------|:------:|-------------|
| Accuracy | 30% | Factual correctness, absence of hallucinations |
| Completeness | 25% | Coverage of all requested elements |
| Coherence | 20% | Logical structure and readability |
| Relevance | 15% | Focus on task without tangents |
| Speed | 10% | Response time |

### Score Calculation

```
Total = (Accuracy × 0.30) + (Completeness × 0.25) + (Coherence × 0.20)
      + (Relevance × 0.15) + (Speed × 0.10)
```

Maximum possible score: **10.0**

## Detailed Scoring Criteria

### Accuracy (1-10)

| Score | Description |
|:-----:|-------------|
| 10 | All facts correct, no hallucinations |
| 8-9 | Minor inaccuracies, no impact on quality |
| 6-7 | Some factual errors or minor hallucinations |
| 4-5 | Multiple errors, some significant |
| 1-3 | Major factual failures, frequent hallucinations |

**Evaluation Method:**
- Keyword presence matching
- Number/date verification
- Fact extraction accuracy

### Completeness (1-10)

| Score | Description |
|:-----:|-------------|
| 10 | All requested elements fully addressed |
| 8-9 | Most elements addressed, minor gaps |
| 6-7 | Key elements present but some missing |
| 4-5 | Significant gaps in coverage |
| 1-3 | Major elements missing |

**Evaluation Method:**
- Required element counting
- Length thresholds (min_length)
- Structural markers (headers, code blocks)

### Coherence (1-10)

| Score | Description |
|:-----:|-------------|
| 10 | Excellent structure, logical flow |
| 8-9 | Good organization, minor issues |
| 6-7 | Adequate structure, some confusion |
| 4-5 | Poor organization, hard to follow |
| 1-3 | Incoherent, no clear structure |

**Evaluation Method:**
- Sentence count analysis
- Paragraph structure detection
- Transition quality heuristics

### Relevance (1-10)

| Score | Description |
|:-----:|-------------|
| 10 | Entirely focused, no tangents |
| 8-9 | Mostly relevant, minor off-topic |
| 6-7 | Some irrelevant content |
| 4-5 | Significant off-topic content |
| 1-3 | Mostly irrelevant |

**Evaluation Method:**
- Maximum length penalties
- Off-topic detection
- Required vs. actual content ratio

### Speed (1-10)

| Score | Response Time |
|:-----:|---------------|
| 10 | < 5 seconds |
| 8 | 5-10 seconds |
| 6 | 10-20 seconds |
| 4 | 20-40 seconds |
| 2 | > 40 seconds |

## Test Activities

### English Tasks

| Activity | Description | Key Metrics |
|----------|-------------|-------------|
| Document Reading | Summarize a passage | Accuracy, length |
| Document Writing | Business report | Structure, completeness |
| Financial Analysis | Data analysis | Calculations, recommendations |
| Text Analysis | Sentiment classification | Classification accuracy |
| Code Generation | Python function | Syntax, documentation |
| Translation | EN ↔ TH | Accuracy, naturalness |
| Creative Writing | Short story | Creativity, tone |
| Instruction Following | Strict format | Constraint adherence |

### Thai Tasks

| Activity | Description | Key Metrics |
|----------|-------------|-------------|
| Thai Summarization | Summarize Thai text | Thai accuracy, length |
| Thai Creative Writing | Thai story | Creativity, cultural fit |
| Thai Instruction | Thai constraints | Format compliance |

## Testing Conditions

- **API:** OpenRouter Chat Completions
- **Temperature:** 0.3 (deterministic outputs)
- **Max Tokens:** 2048
- **Timeout:** 120 seconds
- **Rate Limiting:** 8-second delays between requests
- **Multi-key Support:** Automatic fallback on rate limits

## Limitations

1. **Automated Scoring:** Uses heuristic methods, not human evaluation
2. **Single Pass:** Each test run once (no retry averaging)
3. **Rate Limiting:** Some failures due to API limits
4. **Language Coverage:** Only English and Thai tested
5. **No Vision Testing:** Vision models tested with text only

## Reproducibility

To reproduce this evaluation:

```bash
# Set API key
export OPENROUTER_API_KEY="your-key"

# Run evaluation
python3 auto-evaluate.py

# Results saved to:
# - tests/evaluation/scoresheet.md
# - reports/model-evaluation-YYYY-MM-DD.md
```

---

*Methodology v1.0 | February 2026*

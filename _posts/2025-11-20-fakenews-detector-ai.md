---
layout: post
title: "FakeNewsDetector AI: Misinformation Detection with RoBERTa and NLP Heuristics"
description: "Fine-tuning RoBERTa for three-class fake news classification, with a custom heuristic layer for pseudoscience detection and a Gradio web interface."
date: 2025-11-20
categories: blog projects
permalink: /blog/projects/fakenews-detector-ai/
---

FakeNewsDetector AI is a misinformation detection system that classifies news articles as Reliable, Doubtful, or Fake. The key challenge it addresses is not obvious clickbait — it's fake content that mimics the language and structure of legitimate science.

---

## The problem

Most fake news classifiers are trained on surface-level patterns: excessive capitalization, sensationalist vocabulary, anonymous sourcing. They fail on a different kind of misinformation: pseudoscientific articles that use academic-sounding language to disguise false claims.

A headline like *"Scientists confirm coffee prevents cancer 100% — study not yet published in any recognized journal"* will fool a model trained only on obvious fake news, because it contains words like "scientists", "study", and "university". This system was designed specifically to catch those cases.

---

## Project objectives

- Fine-tune a transformer model for three-class news classification
- Add a heuristic layer specifically targeting pseudoscientific language patterns
- Build a usable interface for editorial and research use cases
- Expose a REST API for potential integration

---

## Technologies used

- **RoBERTa-base** (HuggingFace Transformers) for neural inference
- **PyTorch + HuggingFace Trainer** for fine-tuning
- **Custom regex heuristics** for pseudoscience pattern detection
- **Gradio 4.x** for the web interface and REST API
- **Google Colab (NVIDIA T4 GPU)** for training infrastructure

---

## How it works

The prediction pipeline has two stages that are fused at inference time:

**Stage 1 — Neural inference:** The input text is tokenized and passed through the fine-tuned RoBERTa model (12 attention layers), producing softmax scores for each class.

**Stage 2 — Heuristic fusion:** A preprocessing module extracts an `alarm_score` based on regex pattern matches. This score is blended with the neural output using an 80/20 weighting.

```python
# When alarm_score is high, heuristics get 35% weight
if alarm_score > 0.6:
    scores["FAKE"] = scores["FAKE"] * 0.65 + alarm_score * 0.35
```

The reason for the fusion approach: transformers are excellent at contextual understanding but can be fooled by well-structured pseudoscience. Explicit rules catch the patterns that the neural model misses.

---

## Pseudoscience detection

The hardest cases use fake academic language. The heuristic module uses patterns like:

```python
r"\b100\s*%\s*(protection|effectiveness|cure)",
r"(not|never)\s+(yet\s+)?(been\s+)?(published|peer.reviewed)",
r"(unnamed|anonymous)\s+(university|researchers|scientists)",
r"(secret|hidden|suppressed)\s+(cure|treatment|study)",
```

When two or more of these patterns match, the system overrides the neural score and forces a high-confidence Fake classification.

---

## Training

The model was fine-tuned on ~8,500 balanced news articles from the Kaggle Fake and Real News Dataset, supplemented with 45 hand-crafted pseudoscience examples.

| Epoch | Train Loss | Val Accuracy | F1 |
|---|---|---|---|
| 1 | 0.008785 | 99.84% | 99.84% |
| 2 | 0.000578 | 99.84% | 99.84% |
| 3* | 0.000352 | 99.38% | 99.37% |

*EarlyStopping triggered at epoch 3 — best model from epoch 2 saved.*

Training ran in approximately 12 minutes on a Google Colab T4 GPU.

---

## Interface and API

The Gradio interface provides a result card with verdict, confidence bars, and an explanation of the classification signals detected. Gradio also automatically exposes a REST API at `/run/predict`, making the system callable from external tools without additional backend work.

---

## Challenges and decisions

The decision to use a fusion approach rather than a purely neural model came from observing failures on pseudoscience examples during early testing. A model trained only on political fake news learned different surface patterns than what appears in health or science misinformation.

The 80/20 weighting was set empirically — enough heuristic influence to catch explicit pseudoscience signals, without overriding the model on ambiguous inputs.

---

## Limitations

- Primarily trained on English-language US political news
- Performance varies on non-political domains and Spanish content
- No real-time fact-checking database integration

---

## What I learned

- Fine-tuning transformer models for classification tasks
- Designing hybrid neural + rule-based systems
- The limits of single-source training data for out-of-domain generalization
- Building deployable ML interfaces with Gradio

---

## Next steps

- Multilingual support with XLM-RoBERTa
- Integration with fact-checking APIs (Snopes, PolitiFact)
- FastAPI backend for production deployment
- Browser extension for real-time article scanning

---

**Repository:**  
https://github.com/renecano/FakeNewsDetectorAI

---

You can also explore:
- [All projects](/projects/)
- [More technical posts](/blog/)

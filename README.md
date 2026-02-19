# Emotion Impact Aware Summarization

📄 **Full Paper Detail**

[![Paper](https://img.shields.io/badge/Paper-PDF-red)](Emotion_impact_summarization.pdf)
[![Model](https://img.shields.io/badge/Model-T5--Base-blue)]
[![Dataset](https://img.shields.io/badge/Dataset-TweetSum-green)]
[![Framework](https://img.shields.io/badge/Framework-HuggingFace-orange)]
[![License](https://img.shields.io/badge/License-Academic-lightgrey)]

Official implementation of:

Emotion Impact Aware Summarization  
Ouayres Oumaima, El Ater Khaoula, Boujnia Aya, El Abdellaoui Said  
Cadi Ayyad University – Morocco

---

## Abstract

Emotions significantly influence how events are perceived, interpreted, and remembered.  
However, most neural summarization systems prioritize factual compression and lexical similarity while overlooking affective alignment.

This work introduces an emotion-conditioned abstractive summarization framework built upon T5-base. By integrating fine-grained emotion detection into the generation prompt, the model produces summaries that preserve both semantic fidelity and emotional consistency.

Experiments on the TweetSum dataset demonstrate improvements in lexical overlap, semantic similarity, and affective alignment compared to a Vanilla T5 baseline.

---

## Contributions

• Systematic analysis of emotional signals in event-based social media summarization  
• Emotion-conditioned fine-tuning of T5 for controlled abstractive generation  
• Multi-dimensional evaluation combining lexical, semantic, and affective metrics  
• End-to-end pipeline integrating emotion detection, prompt conditioning, and evaluation  

---

## Method Overview

Pipeline:

Tweets  
→ Emotion Detection  
→ Prompt Conditioning  
→ T5 Fine-tuning  
→ Emotion-Aware Summary  
→ Multi-Dimensional Evaluation  

### Components

1. Event aggregation (up to 5 tweets per event)
2. Emotion classification using pretrained RoBERTa-based model
3. Emotion-conditioned prompt construction
4. Fine-tuning T5-base (5 epochs, LR = 3e-5)
5. Evaluation using ROUGE, BERTScore, Emotion Consistency, KL divergence

---

## Quantitative Results

| Model | ROUGE-1 | ROUGE-2 | ROUGE-L | Emotion Consistency | KL Divergence | BERTScore |
|--------|----------|----------|----------|---------------------|---------------|------------|
| T5 Vanilla | 0.2741 | 0.0613 | 0.2237 | 0.3124 | 1.1846 | 0.8412 |
| T5 Fine-tuned | **0.3065** | **0.0826** | **0.2503** | **0.4679** | **0.7595** | **0.8680** |

The fine-tuned model improves semantic fidelity while significantly enhancing emotional alignment and reducing affective divergence.

---

## Repository Structure

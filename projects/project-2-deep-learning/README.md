# Project 2: Deep Learning — Fine-Tuned Model

## Overview
Fine-tune a pre-trained model (vision or NLP) on a novel task with full experiment tracking.

## When to Build
Week 16 (end of Phase 3)

## Requirements
- Use PyTorch (not TensorFlow)
- Fine-tune a pre-trained model (ResNet, BERT, etc.)
- Track experiments with Weights & Biases
- Include error analysis (where does the model fail?)
- Document training decisions and tradeoffs

## Ideas
- Custom image classifier (your own dataset)
- Sentiment analysis on niche domain
- Named Entity Recognition on domain-specific text
- Document classification

## Deliverables
- [ ] Training scripts (clean, modular)
- [ ] W&B dashboard with experiments
- [ ] Model evaluation report
- [ ] Error analysis notebook
- [ ] Blog post: "Lessons from Fine-Tuning"
- [ ] README with reproduction instructions

## Structure
```
project-2-deep-learning/
├── README.md
├── src/
│   ├── data.py          # Dataset + DataLoader
│   ├── model.py         # Model architecture
│   ├── train.py         # Training loop
│   ├── evaluate.py      # Evaluation metrics
│   └── config.py        # Hyperparameters
├── notebooks/
│   ├── eda.ipynb
│   └── error_analysis.ipynb
├── configs/
│   └── experiment.yaml
└── requirements.txt
```

# Phase 3: Deep Learning (Weeks 11–16)

## Overview

Go from "I know sklearn" to "I can build and train neural networks from scratch in PyTorch." This phase culminates in implementing a Transformer — the architecture that powers all modern AI.

**Key principle**: Build from scratch first (understand), THEN use frameworks (ship).

---

## Week 11: Neural Networks from Scratch

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [3Blue1Brown: Neural Networks](https://www.youtube.com/playlist?list=PLZHQObOWTQDNU6R1_67000Dx_ZCJB-3pi) | 1.5 hrs |
| 📺 Video | [Karpathy: micrograd](https://www.youtube.com/watch?v=VMj-3S1tku0) | 2.5 hrs |
| 📺 Lecture | CS231n Lectures 3–4 | 3 hrs |

### What to Build
- Neural network from scratch (NumPy only):
  - Forward pass
  - Backpropagation (compute gradients via chain rule)
  - Gradient checking (numerical vs analytical)
  - Training loop with mini-batches
- Train on MNIST → achieve >95% accuracy
- Visualize: activation distributions, gradient magnitudes per layer

### Interview Connection
- "Implement backpropagation" — Amazon, Google coding rounds
- "What causes vanishing gradients?" — ML fundamentals (everywhere)

---

## Week 12: PyTorch Mastery

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Tutorial | [PyTorch Official Tutorials](https://pytorch.org/tutorials/) | 4 hrs |
| 📺 Video | [Karpathy: makemore Part 1](https://www.youtube.com/watch?v=PaCmpygFfXo) | 2 hrs |
| 📺 Course | Fast.ai Lesson 1–2 | 3 hrs |

### What to Build
- Rewrite Week 11's network in PyTorch
- Custom Dataset + DataLoader implementation
- Training with: Adam, lr scheduler, early stopping, checkpointing
- Mixed precision training (torch.cuda.amp)
- W&B (Weights & Biases) experiment tracking integration

### Interview Connection
- PyTorch is explicitly required at OpenAI, Anthropic, and preferred everywhere
- "Walk me through your training loop" — common in ML depth rounds

---

## Week 13: CNNs & Computer Vision

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Lecture | CS231n Lectures 5, 9 | 3 hrs |
| 📺 Course | Fast.ai Lesson 3 | 1.5 hrs |
| 📖 Book | Géron Ch. 14 | 2 hrs |

### What to Build
- Image classifier on custom dataset (collect your own!)
- Transfer learning: fine-tune ResNet/EfficientNet
- Grad-CAM: visualize what the model "looks at"
- Data augmentation comparison (effect on performance)
- Architecture comparison: VGG vs ResNet vs EfficientNet (params vs accuracy)

### Blog Idea
"What CNNs Actually See: A Layer-by-Layer Visual Tour" — include feature maps + Grad-CAM heatmaps

---

## Week 14: Sequence Models & Attention

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Lecture | CS231n Lecture 10 | 1.5 hrs |
| 📺 Video | [Karpathy: makemore Part 2–3](https://www.youtube.com/watch?v=PaCmpygFfXo) | 4 hrs |
| 📖 Blog | [Jay Alammar: The Illustrated Transformer](https://jalammar.github.io/illustrated-transformer/) | 1 hr |

### What to Build
- Character-level language model (bigram → MLP → RNN)
- RNN/LSTM from scratch
- Attention mechanism from scratch:
  - Scaled dot-product attention
  - Visualize attention weights as heatmap
- Sequence-to-sequence with attention (translation toy task)

### Interview Connection
- "Explain the attention mechanism" — asked at every AI company
- "What problems do RNNs have that Transformers solve?" — ML fundamentals

---

## Week 15: Transformers (Full Architecture) ⭐⭐⭐

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Video | [Karpathy: Let's build GPT](https://www.youtube.com/watch?v=kCc8FmEb1nY) | 2 hrs |
| 📺 Video | [Karpathy: Zero to Hero Lessons 4–5](https://www.youtube.com/playlist?list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ) | 4 hrs |
| 📄 Paper | "Attention Is All You Need" (Vaswani et al., 2017) | 1 hr |
| 📺 Course | [ML Mastery: Transformer Mini-Course](https://machinelearningmastery.com/building-transformer-models-from-scratch-with-pytorch-10-day-mini-course/) (days 1–5) | 3 hrs |

### What to Build
- **Mini-GPT from scratch** (following Karpathy):
  - Token + positional embeddings
  - Multi-head self-attention
  - Layer normalization
  - Feed-forward blocks
  - Causal masking
  - Full decoder-only transformer
- Train on Shakespeare → generate text
- Experiment: vary model size, context length, # heads
- Visualize: attention patterns, positional encoding, loss scaling

### Blog Idea
"Building GPT from Scratch: My Annotated Implementation" — THIS WILL BE YOUR HIGHEST-ENGAGEMENT POST. Annotate every component. Include architecture diagrams.

### Interview Connection
- "Explain the Transformer architecture" — asked at Amazon, Meta, Google, OpenAI, Anthropic
- "What is KV-cache?" — inference optimization (OpenAI, Anthropic)
- "How does multi-head attention differ from single-head?" — ML depth rounds

---

## Week 16: Training Best Practices + DL Project #2

### Resources
| Type | Resource | Time |
|---|---|---|
| 📺 Course | Fast.ai Lessons 4–7 | 6 hrs |
| 📖 Blog | Sebastian Raschka's training tips | Reference |

### Topics
- Learning rate finder + cosine annealing + warmup
- Gradient clipping, gradient accumulation
- Data augmentation strategies
- Label smoothing, mixup
- Knowledge distillation (intro)
- Distributed training basics (DDP)

### Project #2
**Fine-tune a pre-trained model on a novel task:**
- Choose NLP or Vision
- Full pipeline: data → preprocess → fine-tune → evaluate → iterate
- Track all experiments in W&B
- Error analysis: where does the model fail?
- Write-up: what worked, what didn't, what you'd change

---

## 🎯 Phase 3 Completion Criteria

You're ready for Phase 4 when you can:
- [ ] Implement backpropagation by hand for a 2-layer network
- [ ] Write a PyTorch training loop from memory (Dataset, DataLoader, optimizer, scheduler)
- [ ] Explain the full Transformer architecture (attention, FFN, residuals, layer norm, masking)
- [ ] Fine-tune a pre-trained model on a new task
- [ ] Explain why Transformers replaced RNNs (parallelism, long-range dependencies)
- [ ] Published your "GPT from scratch" blog post

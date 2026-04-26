# RT-2 Toy Implementation (Vision-Language-Action Model)

## Overview
This project implements a simplified version of RT-2:

- Vision-Language-Action (VLA) model
- Mixed training with VQA + robot action data
- Action tokenization (continuous → discrete → text tokens)

## Key Idea
Unify:
- image + instruction → action tokens  
- image + question → text  

using a single sequence generation model.

## Core Implementation
- Robot actions are represented as **text tokens**
- The model generates **action token sequences** from image + instruction prompts
- VQA and robot action data are both formulated as sequence generation tasks and trained using a single cross-entropy loss
- **Constrained decoding** is applied during inference to allow only valid action tokens

## Differences from RT-2 Paper
- Uses a small **ViT-GPT2** model instead of PaLI-X / PaLM-E
- Predicts **2D actions (dx, dy)** instead of 6-DoF robot actions
- Uses **21-bin discretization** instead of 256-bin
- Trained on a **toy dataset** (SimpleVQA + Language-Table subset) instead of web-scale data
- Focuses on **action prediction only**, without full multi-task setup from the paper
- Does not include **closed-loop control rollout** (single-step prediction only)

## Results
- AX accuracy: 0.31  
- AY accuracy: 0.46  
- Both: 0.27  

## Key Contribution
- Demonstrates VLA formulation in a minimal setting
- Implements action-token-based control via language modeling
- Validates mixed-task learning (VQA + control) in a unified framework
 
## How to Run
- Open in Colab
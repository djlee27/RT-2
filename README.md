# RT-2 Toy Implementation (Vision-Language-Action Model)

## Overview
This project implements a simplified version of RT-2:
- Vision-Language-Action (VLA) model
- Mixed training with VQA + robot action data
- Action tokenization (continuous → discrete → text tokens)

## Key Idea
We unify:
image + instruction → action tokens
image + question → text

using a single sequence generation model.

## Differences from RT-2
- Small ViT-GPT2 model instead of PaLI-X / PaLM-E
- 2D action space (dx, dy)
- 21-bin discretization (not 256-bin)
- Toy dataset (Language-Table + SimpleVQA)

## Results
- AX accuracy: 0.31
- AY accuracy: 0.46
- Both: 0.27

## Key Contribution
- Demonstrated VLA formulation in a minimal setting
- Implemented action-token constrained decoding
- Verified mixed-task learning (VQA + control)

## How to run
(Open in Colab)
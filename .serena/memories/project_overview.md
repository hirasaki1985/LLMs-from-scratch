# LLMs from Scratch - Project Overview

## Purpose
This repository contains the code for developing, pretraining, and finetuning a GPT-like LLM. It's the official code repository for the book "Build a Large Language Model (From Scratch)" by Sebastian Raschka.

## Key Features
- Implementation of GPT models from scratch using PyTorch
- Chapter-by-chapter progression from basic concepts to advanced techniques
- Educational focus with step-by-step explanations
- Code designed to run on conventional laptops (no specialized hardware required)
- Automatic GPU utilization when available

## Repository Structure
- **ch01-ch07/**: Main chapter code organized by book chapters
  - ch02: Working with Text Data (tokenization, data loading)
  - ch03: Coding Attention Mechanisms  
  - ch04: Implementing a GPT Model from Scratch
  - ch05: Pretraining on Unlabeled Data
  - ch06: Finetuning for Text Classification
  - ch07: Finetuning to Follow Instructions
- **appendix-A/**: Introduction to PyTorch
- **appendix-D/**: Adding Bells and Whistles to Training Loop
- **appendix-E/**: Parameter-efficient Finetuning with LoRA
- **setup/**: Setup and installation instructions
- **pkg/**: Python package with reusable modules (`llms_from_scratch`)

## Tech Stack
- **Primary Language**: Python (3.10-3.12)
- **ML Framework**: PyTorch (>=2.3.0)
- **Development**: Jupyter Lab (>=4.0)
- **Key Dependencies**:
  - tiktoken (tokenization)
  - matplotlib (plotting)
  - tensorflow (some utilities)
  - tqdm (progress bars)
  - numpy, pandas (data manipulation)

## Target Audience
Educational repository for learning LLM implementation from scratch. Code is optimized for understanding rather than production performance.
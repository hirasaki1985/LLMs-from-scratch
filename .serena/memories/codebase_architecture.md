# Codebase Architecture

## Directory Structure

```
LLMs-from-scratch/
├── ch01-ch07/                    # Main book chapters
│   ├── 01_main-chapter-code/     # Primary implementations
│   ├── 02_bonus*/               # Supplementary materials
│   └── exercise-solutions.ipynb # Chapter exercises
├── appendix-A/                  # PyTorch introduction
├── appendix-D/                  # Training loop enhancements  
├── appendix-E/                  # LoRA finetuning
├── setup/                       # Installation guides
├── pkg/                         # Python package
│   └── llms_from_scratch/       # Reusable modules
│       ├── ch02.py - ch07.py    # Chapter implementations
│       ├── llama3.py            # Llama model implementation
│       ├── qwen3.py             # Qwen model implementation  
│       ├── kv_cache/            # KV caching implementations
│       └── tests/               # Test suite
└── .github/workflows/           # CI/CD pipelines
```

## Core Components

### Chapter Progression
1. **ch02**: Text processing, tokenization, data loading
2. **ch03**: Attention mechanisms (self-attention, multi-head)
3. **ch04**: Complete GPT model architecture
4. **ch05**: Pretraining procedures and techniques
5. **ch06**: Classification finetuning
6. **ch07**: Instruction following finetuning

### Key Python Modules (`pkg/llms_from_scratch/`)

#### Core Model Classes
- **GPTModel**: Basic transformer architecture
- **LayerNorm**: Layer normalization implementation
- **TransformerBlock**: Single transformer layer
- **MultiHeadAttention**: Attention mechanism
- **FeedForward**: MLP component

#### Advanced Implementations  
- **llama3.py**: Llama 3 architecture from scratch
- **qwen3.py**: Qwen 3 model (including MoE variants)
- **kv_cache/**: Optimized inference with key-value caching
- **kv_cache_batched/**: Batch processing with KV cache

#### Utilities
- Text processing and tokenization helpers
- Training loop utilities
- Model loading and saving functions
- Generation and inference tools

## Design Patterns

### Configuration-Driven Models
```python
cfg = {
    "vocab_size": 50257,
    "context_length": 1024, 
    "emb_dim": 768,
    "n_heads": 12,
    "n_layers": 12,
    "drop_rate": 0.1
}
model = GPTModel(cfg)
```

### Modular Architecture
- Separate classes for each component (attention, feedforward, etc.)
- Easy swapping of implementations (basic vs. fast versions)
- Clear separation between model definition and training code

### Educational Implementations
- **Basic versions**: Clear, step-by-step implementations
- **Optimized versions**: Performance-focused variants (e.g., GPTModelFast)
- **From-scratch**: Mathematical operations implemented without high-level libraries

## Testing Strategy
- **Unit tests**: Individual component testing
- **Integration tests**: Full model pipeline testing  
- **Cross-platform**: Linux, macOS, Windows compatibility
- **Multiple PyTorch versions**: Ensuring compatibility across versions
- **Chapter-specific tests**: Validation for each book chapter
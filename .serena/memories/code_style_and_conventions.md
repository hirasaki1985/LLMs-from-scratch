# Code Style and Conventions

## Code Style
- **Linter**: Ruff (faster flake8 equivalent)
- **Line Length**: 140 characters (configured in pyproject.toml)
- **Python Version**: 3.10+ (< 3.13)

## Ruff Configuration (pyproject.toml)
```toml
[tool.ruff]
line-length = 140

[tool.ruff.lint]
exclude = [".venv"]
ignore = [
    "C406", "E226", "E402", "E702", "E703",
    "E722", "E731", "E741"
]
```

## Code Patterns and Conventions

### PyTorch Model Structure
- Models inherit from `nn.Module`
- Standard PyTorch patterns (e.g., `__init__` and `forward` methods)
- Configuration-driven model initialization
- Example from GPTModel:
  ```python
  class GPTModel(nn.Module):
      def __init__(self, cfg):
          super().__init__()
          # Initialize layers based on config
      
      def forward(self, in_idx):
          # Forward pass logic
  ```

### Naming Conventions
- **Classes**: PascalCase (e.g., `GPTModel`, `TransformerBlock`)
- **Functions**: snake_case (e.g., `generate_text_simple`)
- **Variables**: snake_case (e.g., `tok_emb`, `pos_emb`)

### Educational Focus
- Code prioritizes readability and understanding over performance
- Extensive use of comments and docstrings for educational purposes
- Step-by-step implementations that mirror mathematical concepts
- Clear separation between basic and optimized implementations (e.g., `GPTModel` vs `GPTModelFast`)

### File Organization
- Main chapter code in Jupyter notebooks (`.ipynb`)
- Reusable utilities in Python modules (`.py`)
- Summary/standalone versions for key implementations
- Test files organized under `pkg/llms_from_scratch/tests/`
# Suggested Commands

## Package Installation
```bash
# Quick setup (from root directory)
pip install -r requirements.txt

# For development (with uv - modern Python package manager)
uv sync --dev --python=3.10

# For Google Colab
pip install uv && uv pip install --system -r https://raw.githubusercontent.com/rasbt/LLMs-from-scratch/refs/heads/main/requirements.txt
```

## Development Commands

### Linting and Code Quality
```bash
# Run ruff linting (primary linter)
ruff check .

# With uv environment
source .venv/bin/activate
ruff check .
```

### Testing
```bash
# Run pytest (tests located in pkg/llms_from_scratch/tests/)
pytest

# With uv
uv run pytest
```

### Jupyter Lab
```bash
# Start Jupyter Lab for notebook development
jupyter lab

# With uv
uv run jupyter lab
```

## Git Commands (macOS/Darwin)
```bash
# Basic git operations
git status
git add .
git commit -m "message"
git push origin main

# Clone repository
git clone --depth 1 https://github.com/rasbt/LLMs-from-scratch.git
```

## File System Commands (macOS/Darwin)
```bash
# List files
ls -la

# Find files
find . -name "*.py" -type f

# Navigate directories  
cd path/to/directory

# Search in files
grep -r "pattern" .
```

## Package Building (for maintainers)
```bash
# Build package
python -m build

# Upload to PyPI
twine upload dist/*
```

## Environment Management
```bash
# With uv (recommended)
uv venv
source .venv/bin/activate

# Traditional approach
python -m venv venv
source venv/bin/activate  # macOS/Linux
```
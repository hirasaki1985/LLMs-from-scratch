# Task Completion Checklist

## When Code Changes Are Made

### 1. Code Quality Checks
```bash
# Run ruff linting (REQUIRED)
ruff check .

# If using uv environment:
source .venv/bin/activate
ruff check .
```

### 2. Testing
```bash
# Run all tests 
pytest

# Run specific test files if working on particular chapters
pytest pkg/llms_from_scratch/tests/test_ch04.py
pytest pkg/llms_from_scratch/tests/test_ch05.py
# etc.
```

### 3. Notebook Validation
- If working with Jupyter notebooks, ensure they run from start to finish
- Check that outputs are reasonable and match expected results
- Clear outputs before committing (if required by project standards)

### 4. Documentation
- Update relevant README files if functionality changes
- Ensure code comments are accurate and helpful
- Update exercise solutions if exercises are modified

## Before Committing

### 1. File Organization
- Ensure new files are in appropriate directories
- Follow naming conventions (snake_case for files, PascalCase for classes)
- Don't commit temporary or generated files

### 2. Dependencies
- If new dependencies are added, update `requirements.txt` and `pyproject.toml`
- Ensure compatibility with Python 3.10-3.12
- Test that installation works from clean environment

### 3. Final Verification
```bash
# Clean install test (with uv)
uv sync --dev --python=3.10
source .venv/bin/activate
ruff check .
pytest
```

## Special Considerations
- **Educational Focus**: Ensure code changes maintain readability and educational value
- **Book Consistency**: Changes to main chapter code should align with book content
- **Hardware Compatibility**: Code should work on conventional laptops without GPU requirements
- **Cross-platform**: Test on different operating systems when possible

## CI/CD Pipeline
The repository uses GitHub Actions for:
- **Linting**: PEP8 style checks with ruff
- **Testing**: Cross-platform testing (Linux, macOS, Windows)  
- **Multiple Python versions**: Testing with different PyTorch versions
- **Link checking**: Ensuring documentation links work
- **Spell checking**: Basic spelling validation
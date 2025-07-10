# Integration Guide

## pip Integration

Use AI-PyResolver as a drop-in replacement for pip's dependency resolver:

```bash
# Install with AI resolution
pip install --use-feature=ai-resolver package-name

# Or use directly
pyresolver resolve "package-name>=1.0" | pip install -r /dev/stdin
```

## Poetry Integration

```toml
# pyproject.toml
[tool.poetry.dependencies]
python = "^3.8"

[tool.ai-pyresolver]
strategy = "ai_optimized"
timeout = 30
```

```bash
# Use with poetry
poetry add $(pyresolver resolve "django>=4.0" --output-format poetry)
```

## pipenv Integration

```python
# Pipfile
[packages]
ai-pyresolver = "*"

[scripts]
resolve = "pyresolver resolve -r Pipfile"
```

## Docker Integration

```dockerfile
FROM python:3.11-slim

# Install AI-PyResolver
RUN pip install ai-pyresolver

# Use for dependency resolution
COPY requirements.txt .
RUN pyresolver resolve -r requirements.txt -o resolved.txt
RUN pip install -r resolved.txt

COPY . .
CMD ["python", "app.py"]
```

## CI/CD Integration

### GitHub Actions

```yaml
name: AI Dependency Resolution
on: [push, pull_request]

jobs:
  resolve:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@v3
    - uses: actions/setup-python@v4
      with:
        python-version: '3.11'
    
    - name: Install AI-PyResolver
      run: pip install ai-pyresolver
    
    - name: Resolve dependencies
      run: pyresolver resolve -r requirements.txt --strategy ai_optimized
    
    - name: Install resolved dependencies
      run: pip install -r requirements.txt
```

## IDE Integration

### VS Code

Add to `.vscode/settings.json`:

```json
{
    "python.defaultInterpreterPath": "./venv/bin/python",
    "python.terminal.activateEnvironment": true,
    "ai-pyresolver.strategy": "ai_optimized",
    "ai-pyresolver.autoResolve": true
}
```

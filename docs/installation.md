# Installation Guide

## Quick Installation

```bash
pip install ai-pyresolver
```

## Development Installation

```bash
# Clone the repository
git clone https://github.com/ommnnitald/pyresolver.git
cd pyresolver

# Install in development mode
pip install -e ".[dev]"

# Run tests
pytest

# Run the demo
python demo.py
```

## Requirements

- Python 3.8+
- pip 21.0+

## Verification

```python
from pyresolver import PyResolver
resolver = PyResolver()
print("AI-PyResolver installed successfully!")
```

# Contributing to AI-PyResolver

## Getting Started

1. **Fork the repository**
2. **Clone your fork**
   ```bash
   git clone https://github.com/yourusername/pyresolver.git
   cd pyresolver
   ```

3. **Set up development environment**
   ```bash
   pip install -e ".[dev]"
   ```

4. **Run tests**
   ```bash
   pytest
   ```

## Development Workflow

1. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Write code
   - Add tests
   - Update documentation

3. **Run the test suite**
   ```bash
   pytest
   flake8 pyresolver/
   black pyresolver/
   mypy pyresolver/
   ```

4. **Commit and push**
   ```bash
   git add .
   git commit -m "Add your feature description"
   git push origin feature/your-feature-name
   ```

5. **Create a Pull Request**

## Code Style

- Use **Black** for code formatting
- Use **flake8** for linting
- Use **mypy** for type checking
- Follow **PEP 8** guidelines

## Testing

- Write tests for all new features
- Maintain 90%+ test coverage
- Use **pytest** for testing
- Add integration tests for complex features

## Documentation

- Update README.md for user-facing changes
- Add docstrings to all public functions
- Update API documentation
- Include examples in docstrings

## AI Model Contributions

If contributing to the AI components:

1. **Data Requirements**
   - Provide training data sources
   - Document data preprocessing steps
   - Include validation metrics

2. **Model Updates**
   - Benchmark against existing models
   - Provide performance comparisons
   - Document model architecture changes

## Reporting Issues

- Use GitHub Issues
- Provide minimal reproduction case
- Include environment details
- Add relevant logs/error messages

## Questions?

- Open a GitHub Discussion
- Join our Discord community
- Email: support@ai-pyresolver.com

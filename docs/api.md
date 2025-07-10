# API Reference

## PyResolver Class

### Constructor

```python
from pyresolver import PyResolver
from pyresolver.core.resolver import ResolverConfig
from pyresolver.core.models import ResolutionStrategy

config = ResolverConfig(
    strategy=ResolutionStrategy.AI_OPTIMIZED,
    use_real_pypi=False,
    timeout=30.0
)
resolver = PyResolver(config)
```

### Methods

#### resolve(requirements)

Resolves a list of package requirements.

**Parameters:**
- `requirements` (List[str]): List of requirement strings (e.g., ['django>=4.0', 'requests>=2.25.0'])

**Returns:**
- `ResolutionResult`: Object containing resolution details

**Example:**
```python
result = resolver.resolve(['django>=4.0', 'requests>=2.25.0'])
print(f"Success: {result.is_successful}")
print(f"Packages: {result.package_count}")
```

## ResolutionResult Class

### Properties

- `is_successful` (bool): Whether resolution succeeded
- `resolved_packages` (Dict[str, PackageVersion]): Resolved packages
- `package_count` (int): Number of resolved packages
- `resolution_time` (float): Time taken in seconds
- `strategy` (ResolutionStrategy): Strategy used
- `conflicts` (List[Conflict]): Any conflicts found

## ResolutionStrategy Enum

- `AI_OPTIMIZED`: Use AI for optimal resolution
- `CONSERVATIVE`: Prefer stable versions
- `LATEST`: Prefer latest versions
- `MINIMAL`: Minimal version resolution

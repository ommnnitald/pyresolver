# CLI Guide

## Basic Usage

```bash
# Resolve requirements from command line
pyresolver resolve "django>=4.0" "requests>=2.25.0"

# Resolve from requirements file
pyresolver resolve -r requirements.txt

# Use specific strategy
pyresolver resolve --strategy ai_optimized "tensorflow>=2.0"

# Output to file
pyresolver resolve -r requirements.txt -o resolved.txt
```

## Commands

### resolve

Resolve package dependencies.

**Options:**
- `-r, --requirements FILE`: Read requirements from file
- `-o, --output FILE`: Write resolved packages to file
- `--strategy STRATEGY`: Resolution strategy (ai_optimized, conservative, latest, minimal)
- `--timeout SECONDS`: Timeout for resolution (default: 30)
- `--verbose`: Enable verbose output
- `--no-ai`: Disable AI features

**Examples:**
```bash
# Basic resolution
pyresolver resolve "django>=4.0"

# From file with AI optimization
pyresolver resolve -r requirements.txt --strategy ai_optimized

# Verbose output
pyresolver resolve --verbose "tensorflow>=2.0" "torch>=1.0"
```

### check

Check for conflicts in existing environment.

```bash
pyresolver check
pyresolver check --environment myenv
```

### explain

Explain why a resolution failed.

```bash
pyresolver explain "conflicting-package-a" "conflicting-package-b"
```

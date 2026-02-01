# Python Project Justfile Template

Comprehensive automation template for Python projects using modern tooling.

## Features

✅ **UV Package Manager** - Fast, modern Python package management  
✅ **Ruff** - Lightning-fast linting and formatting  
✅ **MyPy** - Static type checking  
✅ **Pytest** - Testing with coverage  
✅ **Pre-commit** - Git hooks for code quality  
✅ **Clean Tasks** - Artifact management  

## Installation

```bash
curl -o justfile https://raw.githubusercontent.com/dr-saad-la/polyglot-engineer-templates/main/justfile-templates/python/justfile
```

## Customization

Edit these variables in the justfile:

```bash
python_version := "3.12"    # Your Python version
app_name := "myapp"         # Your package name
```

## Available Commands

### Setup
```bash
just install    # Install dependencies with UV
just setup      # Complete project setup
```

### Development
```bash
just dev        # Start development server
just repl       # Python REPL with project context
```

### Code Quality
```bash
just format     # Format code with Ruff
just lint       # Lint code with Ruff
just types      # Type check with MyPy
just check      # Run all quality checks
```

### Testing
```bash
just test           # Run tests
just test-cov       # Tests with HTML coverage report
just test-watch     # Watch mode (auto-run on changes)
```

### Build & Deploy
```bash
just build          # Build package
just deploy ENV     # Deploy to environment
```

### Cleanup
```bash
just clean      # Remove build artifacts
just reset      # Complete reset (removes .venv)
```

### Utilities
```bash
just info       # Show project information
just            # List all commands
```

## Usage Example

```bash
# First time setup
just setup

# Daily workflow
just dev            # Start development
just test-watch     # Tests running in background

# Before committing
just check          # All quality checks
just test           # Final test run

# Build and deploy
just build
just deploy prod
```

## Requirements

- **Just** - Task runner ([install guide](https://just.systems/))
- **UV** - Package manager ([install guide](https://github.com/astral-sh/uv))
- **Python 3.12+**

## Customization Examples

### Add Database Commands

```bash
# Database migrations
db-migrate MESSAGE:
    uv run alembic revision --autogenerate -m "{{MESSAGE}}"

db-upgrade:
    uv run alembic upgrade head

db-reset:
    uv run alembic downgrade base
    uv run alembic upgrade head
```

### Add Docker Support

```bash
# Docker tasks
docker-build:
    docker build -t {{app_name}}:latest .

docker-run:
    docker run -p 8000:8000 {{app_name}}:latest

docker-up:
    docker-compose up --build

docker-down:
    docker-compose down
```

### Add Documentation

```bash
# Documentation tasks
docs-serve:
    uv run mkdocs serve

docs-build:
    uv run mkdocs build

docs-deploy:
    uv run mkdocs gh-deploy
```

## Project Structure

Expected project structure:

```
my-project/
├── src/
│   └── myapp/
│       ├── __init__.py
│       └── main.py
├── tests/
│   └── test_main.py
├── pyproject.toml
├── justfile
└── README.md
```

## Integration with UV

This template uses UV for dependency management:

```bash
# Add dependencies
uv add requests pandas

# Add dev dependencies
uv add --dev pytest ruff mypy

# Update dependencies
uv sync --upgrade

# Dependencies are tracked in pyproject.toml
```

## Integration with Pre-commit

Setup pre-commit hooks:

```bash
# Install hooks
just setup

# Hooks run automatically on git commit
# Or run manually:
uv run pre-commit run --all-files
```

## Troubleshooting

**Issue: `just` command not found**
```bash
# Install Just
brew install just  # macOS
```

**Issue: `uv` command not found**
```bash
# Install UV
curl -LsSf https://astral.sh/uv/install.sh | sh
```

**Issue: Tests failing**
```bash
# Reset environment
just reset
just setup
```

## Related Templates

- [FastAPI Template](../fastapi/README.md) - For web APIs
- [CLI Template](../cli/README.md) - For command-line tools
- [ML Template](../ml/README.md) - For data science projects

## Blog Articles

- [One Justfile Template for All My Projects](https://dr-saad-la.github.io/polyglot-engineer-blog/blog/2026-01-29-one-justfile-template-for-all-my-projects/)
- [Getting Started with Just](https://dr-saad-la.github.io/polyglot-engineer-blog/blog/2026-01-28-getting-started-with-just/)

## Questions?

[Open an issue](https://github.com/dr-saad-la/polyglot-engineer-templates/issues) or email dr.saad.laouadi@gmail.com

---

**Part of The Polyglot Engineer Templates**

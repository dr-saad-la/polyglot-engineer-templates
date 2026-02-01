# Justfile Templates

Production-ready justfile templates for automating common development tasks.

## Overview

These templates use [Just](https://just.systems/) - a modern command runner that's simpler than Make and more powerful than shell scripts.

**Why Just?**
- Cross-platform (macOS, Linux, Windows)
- Simple syntax
- Better error messages than Make
- No tabs vs spaces issues

## Available Templates

### Python
**For:** General Python projects, libraries, packages

**Features:**
- UV package manager
- Ruff formatting & linting
- MyPy type checking
- Pytest with coverage
- Pre-commit hooks

[**Download →**](python/justfile) | [**Docs →**](python/README.md)

---

### FastAPI
**For:** REST APIs, microservices, web backends

**Features:**
- Everything from Python template
- Uvicorn development server
- Database migrations (Alembic)
- Docker support
- API testing

[**Download →**](fastapi/justfile) | [**Docs →**](fastapi/README.md)

---

### CLI
**For:** Command-line tools and utilities

**Features:**
- Everything from Python template
- Package building
- PyPI publishing
- CLI testing
- Documentation generation

[**Download →**](cli/justfile) | [**Docs →**](cli/README.md)

---

### ML/Data Science
**For:** Machine learning projects, data pipelines

**Features:**
- Everything from Python template
- Jupyter integration
- MLflow experiment tracking
- TensorBoard visualization
- DVC data versioning
- Model evaluation

[**Download →**](ml/justfile) | [**Docs →**](ml/README.md)

---

### General
**For:** Quick starts, minimal projects

**Features:**
- Minimal boilerplate
- Easy to customize
- Universal structure

[**Download →**](general/justfile) | [**Docs →**](general/README.md)

---

## Installation

### 1. Install Just
````bash
# macOS
brew install just

# Linux
curl --proto '=https' --tlsv1.2 -sSf https://just.systems/install.sh | bash -s -- --to /usr/local/bin

# Windows (via Cargo)
cargo install just

# Verify
just --version
````

### 2. Download Template
````bash
# Example: Python template
curl -o justfile https://raw.githubusercontent.com/dr-saad-la/polyglot-engineer-templates/main/justfile-templates/python/justfile
````

### 3. Customize

Edit configuration variables:
````bash
python_version := "3.12"    # Your version
app_name := "myapp"         # Your project name
````

### 4. Use
````bash
just             # See all commands
just setup       # First-time setup
just dev         # Start development
just test        # Run tests
just check       # Quality checks
````

## Common Recipes

All templates include these core recipes:

### Setup
- `just install` - Install dependencies
- `just setup` - Complete project setup

### Development
- `just dev` - Start development server/environment
- `just repl` - Interactive environment

### Code Quality
- `just format` - Format code
- `just lint` - Lint code
- `just types` - Type check
- `just check` - Run all checks

### Testing
- `just test` - Run tests
- `just test-cov` - Tests with coverage

### Cleanup
- `just clean` - Remove artifacts
- `just reset` - Complete reset

### Build
- `just build` - Build project
- `just deploy ENV` - Deploy to environment

### Utilities
- `just info` - Project information
- `just` (no args) - List all commands

## Customization

### Add New Recipes
````bash
# Custom recipe
my-command:
    @echo "Running my command..."
    # Add your commands here
````

### Variables
````bash
# Define variables
my_var := "value"

# Use in recipes
use-var:
    @echo "Variable: {{my_var}}"
````

### Parameters
````bash
# Recipe with parameters
greet NAME:
    @echo "Hello {{NAME}}!"

# Use: just greet World
````

### Dependencies
````bash
# Run other recipes first
deploy: check test build
    @echo "Deploying..."
````

## Best Practices

1. **Keep it simple** - Don't overcomplicate
2. **Use comments** - Document what recipes do
3. **Group related tasks** - Organize with sections
4. **Default to safe** - Add confirmation for destructive operations
5. **Self-document** - Use `@just --list` as default

## Examples

See [examples directory](../docs/examples/) for:
- Real-world customizations
- Project-specific recipes
- Integration examples

## Resources

- [Just Documentation](https://just.systems/)
- [Just GitHub](https://github.com/casey/just)
- [The Polyglot Engineer Blog](https://dr-saad-la.github.io/polyglot-engineer-blog)

## Questions?

[Open an issue](https://github.com/dr-saad-la/polyglot-engineer-templates/issues) or email dr.saad.laouadi@gmail.com

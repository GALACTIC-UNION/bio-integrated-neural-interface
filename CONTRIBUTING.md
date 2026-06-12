# Contributing Guide

Thank you for considering contributing to this project! This document outlines
the process for contributing code, documentation, and ideas.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Workflow](#development-workflow)
- [Coding Standards](#coding-standards)
- [Testing](#testing)
- [Pull Request Process](#pull-request-process)
- [Issue Reporting](#issue-reporting)

---

## Code of Conduct

All contributors are expected to uphold our [Code of Conduct](CODE_OF_CONDUCT.md).
Be respectful, inclusive, and collaborative.

---

## Getting Started

1. **Fork** this repository and clone your fork locally.
2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv .venv
   source .venv/bin/activate      # Linux/macOS
   .venv\Scripts\activate         # Windows
   pip install -r requirements.txt
   ```
3. Copy the example config:
   ```bash
   cp config/config.example.yaml config/config.yaml
   ```
4. Run the test suite to confirm everything is green:
   ```bash
   pytest tests/ -v
   ```

---

## Development Workflow

We use **GitHub Flow**:

1. Create a feature branch from `main`:
   ```bash
   git checkout -b feat/your-feature-name
   ```
2. Make your changes in small, logical commits.
3. Push your branch and open a **Pull Request** against `main`.
4. Address any review comments.
5. Once approved and CI passes, a maintainer will merge.

---

## Coding Standards

- Follow **PEP 8** for Python code (max line length: 120 chars).
- Use **type hints** on all public functions.
- Write **docstrings** for every module, class, and public function (Google style).
- Keep functions small and focused (single responsibility).
- No hardcoded credentials — use `config/` or environment variables.

---

## Testing

- All new features must include corresponding tests in `tests/`.
- Tests are written with `pytest`.
- Coverage target: **≥ 80 %** for new code.
- Run the full suite:
  ```bash
  pytest tests/ --cov=src --cov-report=term-missing
  ```

---

## Pull Request Process

1. Ensure CI passes (lint + tests).
2. Update `docs/` if the change affects public APIs or configuration.
3. Add an entry to `CHANGELOG.md` under the `[Unreleased]` section.
4. Request at least one review from a maintainer.
5. Do **not** merge your own PR without approval.

---

## Issue Reporting

When filing a bug report, include:

- **Environment**: OS, Python version, relevant dependency versions.
- **Steps to reproduce**: Minimal reproducible example.
- **Expected vs. actual behaviour**.
- **Logs / stack traces** (redact sensitive data).

For feature requests, describe the use-case and expected outcome clearly.

---

*Thank you for helping build a better future — one commit at a time.*

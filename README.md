# 🧪 Agent Test App

![CI](https://github.com/BlueprintTechnologies/agent-test-app-1/actions/workflows/python-ci.yml/badge.svg)
[![codecov](https://codecov.io/gh/BlueprintTechnologies/agent-test-app-1/branch/main/graph/badge.svg)](https://codecov.io/gh/BlueprintTechnologies/agent-test-app-1)

This is a simple Python application designed to support experimentation with GitHub Actions CI/CD pipelines and Databricks Mosaic AI agents.

## 🧰 What This App Does

This repo contains a basic calculator module with the following functionality:

- `add(a, b)`
- `subtract(a, b)`
- `multiply(a, b)`
- `divide(a, b)` *(raises `ValueError` on divide by zero)*

All logic lives in `app/calculator.py` and is tested via `pytest` in `tests/test_calculator.py`.

---

## 🧠 Why This Repo Exists

This repo is used as a **sandbox for building AI agents** that can:

- Assess CI/CD workflows for common issues and inefficiencies
- Automatically review pull requests and identify missing reviewers, vague titles, etc.
- Provide feedback on workflow completeness (e.g., are tests being run? Is the pipeline too manual?)

We are integrating these agents using the [Mosaic AI agentic framework](https://learn.microsoft.com/en-us/azure/databricks/generative-ai/tutorials/agent-framework-notebook) in Databricks.

---

## 🚦 How to Test Changes

### 🧪 CI/CD Workflow

This repo uses **GitHub Actions** to run tests automatically:

- ✅ On push to `main`
- ✅ On pull request to `main`

You can trigger it by:
1. Creating a pull request
2. Pushing a commit directly to `main`

Workflow file: `.github/workflows/python-ci.yml`

---

### 🧪 Unit Tests

To run tests locally:

```bash
pip install -r requirements.txt
pytest --cov=app --cov-branch --cov-report=xml
```

To view coverage details, the workflow uses [Codecov](https://codecov.io/gh/BlueprintTechnologies/agent-test-app-1):
- The badge above reflects current code coverage.
- After each CI run, coverage is uploaded and visible on the Codecov dashboard.
- Click the badge to explore uncovered lines or trends over time.

You can also explore coverage in your local dev environment:
```bash
open htmlcov/index.html
```

*(Requires running `coverage html` after tests)*
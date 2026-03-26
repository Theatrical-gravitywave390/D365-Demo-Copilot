# Contributing to D365 Demo Copilot

Thank you for your interest in contributing! This guide will help you get started.

## Development Setup

1. **Fork and clone** the repository:
   ```bash
   git clone https://github.com/<your-username>/D365-Demo-Copilot.git
   cd D365-Demo-Copilot/demo_agent
   ```

2. **Create a virtual environment**:
   ```bash
   python -m venv .venv
   source .venv/bin/activate        # macOS/Linux
   .venv\Scripts\Activate.ps1       # Windows
   ```

3. **Install dependencies** (including dev/test):
   ```bash
   pip install -r requirements.txt
   playwright install chromium
   ```

4. **Configure credentials**:
   ```bash
   cp .env.example .env
   # Edit .env with your D365 URL and LLM credentials
   ```

## Running Tests

```bash
# Unit tests (no D365 connection needed)
pytest demo_agent/tests/ -v --ignore=demo_agent/tests/test_e2e_time_entry.py

# E2E tests (requires D365 auth_state.json)
pytest demo_agent/tests/test_e2e_time_entry.py -v
```

## Code Style

- Python 3.10+ with type hints
- Use `async`/`await` for all I/O operations
- Follow existing patterns in the codebase
- Keep functions focused and under 50 lines where possible

## Pull Request Process

1. Create a feature branch from `main`:
   ```bash
   git checkout -b feature/your-feature
   ```

2. Make your changes and ensure tests pass.

3. Write clear commit messages describing the "why" not just the "what".

4. Open a pull request against `main` with:
   - A clear description of the change
   - Any relevant issue numbers
   - Screenshots/GIFs if the change affects the UI or overlays

## Reporting Bugs

Please use the [GitHub Issues](https://github.com/seangalliher/D365-Demo-Copilot/issues) tab with the bug report template.

## Feature Requests

Feature ideas are welcome! Open an issue using the feature request template.

## License

By contributing, you agree that your contributions will be licensed under the MIT License.

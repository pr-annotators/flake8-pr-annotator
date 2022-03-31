# Flake8 PR Annotator

## Usage

Annotate pull requests with flake8 errors detected during CI.

Note: This doesn't install or run flake8, it just sets up the PR annotations.

### Example workflow

```yaml
name: My Workflow
on: [push, pull_request]
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master

      - name: Set up Python 3.8
        uses: actions/setup-python@v2
        with:
          python-version: "3.8"
        
      - name: Install flake8
        run: |
          pip install flake8

      - name: Add flake8 annotator
        uses: jpy-git/flake8-pr-annotator@master

      - name: Run flake8
        run: |
          flake8 src/
```

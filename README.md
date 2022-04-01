# Flake8 PR Annotator

![demo](images/demo.png)

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
        uses: pr-annotators/flake8-pr-annotator@v1.0.0

      - name: Run flake8
        run: |
          flake8 src/
```

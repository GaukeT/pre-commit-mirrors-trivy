[![build status](https://github.com/GaukeT/pre-commit-mirrors-trivy/actions/workflows/main.yml/badge.svg)](https://github.com/GaukeT/pre-commit-mirrors-trivy/actions/workflows/main.yml)

# trivy-py

A python wrapper to provide a pip-installable [trivy] binary.

Internally this package provides a convenient way to download the pre-built
trivy binary for your particular platform.

### installation

```bash
pip install trivy-py
```

### usage

After installation, the `trivy` binary should be available in your
environment (or `trivy.exe` on windows).

### As a pre-commit hook

See [pre-commit] for instructions

Sample `.pre-commit-config.yaml`:
```yaml
- repo: https://github.com/GaukeT/pre-commit-mirrors-trivy
  rev: v0.67.2
  hooks:
    - id: trivy-fs
      args:
        - --exit-code=1 # Example: set exit with code 1
        - --debug # Example: enable debug output
        - . # Example: scan current directory (provide DIR as last argument if `args` are used)
    - id: trivy-config
```

[trivy]: https://trivy.dev/
[pre-commit]: https://pre-commit.com

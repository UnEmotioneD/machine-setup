# Pyright

Fix import autocompletion by the LSP not getting the correct path when the `.git` directory
and the actual project root do not match.

## Reference

- [pyright configuration](https://github.com/microsoft/pyright/blob/main/docs/configuration.md)

---

## Configuration

Inside `pyrightconfig.json`:

```jsonc
{
  // Virtual environment configuration
  "venvPath": ".", // Look for virtual environments in current directory
  "venv": ".venv", // Virtual environment folder name

  // File inclusion/exclusion
  "include": ["app", "run.py"], // Files and folders to type check
  "exclude": ["**/__pycache__", ".venv"], // Skip these paths

  // Execution environment
  "executionEnvironments": [
    {
      "root": ".", // Set project root to current directory for import resolution
    },
  ],

  // Type checking rules
  "reportMissingImports": true, // Warn when imports can't be resolved
  "reportMissingTypeStubs": false, // Ignore missing type stubs for third-party libraries

  // Python configuration
  "pythonVersion": "3.12", // Target Python version
  "typeCheckingMode": "basic", // Options: "off" | "basic" | "strict"
}
```

---

## Pyproject

`pyproject.toml` for a unified configuration file:

```toml
[tool.pyright]
venvPath = "."
venv = ".venv"
include = ["app", "run.py"]
exclude = ["**/__pycache__", ".venv"]
reportMissingImports = true
reportMissingTypeStubs = false
pythonVersion = "3.12"
typeCheckingMode = "basic"
```

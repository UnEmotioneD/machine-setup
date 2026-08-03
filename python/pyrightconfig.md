# Pyright config

[pyright docs](https://github.com/microsoft/pyright/blob/main/docs/configuration.md)

---

## pyrightconfig

To fix auto import issue, create `pyrightconfig.json` file at the project root:

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

## pyproject

`pyproject.toml` for unified configuration file

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

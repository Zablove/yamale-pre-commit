# Collection of git hooks for Yamale to be used with [pre-commit framework](http://pre-commit.com/)

[![Github tag](https://img.shields.io/github/tag/k-ogawa-1988/yamale-pre-commit.svg)](https://github.com/k-ogawa-1988/yamale-pre-commit/releases)

## How to install

### 1. Install dependencies

* [`pre-commit`](https://pre-commit.com/#install)
* [`yamale`](https://github.com/23andMe/Yamale) < Use this link for examples
* [`pyyaml`](https://github.com/yaml/pyyaml) or [`ruamel`](https://yaml.readthedocs.io/en/latest/)

### 2. Add configs and hooks
Step into the repository you want to have the pre-commit hooks installed and edit `.pre-commit-config.yaml`:

```yaml
repos:
- repo: 'https://github.com/Zablove/yamale-pre-commit/'
  rev: <VERSION> # Get the latest from: https://github.com/Zablove/yamale-pre-commit/releases
  hooks:
    - id: 'yamale-validate'
```

with options:

```yaml
repos:
- repo: 'https://github.com/Zablove/yamale-pre-commit/'
  rev: <VERSION> # Get the latest from: https://github.com/Zablove/yamale-pre-commit/releases
  hooks:
    - id: 'yamale-validate'
      args:  # Describe below
        - '--exclude=venv'
        - '--exclude=node_modules'
      files: 'example.yml'  # For example only to check example.yml 
```

### 3. Run

After pre-commit hook has been installed you can run it manually on all files in the repository

```bash
pre-commit run -a
```

## Configuration

All yamale validation rules can be specified in the .yamale-validate-schema.yaml file.

### Examples

You can find examples for a schema at: [`yamale`](https://github.com/23andMe/Yamale)

## Authors

This repository is managed by [ZabLove](https://github.com/Zablove/).  
Credits for the original repo to [Ken'ichi Ogawa](https://github.com/k-ogawa-1988)
Any forks or pull requests are welcome!

## License

MIT licensed. See LICENSE for full details.

# Corgea Blast Action

This action runs Corgea Blast to scan your code for security vulnerabilities and code quality issues.

## Inputs

- `token` (required): Your Corgea API token
- `url` (optional): Corgea API URL (for on-premises deployments)
- `fail-on` (optional): Fail the action on a specific severity level (CR, HI, ME, LO)
- `fail` (optional): Fail based on blocking rules defined in web app (default: false)
- `version` (optional): Version of Corgea CLI to install (default: latest)
- `project-path` (optional): Path to the project to scan, useful for monorepos (default: .)

## Example Usage

Basic usage:

```yaml
name: Security Scan
on: [push]

jobs:
  security:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - name: Run Corgea Blast
        uses: @corgea/actions/blast@v1
        with:
          token: ${{ secrets.CORGEA_TOKEN }}
          fail: true
```

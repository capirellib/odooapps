# AGENTS.md

## Repository
- **Fork** of <https://github.com/odoomates/odooapps> (upstream)
- Work on branch `19.0` — do not commit to `18.0`, `18.0-betta`, `19.0_conciliacion`
- Upstream compatibility matters: prefer XPath inheritance for view changes to avoid merge conflicts
- Author attribution: `Odoo Mates, Odoo SA` / maintainer `Odoo Mates`

## Modules (11 addons)
- `om_account_accountant` — umbrella applicative module; depends on all other accounting modules
- `om_data_remove` — standalone data cleanup tool; depends only on `base`
- `om_hr_payroll_account` — depends on `om_hr_payroll` + `account`
- All others depend on `account` (+ `mail` for followup, `accounting_pdf_reports` for daily reports)

## Development
- **No tests** — no `tests/` directory in any module
- **No CI/CD, no linting, no pre-commit, no type checking**
- **No build system** — pure addons, no package.json/pyproject.toml/setup.py
- Only demo data: `om_account_followup/demo/demo.xml`
- VS Code: XML symbols disabled (`.vscode/settings.json`)
- Commit prefix convention: `[IMP]`, `[FIX]`, `[ADD]`, `[REM]`, `[MIG]`, `chore:`
- All modules are LGPL-3 licensed
- Target Odoo **19** (`19.0` branch); use `betta-odoo-workflow`, `odoo-19`, and `odoo-development` skills as reference
- If you detect recurring conceptual errors in our codebase, update the `odoo-development` skill so we do not repeat them

## Translation
- PO files checked in directly under `i18n/` per module
- `es_AR` (Argentina Spanish) is the primary translation target
- Source strings in English per Odoo convention

# Final Year Project - Inventory Management System (IMS)

This repository contains a desktop Inventory Management System built with Python, Tkinter, and SQLite.

## Features

- Employee, supplier, category, and product management
- Billing and sales workflow
- SQLite database initialization via script
- Encrypted storage for selected sensitive fields
- OTP-based password reset flow via SMTP

## Tech Stack

- Python 3
- Tkinter (GUI)
- SQLite
- `cryptography` (Fernet encryption)

## Project Structure

- `login.py`: main entry point
- `create_db.py`: database and table initialization
- `dashboard.py`, `employee.py`, `supplier.py`, `category.py`, `product.py`, `billing.py`, `sales.py`: app modules
- `script.sql`: SQL schema reference
- `config.json`: SMTP credentials (local, do not commit real values)
- `config.example.json`: template for SMTP credentials
- `bill/`: generated bill text output
- `tests/`: unit and GUI test scripts

## Setup

1. Install Python 3.10+.
2. Create and activate a virtual environment.
3. Install dependencies:

```bash
pip install cryptography
```

4. Configure email credentials for OTP:
   - Copy `config.example.json` to `config.json` (if needed).
   - Set:
     - `email`: Gmail address used to send OTPs
     - `password`: Gmail app password (not your normal account password)

## Run

```bash
python login.py
```

On first launch, the app creates `ims.db` automatically and prompts for initial admin creation if no admin exists.

## Tests

This project includes test scripts under `tests/`, including:

- Unit tests for database, login, billing, and encryption classes
- GUI automation tests

Test files are not fully standardized for one-command execution, but they can be run directly, for example:

```bash
python "tests/Unit Testing/CryptoManagerClass/encrypt_decrypt.py"
```

## Security Notes

- Do not commit real credentials in `config.json`.
- `secret.key`, `ims.db`, and generated bills are ignored by `.gitignore`.
- If credentials were previously committed, rotate them immediately.

## Maintenance

Recommended regular maintenance:

- Keep dependencies updated (`cryptography` in particular).
- Periodically review committed files for secrets.
- Keep diagrams and documentation aligned with code changes.

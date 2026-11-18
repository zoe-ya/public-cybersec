# Python for Security: Starter Toolkit

Three small Python tools I built to practice core security concepts: hashing, network discovery, and password risk checks. Each notebook runs on its own and explains what it does and why it matters.

| # | Notebook | What it does | Security concept |
|---|---|---|---|
| 1 | [`day1-password-hasher.ipynb`](day1-password-hasher.ipynb) | Hashes a string with SHA-256 | Why systems store hashes, not passwords |
| 2 | [`day2-simple-scanner.ipynb`](day2-simple-scanner.ipynb) | Fast port and service scan with `python-nmap` (top 100 ports, version detection) | Asset discovery and attack surface |
| 3 | [`day3_password-strength.ipynb`](day3_password-strength.ipynb) | Scores password length and character mix, checks a common-password list, and checks Have I Been Pwned | Credential risk and k-anonymity |

## Highlights
- **Privacy-safe breach check.** The analyzer sends only the first 5 characters of the password's SHA-1 hash to the Have I Been Pwned API (k-anonymity), so the password never leaves the machine.
- **Authorized targets only.** The scanner targets `scanme.nmap.org`, which Nmap provides for legal practice scanning.
- **Input masking.** Passwords are shown as asterisks in output.

## How to run
```bash
pip install python-nmap requests jupyter
# Nmap must also be installed: https://nmap.org/download
jupyter notebook
```

## What I'd improve next
- Use a salted, slow hash (bcrypt or Argon2) instead of plain SHA-256 for password storage.
- Export scan results to CSV for vulnerability tracking.
- Add handling for timeouts and API errors instead of silently passing.

## About me
Elise Aleman. M.S. Cyber Defense student at Dakota State University. Background in Security Operations Center (SOC) analysis and IT support. [LinkedIn](https://www.linkedin.com/in/cyberelise)

> Practice code for learning. Only scan systems you own or have written permission to test.

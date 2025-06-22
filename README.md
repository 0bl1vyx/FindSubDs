# 🔍 FindSubDs

A powerful and user-friendly **Subdomain Enumeration Tool** built for OSINT-based recon, combining multiple top subdomain discovery engines like `subfinder`, `assetfinder`, `sublist3r`, `crt.sh`, and `findomain`. It resolves subdomains using `dnsx` and detects live web hosts via `httpx`. Enhanced with animated CLI banners, spinners, and detailed stage indicators.

---

## 🚀 Features

- 🔗 Aggregates results from 5 powerful sources:
  - `subfinder`, `assetfinder`, `sublist3r`
  - Certificate transparency logs via `crt.sh`
  - Passive DNS via `findomain`
- 📦 Automatically deduplicates and cleans results
- 🌐 Resolves domains via `dnsx`
- 🔎 Checks for live HTTP/S endpoints via `httpx`
- 🎨 Fully interactive and colorful CLI:
  - Loading spinners for each stage
  - ASCII banners and countdowns
- 💾 Generates 2 output files:
  - All discovered subdomains
  - Only live & resolved subdomains

---

## 🛠️ Prerequisites

Install the required tools and dependencies:

```bash
# Install system dependencies
sudo apt install -y curl jq subfinder sublist3r assetfinder dnsx findomain

# Install Go-based tools
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
````

Ensure all tools are in your `$PATH`.

---

## ⚙️ Usage

```bash
git clone https://github.com/cryptspecter/FindSubDs.git
cd FindSubDs
chmod +x FindSubDs

./FindSubDs -d example.com -o subdomains.txt -l live_subs.txt
```

* `-d` — Target domain
* `-o` — Output file for all discovered subdomains
* `-l` — Output file for live subdomains

---

## 📂 Output Files

| File             | Description                            |
| ---------------- | -------------------------------------- |
| `subdomains.txt` | All unique subdomains found            |
| `live_subs.txt`  | Subdomains with active HTTP/S services |

---

## 🧠 Notes

* Internet is required for OSINT and resolution queries.
* Tool checks ensure all dependencies are present before execution.
* Best run on Linux/macOS terminals with support for ANSI escape sequences.

---

## 📜 License

MIT License — use it, modify it, contribute to it.

---

## 👤 Author

**[Priyo (Crypt Specter)](https://github.com/cryptspecter)**
Ethical Hacker & Bug Bounty Hunter

---

## 🤝 Contribution

Pull requests, improvements, bug fixes, and suggestions are welcome!
Please follow responsible disclosure norms and ethics.

---

## ⚠️ Disclaimer

This tool is built **only for legal and authorized security testing**.
Unauthorized scanning or probing of systems without consent is **illegal** and unethical.

---

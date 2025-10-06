# 🔍 FindSubDs - The Ultimate Subdomain Enumerator

**FindSubDs** is a powerful and lightning-fast Bash script that automates the process of subdomain enumeration. It intelligently orchestrates a suite of the best open-source tools to discover, resolve, and verify subdomains, presenting the results in a clean, user-friendly interface.

This tool was designed to be the perfect first step in any reconnaissance workflow for bug bounty hunters, penetration testers, and security researchers.

---

## ✨ Features

-   **Multi-Source Enumeration**: Aggregates results from multiple industry-standard tools (`Subfinder`, `Assetfinder`, `Findomain`, `Sublist3r`) and data sources (`crt.sh`, `Web Archive`) for maximum coverage.
-   **Blazing Fast Performance**: Executes all enumeration tools in **parallel**, dramatically reducing scan time.
-   **Smart & Efficient Workflow**: Resolves found domains with `dnsx` before probing for live hosts with `httpx`, ensuring that only valid domains are checked.
-   **Polished User Experience**: A modern, clean interface with spinners, color-coded output, and a clear summary keeps you informed at every stage.
-   **Dependency Check**: Automatically verifies that all required tools are installed before running to prevent mid-scan failures.
-   **Safe & Simple**: Written in pure Bash with no complex installation required. Just clone and run!

---

## 🛠️ Installation

FindSubDs is a Bash script and doesn't require compilation, but you need to install the open-source tools it relies on.

**1. Clone the Repository:**

```bash
wget https://raw.githubusercontent.com/0bl1vyx/FindSubDs/refs/heads/main/FindSubDs
chmod +x FindSubDs
```

**2. Install Dependencies:**

The easiest way to install the required tools is through your system's package manager, supplemented by `go` for the latest versions.

### Easy Install (Recommended for Debian, Ubuntu, Kali, etc.)

This single command will install most of the required tools from the official repositories.

```bash
sudo apt update && sudo apt install -y massdns curl jq subfinder sublist3r assetfinder dnsx findomain
```

The `httpx & puredns` tool is best installed with `go` to ensure you have the latest version:

```bash
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
go install github.com/d3mondev/puredns/v2@latest
```
---

## 🚀 Usage

The script is simple to run. Provide a target domain, an output file for all found subdomains, and an output file for live subdomains.

**Basic Syntax:**

```bash
./findsubds.sh -d <domain.com> -o <all_subs.txt> -l <live_subs.txt>
```

**Example:**

```bash
./findsubds.sh -d hackerone.com -o subs.txt -l live.txt
```

### Arguments

| Flag | Description                    | Example              |
| :--- | :----------------------------- | :------------------- |
| `-d` | **Domain** to scan for subdomains. | `-d example.com`     |
| `-o` | **Output** file for all unique subdomains. | `-o all_domains.txt` |
| `-l` | **Live** output file for reachable (HTTP/HTTPS) subdomains. | `-l live_hosts.txt`  |

---

## 🤝 Contributing

Contributions are welcome! If you have an idea for a new feature, find a bug, or want to improve the script, feel free to open an issue or submit a pull request.

---

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

## ⚠️ Disclaimer

This tool is intended for ethical testing and security research purposes only. Do not use it on any system without explicit permission. The author is not responsible for any misuse or damage caused by this script.

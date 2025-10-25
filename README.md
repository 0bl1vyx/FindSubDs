# 🔍 FindSubDs - The Ultimate Subdomain Enumerator (v2.7)

**FindSubDs** is a powerful and lightning-fast Bash script that automates the process of subdomain enumeration. It intelligently orchestrates a suite of the best open-source tools to discover, resolve, and verify subdomains, presenting the results in a clean, user-friendly interface.

This tool was designed to be the perfect first step in any reconnaissance workflow for bug bounty hunters, penetration testers, and security researchers.

-----

## ✨ Features

  - **Multi-Source Enumeration**: Aggregates results from industry-standard passive tools (`Subfinder`, `Findomain`) for wide coverage.
  - **Optional Brute-Forcing**: Integrate `puredns` with your custom wordlists to discover unlinked subdomains.
  - **Optional Permutations**: Use `alterx` to generate and resolve potential subdomain permutations.
  - **Blazing Fast Performance**: Executes enumeration tools in **parallel**, dramatically reducing scan time.
  - **Smart & Efficient Workflow**: Features an intelligent resolution engine. It avoids re-resolving domains already confirmed by brute-force or permutation, running `dnsx` only on the remaining passive-only results.
  - **Polished User Experience (v2.7)**: A modern, clean interface with spinners, color-coded output, and a clear summary keeps you informed at every stage.
  - **Verbose Mode**: A `-v` flag to disable spinners and see the raw output from all underlying tools for debugging.
  - **Dependency Check**: Automatically verifies that all required tools are installed before running to prevent mid-scan failures.
  - **Safe & Simple**: Written in pure Bash with no complex installation required. Just clone and run\!

-----

## 🛠️ Installation

FindSubDs is a Bash script and doesn't require compilation, but you need to install the open-source tools it relies on.

**1. Clone the Repository:**

```bash
wget https://raw.githubusercontent.com/0bl1vyx/FindSubDs/refs/heads/main/FindSubDs
chmod +x FindSubDs
```

**2. Install Dependencies:**

FindSubDs relies on a set of powerful Go-based tools. You must install: `subfinder`, `findomain`, `dnsx`, `httpx`, `puredns`, and `alterx`.

### Using Go (Recommended)

This method ensures you have the latest versions of all tools. You must have [Go installed](https://go.dev/doc/install) and configured.

```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
go install -v github.com/findomain/findomain@latest
go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
go install -v github.com/d3mondev/puredns/v2@latest
go install -v github.com/projectdiscovery/alterx/cmd/alterx@latest
```

### Using APT (Debian/Ubuntu/Kali)

You can use `apt` to install the tools, though the versions in the official repositories may be older.

```bash
sudo apt update && sudo apt install -y subfinder findomain dnsx httpx puredns alterx
```

-----

## 🚀 Usage

The script is simple to run. Provide a target domain and output files. You can add optional flags for more advanced enumeration.

**Basic Syntax:**

```bash
./FindSubDs -d <domain.com> -o <all_subs.txt> -l <live_subs.txt>
```

**Full-Featured Example:**

This runs a passive scan, brute-force, and permutation checks, all in verbose mode.

```bash
./FindSubDs -d hackerone.com -o subs.txt -l live.txt -w /path/to/wordlist.txt -r /path/to/resolvers.txt -p -v
```

### Arguments

| Flag | Description | Example |
| :--- | :--- | :--- |
| `-d` | **Domain** to scan for subdomains. | `-d example.com` |
| `-o` | **Output** file for all unique subdomains. | `-o all_domains.txt` |
| `-l` | **Live** output file for reachable (HTTP/HTTPS) subdomains. | `-l live_hosts.txt` |
| `-w` | **(Optional)** Path to a **Wordlist** for `puredns` brute-forcing. | `-w common.txt` |
| `-r` | **(Optional)** Path to a file of **Resolvers** for `puredns`. | `-r resolvers.txt` |
| `-p` | **(Optional)** Run subdomain **Permutations** with `alterx`. | `-p` |
| `-v` | **(Optional)** **Verbose** mode. Disables spinners and shows tool output. | `-v` |
| `-h` | **(Optional)** Display the help menu. | `-h` |

-----

## 🤝 Contributing

Contributions are welcome\! If you have an idea for a new feature, find a bug, or want to improve the script, feel free to open an issue or submit a pull request.

-----

## 📜 License

This project is licensed under the MIT License. See the [LICENSE](https://www.google.com/search?q=LICENSE) file for details.

-----

## ⚠️ Disclaimer

This tool is intended for ethical testing and security research purposes only. Do not use it on any system without explicit permission. The author is not responsible for any misuse or damage caused by this script.

# FindSubDs

A powerful and user-friendly **Subdomain Enumeration Tool** that combines multiple popular OSINT tools — `subfinder`, `assetfinder`, and `sublist3r` — to maximize subdomain discovery. It further resolves subdomains using `dnsx` and identifies live hosts using `httpx`.

---

## Features

- Aggregates subdomains from multiple tools for maximum coverage  
- Filters and deduplicates subdomains automatically  
- Resolves subdomains to valid hosts via `dnsx`  
- Identifies live HTTP/S hosts via `httpx`  
- Interactive and colorful CLI with spinners, banners, and stage indicators  
- Outputs two files:
  - All unique subdomains (user-defined output file)  
  - Live subdomains (`live_subs.txt`)  

---

## Prerequisites

Make sure the following tools are installed and in your `$PATH`:

- [subfinder](https://github.com/projectdiscovery/subfinder) 
- [assetfinder](https://github.com/tomnomnom/assetfinder)  
- [sublist3r](https://github.com/aboul3la/Sublist3r)  
- [dnsx](https://github.com/projectdiscovery/dnsx)  
- [httpx](https://github.com/projectdiscovery/httpx)  

```bash
sudo apt install -y subfinder sublist3r assetfinder dnsx

go install -v github.com/projectdiscovery/httpx/cmd/httpx@latest
```

---

## Usage

```bash
git clone https://github.com/cryptspecter/FindSubDs.git
cd FindSubDs
chmod +x FindSubDs

./FindSubDs -d example.com -o subdomains.txt -l live_subs.txt
```

- `-d` — Target domain  
- `-o` — Output file for all unique discovered subdomains
- `-l` _ Output file for all live subdomains

---

## Output

- `subdomains.txt` — All unique subdomains discovered  
- `live_subs.txt` — Verified live subdomains  

---

## Notes

- Requires internet connection to query APIs and resolve hosts  
- Ensure you have permission to perform reconnaissance on target domains  
- Run on Linux/macOS terminals with Bash  

---

## License

MIT License — feel free to use and modify.

---

## Author

[Priyo](https://github.com/cryptspecter) — Ethical Hacker & Bug Bounty Hunter

---

## Contribution

Pull requests and issues are welcome. Please follow responsible disclosure practices.

---

## Disclaimer

This tool is designed for authorized security testing only. Unauthorized scanning or enumeration of domains may be illegal.

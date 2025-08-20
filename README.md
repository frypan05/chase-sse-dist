# chase-sse-dist
Public Distribution Command Line Tool

# 🔍 Chase SSE - Scientific Search Engine CLI

[![GitHub Release](https://img.shields.io/github/v/release/frypan05/chase-sse-dist)](https://github.com/frypan05/chase-sse-dist/releases)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Platforms](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-blueviolet)]()

> Lightning-fast command-line tool for discovering scientific literature across multiple databases.

## 📦 Installation

### Windows (Recommended)
1. Download the latest installer from [Releases page](https://github.com/frypan05/chase-sse-dist/releases)
2. Run `chase-sse-setup-<version>.exe`
3. Check "Add to PATH" during installation

### macOS/Linux
```bash
# Install via curl (auto-detects your OS)
curl -fsSL https://github.com/frypan05/chase-sse-dist/releases/latest/download/install.sh | bash

# Manual installation
curl -LO https://github.com/frypan05/chase-sse-dist/releases/download/v2.1.8/chase-sse
chmod +x chase-sse
sudo mv chase-sse /usr/local/bin/
```
🚀 Quick Start
```bash
# Search for papers
chase-sse search "quantum computing" --limit 5

# View paper details
chase-sse view arxiv:2103.0001v1

# Download PDF
chase-sse download arxiv:2103.0001v1 --output ~/papers

# List recent searches
chase-sse history
⚙️ Configuration
Create ~/.chase-sse/config.yaml:

yaml
# Required API Keys
api_keys:
  arxiv: your_email@domain.edu  # Recommended for higher rate limits
  ieee: xxxxx-xxxxx-xxxxx

# Default Settings
defaults:
  limit: 10                   # Results per query
  timeout: 30                 # Seconds
  download_dir: ~/Documents/papers
  databases: [arxiv, ieee]    # Search priority

# UI Preferences
ui:
  color: true
  emoji: true
  progress_bars: true
```
🔍 Advanced Usage
Batch Processing
```bash
# Search and download multiple papers
chase-sse search "generative AI" --limit 3 --json | jq '.[].id' | xargs -n1 chase-sse download
```
Custom Output Formats
```bash
# JSON output
chase-sse search "neural networks" --json

# CSV output
chase-sse search "crispr" --format csv > results.csv

# BibTeX export
chase-sse view arxiv:2103.0001v1 --bibtex >> references.bib
```
📚 Supported Databases
Database	ID Prefix	API Key Required
ArXiv	arxiv:	Email recommended
IEEE Xplore	ieee:	Yes
PubMed	pmid:	No
Google Scholar	gs:	No
🛠️ Building from Source
```bash
# Prerequisites: GCC, CMake, cURL development libraries
git clone https://github.com/frypan05/chase-sse-dist.git
cd chase-sse-dist
mkdir build && cd build
cmake .. -DCMAKE_BUILD_TYPE=Release
make -j4
sudo make install
```
❓ Troubleshooting
```bash
# Enable debug logging
chase-sse --verbose search "your query"

# Reset configuration
rm -rf ~/.chase-sse/cache
```
🤝 Contributing
Report issues on our Issue Tracker

For security issues, please email dakshsharma05@outlook.com

📜 License
MIT License - See LICENSE for details.

Maintained with ❤️ by Daksh Sharma

text

This README includes:
1. **Visual badges** for quick scanning
2. **Multiple installation methods** for all platforms
3. **Practical examples** with common use cases
4. **Complete configuration** reference
5. **Advanced usage** patterns
6. **Database reference table**
7. **Build instructions** for developers
8. **Troubleshooting** section
9. **Contributing** guidelines

Would you like me to add any of these sections?
- Video demo embed
- Performance benchmarks
- API endpoint documentation
- Citation instructions for academic use

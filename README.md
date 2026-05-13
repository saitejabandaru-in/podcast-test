<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:8B5CF6,100:6366F1&height=180&section=header&text=Podcast%20RSS%20Generator&fontSize=38&fontColor=E6EEF3&animation=fadeIn&fontAlignY=45" />
</p>

<p align="center">
  🎙️ YAML to RSS Automation &nbsp;|&nbsp; 📡 iTunes Compatible &nbsp;|&nbsp; ✨ Multi-Episode Support
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.6+-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/Format-RSS%202.0-brightgreen?style=flat-square"/>
  <img src="https://img.shields.io/badge/iTunes-Compatible-red?style=flat-square"/>
  <img src="https://img.shields.io/badge/PyPI-podcast--rss--generator-blue?style=flat-square"/>
  <img src="https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square"/>
  <img src="https://img.shields.io/badge/Status-Production%20Ready-success?style=flat-square"/>
</p>

---

# 🎙️ Podcast RSS Generator

A **lightweight Python tool** that transforms podcast metadata from **YAML** into **production-ready RSS feeds** compatible with all major podcast platforms: Apple Podcasts, Spotify, Google Podcasts, and more.

Write your podcast config once in human-readable YAML. Generate standards-compliant RSS feeds instantly. Deploy to any podcast directory.

---

## 🧠 What This System Does

```
feed.yaml (Your Podcast Config)
        ↓
podcast-rss-generator (CLI Tool)
        ↓
podcast.xml (RSS Feed)
        ↓
✔ Apple Podcasts
✔ Spotify
✔ Google Podcasts
✔ Any RSS Reader
✔ Your Website
```

No more manual XML editing. No more broken podcast feeds. Just YAML + Python + RSS.

---

## ⚙️ Key Features

✔ **Simple YAML Configuration** - Human-readable podcast & episode metadata  
✔ **RSS 2.0 Standard** - Full compliance with podcast specifications  
✔ **iTunes Integration** - Category, artwork, duration, and author metadata  
✔ **Multi-Episode Support** - Unlimited episodes with audio file management  
✔ **Dynamic URLs** - Configurable base URL for all asset links  
✔ **UTF-8 Encoding** - Proper character encoding for international characters  
✔ **Version Control Friendly** - Keep your feed in git, track every change  

---

## 🗂️ Project Structure

```
podcast-test/
├── podcast_rss_generator/      # 📦 Main package
│   ├── __init__.py             # Package exports & version
│   ├── generator.py            # Core RSS generation engine
│   └── cli.py                  # Command-line interface
│
├── tests/                      # 🧪 Test suite
│   ├── __init__.py
│   └── conftest.py
│
├── feed.yaml                   # 📋 Example config (you edit this)
├── podcast.xml                 # 📡 Generated RSS feed (output)
│
├── pyproject.toml              # 🔧 Modern package config (PEP 517/518)
├── setup.py                    # 🔧 Traditional setup config
├── MANIFEST.in                 # 📦 File inclusion rules
├── requirements.txt            # 📦 Production dependencies
├── requirements-dev.txt        # 🛠️ Development dependencies
│
├── README.md                   # 📖 This file
├── INSTALLATION.md             # 💾 Installation guide
├── PACKAGE_DESCRIPTION.md      # 📝 Full package overview
├── PYPI_PUBLISHING_GUIDE.md    # 🚀 How to publish to PyPI
├── PROJECT_SUMMARY.md          # 🎯 Enhancement summary
├── LICENSE                     # 📄 MIT License
```

---

## 📥 Installation

### Option 1: Install from PyPI (Recommended)

```bash
pip install podcast-rss-generator
```

Then use the CLI:

```bash
podcast-rss-generator --input feed.yaml --output podcast.xml
```

### Option 2: Install from Source

```bash
git clone https://github.com/saitejabandaru-in/podcast-test.git
cd podcast-test
pip install -e .
```

### Option 3: Run Locally

```bash
pip install pyyaml
python feed.py
```

---

## 💻 Usage

### Command Line Interface

```bash
# Using default filenames (feed.yaml → podcast.xml)
podcast-rss-generator

# Custom input/output
podcast-rss-generator --input my-podcast.yaml --output my-feed.xml

# Show help
podcast-rss-generator --help

# Show version
podcast-rss-generator --version
```

### Python API

```python
from podcast_rss_generator import generate_rss_feed

# Generate RSS feed from YAML
output_path = generate_rss_feed("feed.yaml", "podcast.xml")
print(f"✅ Feed generated: {output_path}")
```

---

## 📝 Configuration Guide

### Podcast Metadata (Top Level)

```yaml
title: Your Podcast Title              # Display name
subtitle: Your Tagline                 # Short description (1-2 lines)
author: Your Name                      # Podcast host/creator
description: Full description          # Complete podcast description
link: https://example.com              # Base URL (prepended to all paths)
image: /images/artwork.jpg             # Podcast artwork path
language: en-us                        # Language code (en-us, es-es, etc.)
category: Technology                   # iTunes category
format: audio/mpeg                     # Audio format (usually audio/mpeg)
```

### Episodes Section

Add episodes to the `item` array. Each episode needs:

```yaml
item:
  - title: "Episode Title"                           # Display name
    description: "What this episode is about"        # Episode description
    published: "Thu, 12 Jan 2023 18:00:00 GMT"       # RFC 2822 format
    file: /audio/episode.mp3                         # Audio file path (relative to link)
    duration: "00:45:30"                             # Length in HH:MM:SS
    length: 54567123                                 # File size in bytes
```

**Publication Date Format:** Must follow RFC 2822 (e.g., `Thu, 12 Jan 2023 18:00:00 GMT`)

---

## 🔄 Workflow

### Step 1: Edit Configuration
Edit `feed.yaml` with your podcast details and episodes:

```bash
nano feed.yaml
# or use VSCode, Sublime, or your favorite editor
```

### Step 2: Generate Feed
Use the CLI command:

```bash
podcast-rss-generator --input feed.yaml --output podcast.xml
```

Or use the Python API:

```python
from podcast_rss_generator import generate_rss_feed
generate_rss_feed("feed.yaml", "podcast.xml")
```

### Step 3: Deploy
Upload `podcast.xml` to your web server and submit the feed URL to podcast platforms:
- Apple Podcasts
- Spotify
- Google Podcasts
- All RSS directory services

---

## 💡 Usage Examples

### Example 1: Adding a New Episode

```yaml
  - title: "EP06-New Topic"
    description: "Deep dive into the latest trends"
    published: "Thu, 16 Feb 2023 18:00:00 GMT"
    file: /audio/TFIT06.mp3
    duration: "00:35:00"
    length: 42000000
```

Then run:
```bash
podcast-rss-generator
```

### Example 2: Updating Podcast Title

```yaml
title: "The Future in Tech - Season 2"
subtitle: "Advanced Topics & Expert Interviews"
```

Re-run the generator → all episodes inherit new metadata.

### Example 3: Changing the Base URL

```yaml
link: https://mynewsite.com
```

All episode audio paths automatically prepend the new URL:
- `/audio/ep1.mp3` → `https://mynewsite.com/audio/ep1.mp3`

---

## 📈 What This Project Demonstrates

✔ Professional Python package structure (PEP 517/518)  
✔ CLI development with argparse  
✔ YAML configuration management  
✔ XML generation from structured data  
✔ RSS/podcast standards knowledge  
✔ iTunes integration and compatibility  
✔ Clean, modular Python scripting  
✔ Version-controlled podcast distribution  
✔ PyPI package publishing  

---

## 🧪 Tech Stack

* **Python:** 3.6+
* **Runtime:** PyYAML, xml.etree.ElementTree (stdlib)
* **Development:** setuptools, pytest, black, flake8, twine

---

## 📋 Requirements

- **Python:** 3.6 or higher
- **Dependencies:** pyyaml (auto-installed with package)
- **Workflow:** YAML config file + valid podcast metadata
- **Hosting:** Audio files accessible from your base URL

---

## 📚 Documentation

| Document | Purpose |
|----------|---------|
| **README.md** | Main guide & examples (this file) |
| **INSTALLATION.md** | Setup instructions |
| **PACKAGE_DESCRIPTION.md** | Full package overview |
| **PYPI_PUBLISHING_GUIDE.md** | How to publish to PyPI |
| **PROJECT_SUMMARY.md** | What was improved

---

## � Workflow Tips

1. **Version Control** - Keep `feed.yaml` in git, track all episode changes
2. **Validate Feed** - Use [podtrac.com](https://podtrac.com) or [podbase.io](https://podbase.io) to validate
3. **Host the XML** - Upload `podcast.xml` to your web server
4. **Submit URLs** - Most platforms accept your feed URL (e.g., `https://yourdomain.com/podcast.xml`)
5. **Update Regularly** - Edit `feed.yaml`, run `podcast-rss-generator`, redeploy
6. **Test Locally** - Keep multiple copies for testing different configurations

---

## 👨‍💻 Author

**Sai Teja Bandaru**  
Data Scientist & Open Source Developer

🌐 [https://www.saitejabandaru.com/](https://www.saitejabandaru.com/)

---

## 📄 License

MIT License — see `LICENSE` for details.

---

## ⭐ Support

If you find this useful:

⭐ **Star the repo** — helps others discover it  
🍴 **Fork it** — build on it for your use case  
🐛 **Report issues** — help improve the tool  

---

> Building automation-driven workflows for content creators.


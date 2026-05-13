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
  <img src="https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square"/>
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
   feed.py Script
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
├── feed.py             # Main script - YAML → XML conversion
├── feed.yaml           # Podcast config & episodes (you edit this)
├── podcast.xml         # Generated RSS feed (output)
├── LICENSE             # MIT License
└── README.md           # This file
```

**What Each File Does:**

| File | Purpose | Editing |
|------|---------|---------|
| `feed.py` | Python script that reads YAML and generates RSS/XML | Not usually |
| `feed.yaml` | Your podcast metadata & all episodes | ✏️ Edit this |
| `podcast.xml` | Final RSS feed output | Auto-generated |

---

## 🚀 Quick Start

### 1. Install Python Dependencies

```bash
pip install pyyaml
```

### 2. Edit Your Podcast Config

Open `feed.yaml` and update with your podcast details:

```bash
nano feed.yaml
# or use VSCode, Sublime, or your favorite editor
```

**Key fields to customize:**
- `title` - Your podcast name
- `author` - Your name
- `link` - Your website base URL
- `image` - Path to podcast artwork
- `item` - Add your episodes here

### 3. Generate Your RSS Feed

```bash
python feed.py
```

### 4. Check the Output

Open `podcast.xml` - this is your RSS feed! Ready to:
- ✅ Submit to Apple Podcasts
- ✅ Submit to Spotify
- ✅ Host on your website
- ✅ Share anywhere

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

## 🔧 System Workflow

```text
1. Load YAML Configuration
   ↓
2. Parse Podcast Metadata
   ↓
3. Create RSS Structure
   ├─ Add RSS 2.0 root element
   ├─ Add iTunes namespace
   └─ Add content namespace
   ↓
4. Build Channel Section
   ├─ Title, author, language
   ├─ Description, artwork
   ├─ Category, link
   └─ Format
   ↓
5. Process Episodes
   ├─ Iterate through items
   ├─ Add episode metadata
   ├─ Create audio enclosure
   └─ Set publication date
   ↓
6. Write podcast.xml
   ├─ UTF-8 encoding
   ├─ XML declaration
   └─ Proper formatting
   ↓
7. Deploy & Submit
   ├─ Upload to web server
   ├─ Submit feed URL to platforms
   └─ Verify in podcast directories
```

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
python feed.py
```

### Example 2: Updating Podcast Title

```yaml
title: "The Future in Tech - Season 2"
subtitle: "Advanced Topics & Expert Interviews"
```

Re-run `python feed.py` → all episodes inherit new metadata.

### Example 3: Changing the Base URL

```yaml
link: https://mynewsite.com
```

All episode audio paths automatically prepend the new URL:
- `/audio/ep1.mp3` → `https://mynewsite.com/audio/ep1.mp3`

---

## 📈 What This Project Demonstrates

✔ YAML configuration management  
✔ XML generation from structured data  
✔ RSS/podcast standards knowledge  
✔ iTunes integration and compatibility  
✔ Clean Python scripting  
✔ Version-controlled podcast distribution  

This is how **real podcast platforms** manage their feeds.

---

## 🧪 Tech Stack

* Python 3.6+
* PyYAML
* xml.etree.ElementTree (standard library)

---

## 📋 Requirements

- Python 3.6 or higher
- pyyaml library (`pip install pyyaml`)
- Valid podcast metadata
- Audio files accessible from your base URL

---

## 🔄 Workflow Tips

1. **Version Control** - Keep `feed.yaml` in git, track all episode changes
2. **Validate Feed** - Use [podtrac.com](https://podtrac.com) or [podbase.io](https://podbase.io) to validate
3. **Host the XML** - Upload `podcast.xml` to your web server
4. **Submit URLs** - Most platforms accept your feed URL (e.g., `https://yourdomain.com/podcast.xml`)
5. **Update Regularly** - Edit `feed.yaml`, run `python feed.py`, redeploy
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


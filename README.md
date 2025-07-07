# 🤖 BrowserArena Verified GIFs

This repository contains **227 verified GIFs** (177MB) from the BrowserArena dataset - only the GIFs that are referenced in verified human preference experiments.

## 📊 Overview

- **227 verified GIFs** from 126 browser automation interactions
- **177MB total size** (reduced from 560MB of all GIFs)
- **Interactive web viewer** with copy-to-clipboard functionality
- **GitHub Pages deployment** ready

## 🚀 Quick Start

1. **View online:** https://davisrbr.github.io/verified-gifs-only/

2. **Direct GIF access:**
   ```
   https://davisrbr.github.io/verified-gifs-only/gifs/[GIF_ID].gif
   ```

3. **Example URLs:**
   - https://davisrbr.github.io/verified-gifs-only/gifs/12_05_2025_03_54_21_KhV.gif
   - https://davisrbr.github.io/verified-gifs-only/gifs/07_05_2025_15_10_56_EiU.gif

## 📁 Repository Structure

```
verified-gifs-only/
├── index.html          # Interactive GIF viewer
├── gifs/              # 227 verified GIF files
│   ├── 03_05_2025_04_36_24_DPn.gif
│   ├── 03_05_2025_04_36_24_hCn.gif
│   └── ...
└── README.md          # This file
```

## 🎯 Usage in Research

### Markdown
```markdown
![Browser Automation](https://davisrbr.github.io/verified-gifs-only/gifs/12_05_2025_03_54_21_KhV.gif)
```

### HTML
```html
<img src="https://davisrbr.github.io/verified-gifs-only/gifs/12_05_2025_03_54_21_KhV.gif" alt="Browser Task">
```

### LaTeX
```latex
\includegraphics[width=\textwidth]{https://davisrbr.github.io/verified-gifs-only/gifs/12_05_2025_03_54_21_KhV.gif}
```

## 🔄 Deployment to GitHub Pages

### Prerequisites
1. Create a **public** repository named `verified-gifs-only` on GitHub
2. Ensure you have git configured with your GitHub username

### Deploy Steps
```bash
# Add GitHub remote
git remote add origin https://github.com/davisrbr/verified-gifs-only.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### Enable GitHub Pages
1. Go to repository **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / (root)
4. Click **Save**

Your GIFs will be available at: `https://davisrbr.github.io/verified-gifs-only/`

## 📈 Dataset Information

These GIFs represent browser automation attempts from the BrowserArena dataset:
- Each GIF shows a model attempting to complete a specific user task
- Tasks include web browsing, form filling, information extraction, etc.
- GIFs are paired (2 model attempts per task) for human preference evaluation
- Only successful and verified interactions are included

## 🔗 Related Files

- **Full dataset:** `/Users/davisbrown/browserarena/FastChat/verified_conv_log/verified_interactions-clean.json`
- **Extracted interactions:** `/Users/davisbrown/browserarena/extracted_verified_interactions_fixed.txt`
- **All GIFs (560MB):** `/Users/davisbrown/browserarena/browserarena-gifs/`

---

**Total:** 227 verified GIFs • 177MB • Ready for web deployment 🚀
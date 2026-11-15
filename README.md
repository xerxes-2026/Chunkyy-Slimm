# Chunky Slimm(https://chunkyslimm.netlify.app)

**A smart KV-cache memory layer that lets small LLMs remember more on less GPU.**

Team XERXES · Perceptron Hackathon, Techfest IIT Bombay 2026 · Problem 2



# Overview

Chunky Slimm sorts every chat message by importance and decides where its KV cache should live: kept hot on the GPU, compressed into 2-bit "boxes", moved to a shared common store, or sealed in a private vault. The result is longer, cheaper conversations with better recall than keeping the full cache.

This repo holds a clickable web prototype of the experience.

#✨ Features

- **Message triage**: each message is tagged as keep hot, box it, common store, unclear, filler or vault.
- **Chat commands**: `/pin`, `/lock`, `/unlock`, `/seal`, `/forget`, `/help`
- **Tiered storage**: GPU → RAM → Disk → Cloud, with a "Let 1 hour pass" simulation
- **Private vault** for sensitive data (demo key: `xerxes`)
- **Mode switch**: Chunky Slimm vs full cache, on Llama 3.2 1B, Qwen 2.5 1.5B or Llama 3.2 3B
- **Compare view** against StreamingLLM, H2O and SnapKV
- **AI compressor** step for photo and video attachments

##  Quick start

No install or build needed.

```bash
git clone https://github.com/<your-username>/chunky-slimm.git
cd chunky-slimm
open index.html   # or just double-click it
```

Works offline in Chrome, Edge, Firefox and Safari.



## 📁 Project structure

```
├── index.html      # Whole prototype (HTML, CSS, JS in one file)
├── screenshots/    # Demo captures
└── README.md
```

## ⚠️ Note

All figures are simulated from planning estimates (32 KB of KV cache per token for Llama 3.2 1B, 2-bit boxes at 1/8 of fp16 size). They are not measured results. The full build is planned in Python with Gradio.

## 👥 Team

**Team XERXES**, Techfest IIT Bombay 2026

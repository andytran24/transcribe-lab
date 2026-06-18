# transcribe-lab

A hands-on showcase of the [Cohere Transcribe](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026) model (`cohere-transcribe-03-2026`) — Cohere's first automatic speech recognition (ASR) model supporting 14 languages.

## What's Inside

`transcribe_lab.ipynb` — a Jupyter notebook with four demonstrations:

| # | Topic | Description |
|---|-------|-------------|
| 1 | Noisy Audio | Uses a local FLEURS English clip, adds synthetic background noise (SNR ≈ 10 dB), and transcribes it |
| 2 | Near Real-Time | Chunks mic input (or a local WAV file) into 4-second windows and transcribes each as it arrives |
| 3 | Multilingual | Transcribes all 14 supported languages using local FLEURS clips |
| 4 *(optional)* | Local Streaming | Real-time mic transcription using the model running locally — requires HF token + GPU recommended |

Audio samples for all 14 languages are included in the `audio/` folder — no internet connection required for cells 1–3.

## Setup

### 1. Clone and install dependencies

```bash
git clone https://github.com/andytran24/transcribe-lab.git
cd transcribe-lab
pip install -r requirements.txt
```

### 2. Add your Cohere API key

```bash
cp .env.example .env
# Edit .env and set CO_API_KEY=your_key_here
```

Get a free API key at [dashboard.cohere.com](https://dashboard.cohere.com).

### 3. Launch the notebook

```bash
jupyter notebook transcribe_lab.ipynb
```

## Optional: Cell 4 Setup (Local Model Streaming)

Cell 4 runs the model locally on your machine via HuggingFace `transformers`. It requires a HuggingFace account and token because the model is hosted in a gated repository.

### 1. Accept the model license

Visit [huggingface.co/CohereLabs/cohere-transcribe-03-2026](https://huggingface.co/CohereLabs/cohere-transcribe-03-2026) and click **"Agree and access repository"**.

### 2. Generate a HuggingFace token

Go to [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens), click **"New token"**, select type **"Read"**, and copy the generated token (starts with `hf_...`).

### 3. Add the token to your `.env` file

```bash
HF_TOKEN=hf_your_token_here
```

### 4. Restart the Jupyter kernel and run Cell 4

The cell loads `HF_TOKEN` from `.env` automatically. On first run it downloads ~4 GB of model weights (cached locally afterward).

> **GPU note:** An NVIDIA GPU (CUDA) gives the best performance (~525× real-time). Apple M-series (MPS) also works. CPU is functional but will lag noticeably per chunk.

---

## Audio Files

| Path | Contents |
|------|----------|
| `audio/en_clean.wav` | Clean English FLEURS validation clip |
| `audio/en_noisy.wav` | Same clip with synthetic background noise (SNR ≈ 10 dB) |
| `audio/multilingual/` | FLEURS validation clips for all 14 supported languages |

## Supported Languages

🇺🇸 English · 🇫🇷 French · 🇩🇪 German · 🇪🇸 Spanish · 🇧🇷 Portuguese · 🇮🇹 Italian · 🇳🇱 Dutch · 🇵🇱 Polish · 🇬🇷 Greek · 🇸🇦 Arabic · 🇯🇵 Japanese · 🇰🇷 Korean · 🇨🇳 Chinese · 🇻🇳 Vietnamese

## Resources

- [Cohere Transcribe Model](https://docs.cohere.com/v2/docs/transcribe)
- [Cohere Transcribe Model announcement](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026)
- [Audio Transcriptions API reference](https://docs.cohere.com/v2/reference/create-audio-transcription)
- [Cohere Transcribe HuggingFace Demo UI](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)

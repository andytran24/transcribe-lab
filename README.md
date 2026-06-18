# transcribe-lab

A hands-on showcase of the [Cohere Transcribe](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026) model (`cohere-transcribe-03-2026`) — Cohere's first automatic speech recognition (ASR) model supporting 14 languages.

## What's Inside

`transcribe_lab.ipynb` — a Jupyter notebook with three demonstrations:

| # | Topic | Description |
|---|-------|-------------|
| 1 | Noisy Audio | Uses a local FLEURS English clip, adds synthetic background noise (SNR ≈ 10 dB), and transcribes it |
| 2 | Near Real-Time | Chunks mic input (or a local WAV file) into 4-second windows and transcribes each as it arrives |
| 3 | Multilingual | Transcribes all 14 supported languages using local FLEURS clips |

Audio samples for all 14 languages are included in the `audio/` folder — no internet connection required to run the notebook.

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

## Audio Files

| Path | Contents |
|------|----------|
| `audio/en_clean.wav` | Clean English FLEURS validation clip |
| `audio/en_noisy.wav` | Same clip with synthetic background noise (SNR ≈ 10 dB) |
| `audio/multilingual/` | FLEURS validation clips for all 14 supported languages |

## Supported Languages

🇺🇸 English · 🇫🇷 French · 🇩🇪 German · 🇪🇸 Spanish · 🇧🇷 Portuguese · 🇮🇹 Italian · 🇳🇱 Dutch · 🇵🇱 Polish · 🇬🇷 Greek · 🇸🇦 Arabic · 🇯🇵 Japanese · 🇰🇷 Korean · 🇨🇳 Chinese · 🇻🇳 Vietnamese

## Resources

- [Cohere Transcribe docs](https://docs.cohere.com/v2/docs/transcribe)
- [Cohere Transcribe announcement](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026)
- [Audio Transcriptions API reference](https://docs.cohere.com/v2/reference/create-audio-transcription)
- [Cohere Transcribe HuggingFace Space](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)

# transcribe-lab

A hands-on showcase of the [Cohere Transcribe](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026) model (`cohere-transcribe-03-2026`) — Cohere's first automatic speech recognition (ASR) model supporting 14 languages.

## What's Inside

`transcribe_demo.ipynb` — a Jupyter notebook with three demonstrations:

| Cell | Topic | Description |
|------|-------|-------------|
| 1 | Noisy Audio | Downloads a FLEURS English clip, adds synthetic background noise (SNR ≈ 10 dB), and transcribes it |
| 2 | Near Real-Time | Chunks mic input (or a WAV file) into 4-second windows and transcribes each as it arrives |
| 3 | Multilingual | Transcribes FLEURS clips in English, French, Japanese, Arabic, and Spanish |

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
jupyter notebook transcribe_demo.ipynb
```

## Supported Languages

English · German · French · Italian · Spanish · Portuguese · Greek · Dutch · Polish · Vietnamese · Chinese · Arabic · Japanese · Korean

## Resources

- [Cohere Transcribe announcement](https://docs.cohere.com/v2/changelog/cohere-transcribe-03-2026)
- [Audio Transcriptions API reference](https://docs.cohere.com/v2/reference/create-audio-transcription)
- [Cohere Transcribe HuggingFace Space](https://huggingface.co/spaces/CohereLabs/cohere-transcribe-03-2026)

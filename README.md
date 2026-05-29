# 🎙️ AI-Based Dysarthric Speech Recognition System
### Using Data Augmentation and Pretrained ASR Models

An end-to-end speech and NLP pipeline for dysarthric speech recognition using pretrained transformer-based ASR models, LoRA fine-tuning, and downstream NLP analysis.

---

## 📌 Overview

Dysarthric speech is often difficult for traditional Automatic Speech Recognition (ASR) systems due to:

- Slurred pronunciation
- Reduced articulation clarity
- Weak speech muscle control
- Inconsistent speech patterns

This project presents a lightweight and deployable AI-based dysarthric speech recognition system that integrates:

- 🎤 Speech-to-Text (ASR)
- ✏️ Grammar Correction
- 🎯 Intent Classification
- 🔍 Named Entity Recognition (NER)
- 💬 Sentiment Analysis
- 🌐 Interactive Gradio Web App

The system demonstrates how pretrained transformer architectures can be adapted for accessible real-world speech applications.

---

# 🗺️ System Pipeline

```text
Audio Input
    ↓
Audio Preprocessing
    ↓
Data Augmentation
    ↓
ASR Model (wav2vec2 / Whisper + LoRA)
    ↓
Raw Transcript
    ↓
NLP Processing
    ├── Grammar Correction
    ├── Intent Classification
    ├── Named Entity Recognition
    └── Sentiment Analysis
    ↓
Structured Output
    ↓
Gradio Deployment
```

---

# 📚 Research Gaps Addressed

| Gap | Existing Limitation | Proposed Solution |
|------|--------------------|------------------|
| Implementation Gap | Research papers focus mainly on methodology | Complete end-to-end pipeline |
| Deployment Gap | No user-facing applications | Interactive Gradio-based web interface |
| Feasibility Gap | High computational requirements | Lightweight pretrained models with LoRA |
| Accessibility Gap | Limited usability focus | Simple mic/upload interface |
| Reproducibility Gap | Difficult to replicate pipelines | Single reproducible notebook |

---

# 🚀 Features

- 🎤 Speech recognition using pretrained ASR models
- 🧠 Whisper fine-tuning using LoRA
- 🔊 Audio preprocessing and augmentation
- ✏️ Grammar correction using transformer models
- 🎯 Intent classification
- 🔍 Named entity recognition
- 💬 Sentiment analysis
- 📊 Evaluation using WER, CER, F1-score
- 🌐 Interactive Gradio deployment

---

# 🧠 Models Used

| Task | Model |
|------|------|
| Baseline ASR | wav2vec2-base-960h |
| Fine-Tuned ASR | Whisper-small + LoRA |
| Grammar Correction | T5 |
| Intent Classification | BART / Zero-shot classifier |
| Named Entity Recognition | spaCy |
| Sentiment Analysis | DistilBERT |

---

# ⚙️ Technologies Used

- Python
- PyTorch
- Hugging Face Transformers
- PEFT (LoRA)
- librosa
- audiomentations
- Gradio
- spaCy
- scikit-learn
- pandas

---

# 📂 Project Structure

```text
├── original_audio/
├── augmented_audio/
├── whisper-lora-finetuned/
├── notebook.ipynb
├── README.md
└── requirements.txt
```

---

# 🔄 Workflow

## 1. Audio Preprocessing

The uploaded or recorded speech audio undergoes:

- Mono conversion
- Normalization
- Resampling to 16kHz

---

## 2. Data Augmentation

Audio augmentation techniques improve robustness:

- Gaussian Noise
- Pitch Shift
- Time Stretching

---

## 3. Automatic Speech Recognition (ASR)

Two ASR models are used:

### 🔹 wav2vec2 (Baseline)

Used as the baseline speech recognition model.

### 🔹 Whisper + LoRA

Whisper-small is fine-tuned using Low-Rank Adaptation (LoRA) for efficient adaptation with lower computational cost.

---

## 4. NLP Processing

The generated transcript is processed through multiple NLP tasks:

### ✏️ Grammar Correction
Corrects grammatical inconsistencies in the transcript.

### 🎯 Intent Classification
Detects the user's intent from speech.

### 🔍 Named Entity Recognition
Extracts entities such as names, time, and locations.

### 💬 Sentiment Analysis
Determines emotional tone from the speech transcript.

---

# 📊 Evaluation Metrics

The project evaluates ASR and NLP performance using:

| Metric | Purpose |
|------|------|
| WER | Word Error Rate |
| CER | Character Error Rate |
| F1-Score | Sentiment evaluation |
| Accuracy | Classification performance |

---

# 🌐 Gradio Demo

The project includes an interactive Gradio-based web application where users can:

- Upload `.wav` audio files
- Record speech using microphone
- Select ASR model
- View NLP outputs in real-time

---

# 📈 Sample Output

```json
{
  "raw_transcript": "hello i have appointment tomorrow",
  "corrected_text": "Hello, I have an appointment tomorrow.",
  "intent": {
    "label": "give information",
    "score": 0.92
  },
  "entities": [
    {
      "text": "tomorrow",
      "label": "TIME"
    }
  ],
  "sentiment": {
    "label": "Neutral",
    "score": 0.88
  }
}
```

---

# 🎯 Objectives

- Build an end-to-end dysarthric speech recognition system
- Compare baseline and fine-tuned ASR performance
- Integrate downstream NLP processing
- Provide lightweight and deployable implementation
- Improve accessibility for speech-impaired communication

---

# 🔮 Future Scope

- Integration with real dysarthric datasets (TORGO)
- Multilingual speech support
- Noise-robust inference
- Mobile/Web deployment
- Medical assistance integration

---

# ⚠️ Limitations

- Limited dysarthric dataset availability
- Lightweight fine-tuning due to compute constraints
- Not medically certified
- Performance may vary in noisy environments

---

# 👩‍💻 Author

Developed as part of the **Natural Language Processing & Speech Processing** coursework project.

---

# ⭐ Acknowledgements

- OpenAI Whisper
- Hugging Face Transformers
- Meta wav2vec2
- Gradio
- spaCy
- PyTorch

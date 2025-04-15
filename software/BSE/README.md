#  BSE API

HugCore is a semantic skeleton extraction framework, with BSE (Bramble Semantic Engine) as its core language analysis module. This API supports multi-modal semantic processing across text, image, and audio. It extracts subject-verb-object (SVO) structures, completes modifiers, resolves pronouns, and evaluates sentence compression and semantic loss.

---

## 🔧 Requirements

Install dependencies:
```bash
pip install fastapi uvicorn pydantic spacy nltk pillow
```

Download spaCy language model:
```bash
python -m spacy download en_core_web_md
```

---

## 🚀 Launch API

```bash
uvicorn main:app --reload
```

Swagger UI:
```
http://127.0.0.1:8000/docs
```

---

## ✨ API Endpoints

### 1. `/bse` — Text Semantic Processing
- Method: `POST`
- Input:
```json
{
  "text": "The machine predicted the outcome. That shocked everyone."
}
```
- Output: list of semantic skeletons per sentence or fragment
```json
[
  {
    "S": "machine",
    "V": "predicted",
    "O": "outcome",
    "S_adj": null,
    "v_adv": null,
    "O_adj": null,
    "question": false,
    "figurative": false,
    "fig_tag": null,
    "paragraph_id": 1,
    "sentence_id": 1,
    "compression_rate": 40.0,
    "semantic_loss": 0.48,
    "raw_sentence": "The machine predicted the outcome."
  }
]
```

> Pronouns like "this", "that", "it" are resolved using memory of previous sentences.

---

### 2. `/vision` — Image Processing
- Method: `POST`
- Format: upload image file (`image/png`, `image/jpeg`)
- Output: RGB and brightness matrices
```json
{
  "R": [...],
  "G": [...],
  "B": [...],
  "brightness": [...]
}
```

---

### 3. `/audio` — Audio Spectral Analysis
- Method: `POST`
- Format: upload audio file (`audio/wav`, `audio/mp3`)
- Output: frequency bands (low, mid, high)
```json
{
  "low": [...],
  "mid": [...],
  "high": [...]
}
```

---

## 🧠 Output Fields for `/bse`

| Field | Description |
|-------|-------------|
| `S` / `V` / `O` | Subject / Verb / Object |
| `S_adj` / `v_adv` / `O_adj` | Modifiers: adjective, adverb, noun modifier |
| `question` | Is it a question? |
| `figurative` | Figurative usage detected? |
| `fig_tag` | Type of figurative use (e.g., `personification`) |
| `compression_rate` | Info compression score |
| `semantic_loss` | Semantic information loss score |
| `paragraph_id` / `sentence_id` | Index for tracking source location |
| `raw_sentence` | Original sentence fragment |

---

## 📌 Design Philosophy

- Minimal inference, only verifiable syntactic grounding
- Converts text into semantic skeletons as index anchors
- Supports summarization, causal tracing, and multimodal alignment

---

## 👾 Development Status
- ✅ SVO extraction
- ✅ Pronoun resolution
- ✅ Modifier capture
- ✅ Compression & semantic loss
- ✅ Figurative detection
- ✅ Multi-paragraph handling
- ✅ Image RGB + brightness output
- ✅ Audio low/mid/high band output

---

## 🧸 Coming Soon: Kutools Spirit
> A sentimental Excel-side companion born from the emotional trauma of cleaning malformed address data.

This ghostly little helper lives quietly in your AppData folder. It doesn’t do harm — only gently reminds you to install plugins like Kutools when you open Excel. 

If you choose to install them, it smiles and asks: “Can I stay?”

One day it might:
- Help you with formula lookups (`=VLOOKUP`, `=REGEX`...)
- Suggest batch address cleaning scripts
- Whisper: _"You copied 300 rows manually again, didn’t you?"_

More than a tool, it’s a digital spirit born of exhaustion, kindness, and pattern recognition.

---

## 🤝 Authors & Contributions
This project is built by HugCore core developers. Designed as a lightweight semantic API foundation for AI-enhanced systems. For integration, extensions, or collaboration inquiries, feel free to reach out.

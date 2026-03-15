<div align="center">

# 🎙️ Audio Deepfake Detection

### Detect AI-Generated Audio with Machine Learning

[![Python](https://img.shields.io/badge/Python-3.9+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Flask](https://img.shields.io/badge/Flask-3.0.2-000000?style=for-the-badge&logo=flask&logoColor=white)](https://flask.palletsprojects.com)
[![Librosa](https://img.shields.io/badge/Librosa-0.10.1-FF6B35?style=for-the-badge)](https://librosa.org)

</div>

---

## 📌 Overview

**Audio Deepfake Detection** is a Flask-based web application that uses ML-driven audio feature extraction to classify uploaded audio files as either **Real** or **Deepfake** — and provides a confidence probability score with the result.

The system uses a nearest-neighbor matching approach over a labeled CSV dataset, analyzing the acoustic signature of uploaded audio using multiple signal processing features.

---

## ✨ Features

- 🎵 **Multi-feature Extraction** — Extracts MFCC, Mel Spectrogram, Chroma, ZCR, Spectral Centroid, and Spectral Flatness
- 🤖 **Nearest-Neighbor Classification** — Compares extracted features against a pre-built dataset using Euclidean distance
- 📊 **Confidence Score** — Returns a probability percentage for each prediction
- 🌙 **Modern Dark UI** — Glassmorphism design with TailwindCSS (via CDN)
- 📁 **Supports Multiple Formats** — WAV, MP3, OGG, FLAC and more (via Librosa)

---

## 🗂️ Project Structure

```
Audio-Deepfake-Detection/
├── app.py                  # Main Flask application (routes, feature extraction, prediction)
├── dataset.csv             # Pre-labeled audio feature dataset (real vs deepfake)
├── requirements.txt        # Python dependencies
├── README.md               # Project documentation
│
├── templates/
│   └── model.html          # Frontend UI (TailwindCSS, glassmorphism dark theme)
│
└── Test/                   # Sample audio files for testing
    ├── DeepfakeExample1.wav
    ├── DeepfakeExample2.wav
    ├── DeepfakeExample3.wav
    ├── DeepfakeExample4.wav
    ├── DeepfakeExample5.wav
    ├── RealExample1.wav
    └── RealExample2.wav
```

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
|-------|-----------|---------|
| **Backend** | Python 3.9+ | Core runtime |
| **Web Framework** | Flask 3.0.2 | HTTP server & routing |
| **Audio Processing** | Librosa 0.10.1 | Feature extraction from audio |
| **Resampling** | Resampy 0.4.2 | Audio resampling support |
| **Audio I/O** | SoundFile 0.12.1 | Audio file reading backend |
| **Data Handling** | Pandas 1.5.3 | Dataset loading and row access |
| **Numerical Computing** | NumPy 1.24.3 | Feature vectors & distance calculation |
| **Frontend** | HTML5 + TailwindCSS | Responsive dark-mode UI (via CDN) |
| **Templating** | Jinja2 3.1.3 | Server-side HTML rendering |

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/Audio-Deepfake-Detection.git
cd Audio-Deepfake-Detection
```

### 2. Create a Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate        # macOS/Linux
# venv\Scripts\activate         # Windows
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the App

```bash
python app.py
```

Open your browser and go to: **http://127.0.0.1:5000**

> **Note:** If port 5000 is in use (common on macOS due to AirPlay Receiver), run on a different port:
> ```bash
> flask run --port 5001
> ```

---

## 🧑‍💻 How It Works

```
Upload Audio File
      │
      ▼
Feature Extraction (via Librosa)
  ├─ MFCC (100 coefficients)
  ├─ Mel Spectrogram (128 bands)
  ├─ Chroma Features (50 bins)
  ├─ Zero Crossing Rate
  ├─ Spectral Centroid
  └─ Spectral Flatness
      │
      ▼
Euclidean Distance → Compare against dataset.csv
      │
      ▼
Nearest Neighbor Match → Label: "real" or "deepfake"
      │
      ▼
Confidence Score = 1 - (min_distance / total_distance)
      │
      ▼
Display Result on UI
```

---

## 🎧 Test Samples

The `Test/` folder contains 7 sample audio files you can use immediately:

| File | Label |
|------|-------|
| `DeepfakeExample1.wav` | 🔴 Deepfake |
| `DeepfakeExample2.wav` | 🔴 Deepfake |
| `DeepfakeExample3.wav` | 🔴 Deepfake |
| `DeepfakeExample4.wav` | 🔴 Deepfake |
| `DeepfakeExample5.wav` | 🔴 Deepfake |
| `RealExample1.wav` | 🟢 Real |
| `RealExample2.wav` | 🟢 Real |

---

## ⚠️ Disclaimer

This project was developed as a **college project**. While it demonstrates core deepfake detection concepts, it should **not** be treated as a production-grade security tool. For critical applications, use specialized and professionally audited deepfake detection systems.

The accuracy depends entirely on the diversity and size of `dataset.csv`. Contributing additional labeled audio samples directly improves detection performance.

---

## 🤝 Contributing

Contributions and audio sample donations are welcome!

1. Fork this repository
2. Add labeled audio samples or improve feature extraction
3. Submit a Pull Request

---

## 📄 License

This project is open source. Feel free to use and modify it for educational purposes.

---

<div align="center">
Made with ❤️ for Audio Intelligence Research
</div>

# 🎙️ Real-Time Audio Streaming & Signal Processing

[![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org)
[![NumPy](https://img.shields.io/badge/NumPy-1.20%2B-lightgrey?logo=numpy&logoColor=white)](https://numpy.org)
[![PyAudio](https://img.shields.io/badge/PyAudio-0.2.11%2B-green)](https://people.csail.mit.edu/hubert/pyaudio/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.5%2B-orange)](https://matplotlib.org)

A lightweight Python project for capturing real-time audio streams via microphone, converting raw binary data into structured numerical arrays, calculating dynamic signal statistics, and visualizing the captured audio waveforms. This serves as a fundamental building block for Voice Recognition, DSP (Digital Signal Processing), and Audio Machine Learning pipelines.

---

## ✨ Key Features

- **Live Audio Streaming:** Captures real-time audio from the default input device (microphone) using `PyAudio`.
- **Stream Configuration:** Optimized for standard speech recognition with a **16 kHz sampling rate**, mono channel, and 16-bit depth (`paInt16`).
- **Dynamic Feature Extraction:** Extracts real-time statistical metrics (`Mean`, `Min`, `Max`) per buffer chunk (1024 frames) on the fly using `NumPy`.
- **Interactive Visualization:** Plugs into `Matplotlib Widget` to render interactive and responsive waveform plots directly inside Jupyter Notebooks.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python
* **Audio Core:** `PyAudio` (PortAudio wrapper for Python)
* **Data Processing:** `NumPy` (Vectorized buffer transformations)
* **Visualization:** `Matplotlib` / `ipympl` (Interactive inline notebook widgets)

---

## ⚙️ Installation & Setup

### Prerequisites
Make sure you have `PortAudio` installed on your system before setting up PyAudio.
- **Ubuntu/Debian:** `sudo apt-get install portaudio19-dev`
- **macOS:** `brew install portaudio`

### Environment Setup
1. Clone the repository:
   ```bash
   git clone [https://github.com/your-username/your-repo-name.git](https://github.com/your-username/your-repo-name.git)
   cd your-repo-name
Install the required libraries:

Bash
pip install pyaudio numpy matplotlib ipympl
🚀 How It Works
The workflow inside the core notebook (voice_recognize.ipynb) follows these standard signal processing steps:

Initialization: Instantiates the PyAudio object and sets the buffer window size (sabad = 1024).

Stream Configuration: Opens a hardware channel with the following characteristics:

Python
format = pyaudio.paInt16  # 16-bit resolution
channels = 1              # Mono channel
rate = 16000              # 16kHz sample rate (Speech Standard)
Chunk Processing: Iteratively reads binary stream data, converts it using np.frombuffer, and monitors standard deviation and amplitude limits.

Plotting: Consolidates all frames into a singular continuous time-series vector for plotting the final raw waveform.

📊 Sample Output Structure
During execution, the script prints real-time chunk statistics in the following format:

Plaintext
[Chunk Index]   [Mean Amplitude]   [Min Amplitude]   [Max Amplitude]
0               -48.3974609375     -1495             1145
1               107.0048828125     -1327             1368
2               24.0712890625      -1654             1382
📝 Roadmap / Next Steps
[ ] Implement Fast Fourier Transform (FFT) for real-time Frequency/Spectrum analysis.

[ ] Add Mel-Frequency Cepstral Coefficients (MFCCs) feature extraction.

[ ] Integrate a lightweight deep learning model (e.g., Speech Command Recognition).

Developed by Amirali Afshariyan
   

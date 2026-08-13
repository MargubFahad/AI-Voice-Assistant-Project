
# 🎙️ Advanced AI Voice Assistant

An advanced, multimodal AI voice assistant developed in Python that integrates **speech recognition, digital signal processing (DSP), natural language processing (NLP), voice biometrics, image processing, mathematical and physics computation, dynamic memory, web search, and desktop application control** into a single modular system.

Unlike a basic voice assistant, this system can understand spoken commands, identify speakers, capture and match images, deblur images, solve mathematical and physics problems, learn new information, retrieve information from the web, and launch applications or websites.

---

## 🚀 Key Features

- 🎙️ Speech recognition using Google Speech Recognition
- 🔊 Text-to-speech responses
- ⚡ DSP-based speech preprocessing
- 🎚️ Butterworth bandpass filtering
- 📊 FFT-based signal processing and noise suppression
- 🔄 Convolution-based audio smoothing
- 🗣️ Voice feature extraction using MFCC
- 👤 Speaker identification using cosine similarity
- 📷 Webcam and file-based image capture
- 🖼️ Histogram-based image matching
- ✨ Image deblurring using Richardson–Lucy deconvolution
- 🧮 Mathematical equation solving
- 📐 Differentiation and integration
- ⚙️ Basic physics calculations
- 🧠 Dynamic knowledge and memory system
- 💾 JSON-based information storage
- 🌐 Wikipedia information retrieval
- 🔎 Google Search integration
- 💻 Automatic application detection and launching
- 🌍 Voice-controlled website opening
- 🔤 Basic word prediction and command correction
- 🧩 Modular and extensible architecture

---

## 🏗️ System Architecture

```text
                    ┌────────────────────┐
                    │    User Speech     │
                    └─────────┬──────────┘
                              ↓
                    ┌────────────────────┐
                    │  Audio Recording   │
                    └─────────┬──────────┘
                              ↓
                    ┌────────────────────┐
                    │ DSP Preprocessing  │
                    │ Bandpass + FFT +   │
                    │ Signal Smoothing   │
                    └─────────┬──────────┘
                              ↓
                    ┌────────────────────┐
                    │ Speech Recognition │
                    └─────────┬──────────┘
                              ↓
                    ┌────────────────────┐
                    │ Command Processing │
                    └─────────┬──────────┘
                              ↓
          ┌───────────────────┼────────────────────┐
          ↓                   ↓                    ↓
   Voice Biometrics    Image Processing      Knowledge
          ↓                   ↓                    ↓
    MFCC Features      Histogram Matching    Static Memory
    Cosine Similarity  Richardson–Lucy       Dynamic Memory
          │             Deblurring             Wikipedia
          │                   │                Google Search
          └───────────────────┼────────────────────┘
                              ↓
                    ┌────────────────────┐
                    │   Response Engine  │
                    └─────────┬──────────┘
                              ↓
                    ┌────────────────────┐
                    │  Text-to-Speech    │
                    └────────────────────┘
````

---

## 🧠 Hybrid Knowledge System

The assistant uses a three-level knowledge architecture.

### 1. Static Knowledge Base

A predefined knowledge base provides immediate responses for common requests such as:

* Greetings
* Name
* Date
* Time
* Goodbye

### 2. Dynamic Memory

The assistant can learn new facts during interaction and store them in JSON format.

Example:

```text
Learn that KUET is in Khulna
```

The learned information is stored and can be retrieved during future interactions.

### 3. External Knowledge Retrieval

For questions outside the predefined and learned knowledge, the assistant can retrieve information using:

* Wikipedia
* Google Search

Retrieved information can also be stored in the dynamic knowledge system.

---

# 🎙️ Speech Processing

The assistant applies several digital signal processing techniques to improve the quality of recorded speech before recognition.

## Bandpass Filtering

A Butterworth bandpass filter is applied to isolate the main speech-frequency range.

```text
Lower cutoff: 300 Hz
Upper cutoff: 3400 Hz
```

This helps reduce unwanted low- and high-frequency components.

## FFT-Based Processing

The filtered audio signal is transformed into the frequency domain using the **Fast Fourier Transform (FFT)**.

Frequency components below a defined magnitude threshold are suppressed before converting the signal back into the time domain using the inverse FFT.

## Signal Smoothing

A moving-average convolution kernel is applied to smooth the processed audio signal and reduce rapid fluctuations.

---

# 🗣️ Voice Biometrics

The assistant includes a voice-matching system for identifying previously stored voices.

## MFCC Feature Extraction

The system extracts **13 Mel-Frequency Cepstral Coefficients (MFCCs)** from recorded audio.

The MFCC values are averaged over time to produce a compact representation of the speaker's voice.

```text
Audio
  ↓
MFCC Extraction
  ↓
13-Dimensional Voice Feature Vector
  ↓
Stored in JSON Memory
```

## Voice Matching

The input voice feature vector is compared with stored voiceprints using **cosine similarity**.

The implemented matching threshold is:

```text
Cosine Similarity > 0.85
```

If the similarity exceeds the threshold, the system returns the corresponding stored voice description.

---

# 📷 Image Processing

The assistant provides image capture, image storage, image matching, and image restoration capabilities.

## Image Capture

Images can be captured from:

* Webcam
* Existing image files

Captured images are stored locally and associated with user-defined descriptions.

Example:

```text
Capture image
```

The system captures an image from the webcam and stores it in the image memory.

## 🖼️ Image Feature Extraction

The system converts the image to grayscale and extracts a normalized intensity histogram.

The image is resized when necessary to reduce processing requirements.

The histogram is then stored as the image's feature representation.

## 🔍 Image Matching

An input image can be compared with previously stored images.

The system uses histogram correlation to determine the closest match.

The implemented matching threshold is:

```text
Correlation > 0.80
```

Example command:

```text
Match image
```

The assistant compares the current image against the stored image memory and returns the matching description when the similarity threshold is satisfied.

---

# ✨ Image Deblurring

The assistant includes image restoration using **Richardson–Lucy deconvolution**.

A Gaussian point-spread function (PSF) is generated and used to perform iterative deconvolution.

The implementation uses:

```text
15 Richardson–Lucy iterations
```

After deconvolution, a sharpening filter is applied to enhance the restored image.

Example command:

```text
Clear image
```

The system displays the original and processed images for comparison.

---

# 🧮 Mathematical Solver

The assistant includes mathematical processing using **SymPy**.

Supported operations include:

* Numerical expressions
* Equation solving
* Differentiation
* Integration

Example commands:

```text
Calculate 25*4
```

```text
Solve x**2 - 4
```

```text
Find derivative of x**3
```

```text
Integral of x**2
```

The assistant interprets the expression and returns the calculated result.

---

# 📐 Physics Calculator

The system contains a basic natural-language physics calculator.

Currently implemented calculations include:

## Force

```text
F = ma
```

Example:

```text
What is the force when mass 10 and acceleration 5?
```

## Pressure

```text
P = F/A
```

## Speed

```text
v = d/t
```

The assistant extracts the required numerical values from the user's command and performs the corresponding calculation.

---

# 💾 Dynamic Memory

The assistant maintains persistent information using JSON files.

The project uses memory files for:

```text
memory.json
image_memory.json
audio_memory.json
```

The system can store:

* Learned facts
* Image data and image features
* Voice feature vectors

This allows the assistant to maintain information between interactions.

---

# 💻 Application Control

The assistant can automatically search common Windows application directories and create an application index.

It can then launch applications using voice commands.

Examples:

```text
Open calculator
```

```text
Open Notepad
```

The system searches its application index and attempts to launch the requested program.

---

# 🌐 Website Control

Websites can also be opened using voice commands.

Examples:

```text
Open YouTube
```

```text
Open GitHub
```

```text
Open Google
```

The assistant converts the requested website name into a URL and opens it through the default web browser.

---

# 🔤 Word Prediction

The assistant uses Python's `difflib` module for basic word and command correction.

When the user's command does not exactly match an application, website, or stored knowledge entry, the system searches for a close textual match.

This helps improve command handling when there are small differences in the spoken input.

---

# 🔊 Text-to-Speech

After processing a command, the assistant generates a spoken response using the `pyttsx3` text-to-speech engine.

The interaction cycle is:

```text
User speaks
     ↓
Speech Recognition
     ↓
Command Processing
     ↓
Task Execution
     ↓
Response Generation
     ↓
Text-to-Speech
```

---

# 📝 Example Commands

## General

```text
Hello
```

```text
What is your name?
```

```text
What is the time?
```

## Mathematics

```text
Calculate 25*10
```

```text
Solve x**2 - 4
```

```text
Find derivative of x**3
```

```text
Integral of x**2
```

## Physics

```text
What is the force when mass 10 and acceleration 5?
```

```text
What is the pressure when force 100 and area 5?
```

```text
What is the speed when distance 100 and time 5?
```

## Image Processing

```text
Capture image
```

```text
Match image
```

```text
Clear image
```

## Voice Processing

```text
Record audio
```

```text
Match audio
```

## Memory

```text
Learn that Python is a programming language
```

## Applications and Websites

```text
Open Calculator
```

```text
Open YouTube
```

```text
Open GitHub
```

---

# 🛠️ Technologies & Libraries

## Programming Language

```text
Python
```

## Major Libraries

```text
SpeechRecognition
pyttsx3
NumPy
SciPy
SymPy
OpenCV
Librosa
scikit-image
Pillow
Requests
BeautifulSoup
Wikipedia
googlesearch
```

## Core Technologies

```text
Artificial Intelligence
Digital Signal Processing
Natural Language Processing
Computer Vision
Speech Recognition
Voice Biometrics
Image Processing
Mathematical Computing
Information Retrieval
Desktop Automation
Human-Computer Interaction
```

---

# 📦 Installation

Clone the repository:

```bash
git clone https://github.com/your-username/advanced-ai-voice-assistant.git
```

Enter the project directory:

```bash
cd advanced-ai-voice-assistant
```

Install the required Python packages:

```bash
pip install SpeechRecognition pyttsx3 numpy scipy sympy requests beautifulsoup4 googlesearch-python wikipedia pillow opencv-python librosa scikit-image
```

A working microphone is required for voice interaction.

A webcam is required for webcam-based image capture and matching.

An active internet connection is required for Google Speech Recognition and external information retrieval.

---

# ▶️ Running the Assistant

Run the main Python program:

```bash
python main.py
```

The assistant initializes the required modules and begins listening for voice commands.

Speak a command through the connected microphone and wait for the assistant to process and respond.

To terminate the assistant, say:

```text
Bye
```

---

# 📁 Project Structure

```text
Advanced-AI-Voice-Assistant/
│
├── main.py
├── memory.json
├── image_memory.json
├── audio_memory.json
│
├── recorded_audio/
│
├── captured_images/
│
├── README.md
└── requirements.txt
```

---

# ⚙️ Main Processing Pipeline

```text
Microphone Input
       ↓
Audio Recording
       ↓
Bandpass Filtering
       ↓
FFT Processing
       ↓
Signal Smoothing
       ↓
Google Speech Recognition
       ↓
Natural-Language Command
       ↓
Command Classification
       ↓
┌──────────────┬──────────────┬──────────────┐
│              │              │              │
Voice        Image          Math/Physics   Knowledge
Matching     Processing     Calculation    Retrieval
│              │              │              │
MFCC         Histogram      SymPy          Memory
Cosine       Matching       Physics        Wikipedia
Similarity   Deblurring     Solver         Google Search
│              │              │              │
└──────────────┴──────────────┴──────────────┘
                       ↓
                Response Generation
                       ↓
                 Text-to-Speech
```

---

# 🎯 Project Objectives

The main objectives of the project are:

1. Develop a functional Python-based voice assistant.
2. Integrate speech recognition with DSP-based preprocessing.
3. Implement speaker identification using MFCC features.
4. Develop image matching using histogram-based features.
5. Implement image restoration using Richardson–Lucy deconvolution.
6. Develop mathematical and basic physics-solving capabilities.
7. Implement a persistent dynamic knowledge system.
8. Integrate external information retrieval.
9. Enable voice-controlled application and website launching.
10. Develop a modular architecture that can be expanded with additional AI capabilities.

---

# 💡 Project Strengths

The main strength of this project is its **multimodal and modular architecture**.

Instead of depending on a single AI technique, the system combines:

```text
Speech
+
DSP
+
NLP
+
Voice Biometrics
+
Computer Vision
+
Mathematics
+
Physics
+
Memory
+
Web Search
+
Desktop Automation
```

Each major function is implemented as an independent component, making the system easier to extend and upgrade.

For example, the current histogram-based image matching system could later be replaced with CNN-based image embeddings, while the speech-recognition system could be upgraded to an offline neural speech-recognition model.

---

# ⚠️ Limitations

The current implementation has several limitations:

* Speech recognition relies on Google's API and therefore requires internet connectivity.
* DSP preprocessing, MFCC extraction, image processing, and external queries can introduce processing latency.
* Histogram-based image matching is less robust than deep-learning-based image embeddings.
* Richardson–Lucy deconvolution may be less effective for severe blur and noise.
* Natural-language understanding primarily relies on keyword-based command recognition.
* Voiceprints and images are stored locally without encryption.
* Environmental noise can reduce speech-recognition and speaker-matching accuracy.
* The system currently lacks a dedicated authentication layer.

---

# 🔮 Future Improvements

Potential future improvements include:

* Offline speech recognition
* Wake-word detection
* Deep-learning-based speaker recognition
* CNN-based image recognition
* Face recognition
* Advanced NLP and semantic intent detection
* Secure encrypted memory
* User authentication
* GPU acceleration
* Graphical user interface
* More advanced physics and engineering calculators
* Improved conversational memory
* IoT and smart-home integration
* Multi-user voice profiles
* More robust image restoration
* Real-time visual object recognition

---

# 🧪 Engineering & AI Concepts Demonstrated

This project demonstrates practical implementation of:

* Artificial Intelligence
* Digital Signal Processing
* Speech Signal Processing
* Natural Language Processing
* Speech Recognition
* Speaker Recognition
* MFCC Feature Extraction
* Cosine Similarity
* Computer Vision
* Histogram-Based Image Matching
* Richardson–Lucy Deconvolution
* Mathematical Symbolic Processing
* Physics Computation
* Information Retrieval
* JSON-Based Data Storage
* Desktop Automation
* Human-Computer Interaction

---

# 📚 Project Scope

This project combines multiple areas of electrical engineering, computer engineering, and artificial intelligence into one practical system.

The integration of **DSP and AI** is particularly important because the assistant processes raw microphone signals before performing speech recognition. The system also demonstrates how signal processing, computer vision, mathematical computation, and intelligent decision-making can work together within a single application.

---

# 📌 Conclusion

This project demonstrates the development of a **multimodal AI voice assistant** capable of performing significantly more than basic voice-command execution.

By integrating **speech recognition, DSP, NLP, voice biometrics, computer vision, mathematical computation, physics calculations, dynamic memory, web information retrieval, and desktop automation**, the project provides a strong foundation for a more advanced personal AI assistant.

The modular architecture also makes it possible to replace or upgrade individual components in the future, including speech recognition, image recognition, speaker identification, natural-language understanding, and memory management.

---

## 👨‍💻 Project Information

**Project:** Advanced AI Voice Assistant

**Programming Language:** Python

**Project Type:** Multimodal AI / Personal Voice Assistant

**Primary Areas:** Artificial Intelligence, Digital Signal Processing, Natural Language Processing, Computer Vision, Speech Processing, Voice Biometrics

---

## ⭐ Project

Feel free to explore the source code, experiment with the individual modules, and extend the assistant with new AI, DSP, computer-vision, and automation capabilities.

```
```


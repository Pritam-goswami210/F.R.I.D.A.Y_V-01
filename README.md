# F.R.I.D.A.Y. Core Command Center

An advanced, interactive Windows PC automation and voice assistant system inspired by Iron Man's F.R.I.D.A.Y. This project combines a **Flask-powered web dashboard**, a **3D reactive hologram interface (Three.js)**, **AI-driven intent extraction (Gemini API)**, **AI Text-to-Speech (Deepgram API)**, and **MediaPipe computer vision** for real-time gesture control.

<blockquote>
  <p align="left">
    <strong>⚠️ <span style="color: #ff3333; font-size: 1.1em;">WARNING: DEVELOPMENT BUILD ONLY</span></strong><br>
    <span style="color: #ff5555;">This application is currently running on a <strong>private server under active development</strong>. It is unstable, experimental, contains bugs, and is missing critical security protocols. <strong>DO NOT use this for personal use, production environments, or store sensitive data within it. Use at your own risk.</strong></span>
  </p>
</blockquote>

---

## Features

### Intelligent Core Processing
* **Gemini-Powered Intent Parsing:** Automatically parses user prompts to determine whether they are structural system commands or conversational chats. 
* **Deepgram Text-to-Speech:** Real-time, ultra-low latency voice responses generated asynchronously so the main loop never stutters.

### Windows PC Automation & Controls
* **Media & Volume Management:** Precise system master volume or isolated app-specific volume controls (Spotify, YouTube, Chrome) using `pycaw`.
* **App Ecosystem:** Quick launching and automated forced-termination (`taskkill`) for standard applications (Chrome, Spotify, VS Code, Calculator, and custom shortcuts).
* **System Commands:** Execute system actions like locking your workstation, scheduling or cancelling shutdowns, capturing screenshots, and fetching real-time telemetry metrics.

### Futuristic Dashboard UI & Gestures
* **3D Audio-Reactive Hologram:** Features an interactive Three.js 3D sphere and ring matrix that scales, pulses, and shifts seamlessly based on user interactions and system state.
* **Dual-Wave Equalizer:** A canvas-based interactive waveform visualizer that tracks processing states and voice outputs.
* **MediaPipe Hand Tracking:** Use your webcam for interactive 3D navigation. A closed pinch gesture lets you translate and pan the scene, while an open hand scales, zooms, and rotates the 3D core in real time.

---

## 🛠️ Tech Stack

* **Backend Framework:** Python, Flask, Asyncio, Threading
* **AI Ecosystem:** Google GenAI SDK (`gemini-3.1-pro-preview`), Deepgram Aura TTS API
* **OS & Hardware Integration:** Pycaw (Python Audio Control), Comtypes, PyAutoGUI, Psutil, Pygame (Audio Mixer)
* **Frontend Design:** HTML5, CSS3 Variables (Futuristic Cyberpunk Glow), JavaScript (ES6)
* **Graphics & Vision:** Three.js (WebGL), OrbitControls, UnrealBloomPass, MediaPipe Hands API

---

## 💻 Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com
cd friday-command-center
```

### 2. Install Required Dependencies
Make sure you are running a Windows environment, then install the Python libraries:
```bash
pip install flask google-genai deepgram-sdk pycaw comtypes pyautogui psutil pygame requests pillow python-dotenv
```

### 3. Configure Environment Variables
Create a file named `.env` in the root directory of your workspace. You must supply your own cloud processing API keys:

* **Get your Gemini API Key:** Register on [Google AI Studio](https://aistudio.google.com/welcome)
* **Get your Deepgram API Key:** Generate a token via the [Deepgram Console](https://deepgram.com)

Populate your `.env` file using the following layout format:
```env
DEEPGRAM_API_KEY=your_deepgram_api_key_here
GEMINI_API_KEY=your_gemini_api_key_here
```

### 4. Run the Application
Launch the control hub by running:
```bash
python main.py
```
Open your browser and navigate to `http://localhost:5000` to access the interface.

---

## 🔒 Security Note
The internal command endpoint requires an authorized authorization check. The default password string for executing remote post actions across the network framework is set to `"friday"` inside the configuration file. Change this variable before deploying or sharing access within shared local networks.

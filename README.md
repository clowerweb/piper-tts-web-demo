# 🃏 Piper TTS Web Demo

A web-based demo of **Piper TTS** - a high-quality neural text-to-speech model running entirely in your browser using ONNX Runtime Web! [Try the demo here](https://clowerweb.github.io/piper-tts-web-demo/).

## ✨ Features

- 🎤 **904 Different Voices** - Extensive voice selection from LibriTTS dataset
- ▶️ **Voice Preview** - Click play button to instantly preview any voice
- ⚡ **Adjustable Speed** - From 0.5x (slow) to 2.0x (fast)
- 🌐 **100% Browser-Based** - No server required, runs completely locally
- 📱 **Real-time Generation** - Fast inference using WebAssembly (WASM)

## 🚀 Quick Start

1. **Clone the repository:**
   ```bash
   git clone https://github.com/clowerweb/piper-tts-web-demo
   cd piper-tts-web-demo
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

4. **Open your browser** and navigate to `http://localhost:5173`

5. **Type some text and generate speech!** 🎉

## 📋 Requirements

- Node.js 16+
- Modern browser with WebAssembly support
- ~75MB disk space for model files

## 🏗️ How It Works

This demo replicates the Piper TTS pipeline in JavaScript.

## 🎛️ Controls

- **Voice Selection** - Choose from 904 different voices (Voice 1 - Voice 904)
- **Voice Preview** - Click the ▶️ button to preview any voice with "Hello, this is a voice preview"
- **Speed Control** - Adjust speech rate from 0.5x (slower) to 2.0x (faster)

## 📦 Model Information

This demo uses the **Piper TTS** model:
- **Size:** ~75MB ONNX model
- **Quality:** High-quality speech synthesis
- **Speed:** ~3-5x Real-time generation in browser

**Original Model:**
- 📁 **GitHub:** [OHF-Voice/piper1-gpl](https://github.com/OHF-Voice/piper1-gpl)
- 🤗 **Hugging Face:** [rhasspy/piper-voices](https://huggingface.co/rhasspy/piper-voices)

## 🛠️ Technical Stack

- **Frontend:** Vue 3 + Vite + Tailwind CSS 4
- **ML Runtime:** ONNX Runtime Web (WebAssembly)
- **Phonemization:** phonemizer.js (espeak-ng backend)
- **Audio Processing:** Web Audio API + WAV encoding
- **Text Processing:** Custom text cleaner with smart chunking
- **Model Format:** ONNX model + JSON configuration

## 📁 Project Structure

```
├── index.html              # Main HTML entry point
├── src/
│   ├── App.vue             # Main Vue application
│   ├── main.js             # Application entry point
│   ├── components/         # Vue components
│   │   ├── AudioChunk.vue  # Audio playback component
│   │   ├── SpeedControl.vue
│   │   ├── TextStatistics.vue
│   │   ├── ThemeToggle.vue
│   │   └── VoiceSelector.vue # Voice selection with preview
│   ├── lib/
│   │   └── piper-tts.js   # Core Piper TTS implementation
│   ├── utils/
│   │   ├── model-cache.js  # Model caching utilities
│   │   ├── text-cleaner.js # Text processing & chunking
│   │   └── utils.js        # General utilities
│   └── workers/
│       └── tts-worker.js   # Web Worker for TTS processing
├── public/
│   ├── onnx-runtime/       # ONNX Runtime WASM files
│   └── tts-model/          # Piper model files
│       ├── en_US-libritts_r-medium.onnx
│       └── en_US-libritts_r-medium.onnx.json
├── package.json            # Dependencies
└── vite.config.js          # Vite configuration
```

## 🤝 Contributing

Contributions are welcome! Feel free to:
- Report bugs or issues
- Suggest new features  
- Submit pull requests
- Improve documentation

## 📄 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE](LICENSE) file for details.

### Third-Party Licenses

- **Piper Voices** - MIT License ([rhasspy/piper-voices](https://huggingface.co/rhasspy/piper-voices))
- **LibriTTS Dataset** - CC-BY 4.0 License (original voice recordings)
- **phonemizer.js** - MIT License (espeak-ng phonemization)

## 🙏 Acknowledgments

- **Piper TTS Team** ([rhasspy/piper](https://github.com/rhasspy/piper)) for the amazing neural TTS model
- **Piper Voices** ([rhasspy/piper-voices](https://huggingface.co/rhasspy/piper-voices)) for pre-trained voice models
- **LibriTTS Dataset** for the high-quality voice recordings used in training
- **Microsoft ONNX Runtime** for WebAssembly inference capabilities
- **espeak-ng** for phonemization support

## 🐛 Troubleshooting

**Model not loading?**
- Check browser console for CORS or network errors
- Ensure you have ~75MB free disk space for model caching
- Try refreshing the page to retry model download

**Audio not playing?**
- Try different browsers (Chrome/Firefox recommended)
- Check if audio autoplay is blocked in browser settings
- Click the page first to enable audio context (required by browsers)

**Voice preview not working?**
- Make sure the model is fully loaded (wait for "ready" status)
- Check browser audio permissions
- Try a different voice to see if it's voice-specific

**Slow performance?**
- Close other browser tabs to free up memory
- The 75MB model may take time to load on slower connections
- WebAssembly performance varies by browser and device

---

Made with ❤️ using the Piper TTS model

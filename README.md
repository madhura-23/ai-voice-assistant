# 🎤 AI Voice Assistant

A modern, real-time voice-based AI assistant built with React and Claude API. Talk naturally, get intelligent responses, and hear them spoken back to you.

![AI Voice Assistant Demo](https://img.shields.io/badge/React-18.0+-61dafb?logo=react&logoColor=white)
![Claude API](https://img.shields.io/badge/Claude%20API-Integrated-000000)
![Web Speech API](https://img.shields.io/badge/Web%20Speech%20API-Enabled-blue)

## ✨ Features

- 🎤 **Voice Input** - Speak naturally using your device's microphone
- 🤖 **AI Powered** - Powered by Claude Opus 4 for intelligent responses
- 🔊 **Voice Output** - Hear responses read aloud automatically
- 💬 **Chat History** - View full conversation history
- 🎨 **Modern UI** - Sleek dark mode interface with smooth animations
- ⚡ **Real-time Processing** - Instant transcription and response
- 📱 **Responsive Design** - Works on desktop and tablets
- 🔐 **API Key Management** - Secure key input with visual confirmation

## 🚀 Quick Start

### Prerequisites
- Node.js 16+ and npm
- A Claude API key from [Anthropic](https://console.anthropic.com)
- A modern browser with Web Speech API support (Chrome, Edge, Safari)

### Installation

1. **Clone or create a React project**
   ```bash
   npx create-react-app voice-assistant
   cd voice-assistant
   npm install lucide-react
   ```

2. **Replace the App component**
   - Copy `AIVoiceAssistant.jsx` to your `src` folder
   - Update `src/App.js`:
   ```javascript
   import AIVoiceAssistant from './AIVoiceAssistant';

   function App() {
     return <AIVoiceAssistant />;
   }

   export default App;
   ```

3. **Get your Claude API Key**
   - Visit [Anthropic Console](https://console.anthropic.com/account/keys)
   - Create a new API key
   - Keep it safe! (Never commit to public repos)

4. **Run the application**
   ```bash
   npm start
   ```

5. **Enter API Key**
   - Paste your Claude API key in the input field
   - Click "Set Key" to configure

## 📖 How to Use

1. **Start Recording** - Click the microphone button to begin voice input
2. **Speak Naturally** - Say what you want to ask the AI
3. **Stop Recording** - The app automatically stops or click "Stop Recording"
4. **Review & Send** - See your transcript, click send to submit
5. **Hear Response** - Claude responds and speaks the answer aloud

**Pro Tips:**
- Use a quiet environment for better speech recognition
- Speak clearly and at a normal pace
- The assistant understands context from previous messages
- Click the speaker icon to replay any response

## 🏗️ Architecture

```
┌─────────────────────────────────────────┐
│          User's Voice (🎤)              │
└────────────────┬────────────────────────┘
                 │
                 ▼
        ┌────────────────────┐
        │ Web Speech API     │
        │ (Speech-to-Text)   │
        └────────┬───────────┘
                 │
                 ▼
        ┌────────────────────┐
        │  React Component   │
        │  (Processing)      │
        └────────┬───────────┘
                 │
                 ▼
        ┌────────────────────┐
        │  Claude API        │
        │  (AI Response)     │
        └────────┬───────────┘
                 │
                 ▼
        ┌────────────────────┐
        │ Web Speech API     │
        │ (Text-to-Speech)   │
        └────────┬───────────┘
                 │
                 ▼
        ┌────────────────────┐
        │  User's Speakers   │
        │  (🔊 Audio Output) │
        └────────────────────┘
```

## 🔧 Configuration

### Customizing the Model
Edit the model in `AIVoiceAssistant.jsx`:
```javascript
// Current: claude-opus-4-6 (most capable)
// Options: claude-sonnet-4-6 (faster), claude-haiku-4-5 (most affordable)
model: 'claude-opus-4-6'
```

### Adjust Voice Settings
```javascript
const utterance = new SpeechSynthesisUtterance(text);
utterance.rate = 1;    // Speech speed (0.5 to 2)
utterance.pitch = 1;   // Voice pitch (0 to 2)
utterance.volume = 1;  // Volume (0 to 1)
```

### Change Language
```javascript
recognitionRef.current.lang = 'es-ES'; // Spanish
recognitionRef.current.lang = 'fr-FR'; // French
recognitionRef.current.lang = 'de-DE'; // German
```

## 🌐 Browser Support

| Browser | Voice Input | Voice Output | Status |
|---------|-----------|--------------|--------|
| Chrome  | ✅ | ✅ | Fully Supported |
| Edge    | ✅ | ✅ | Fully Supported |
| Safari  | ✅ | ✅ | Fully Supported |
| Firefox | ⚠️ | ✅ | Partial Support |

## 📦 Environment Variables (Optional)

For production, store API key securely:
```env
REACT_APP_CLAUDE_API_KEY=sk-ant-xxx
```

Then update the component to use `process.env.REACT_APP_CLAUDE_API_KEY`

## 🚀 Deployment

### Vercel (Recommended)
```bash
npm install -g vercel
vercel
```

### GitHub Pages
```bash
npm run build
npm install --save-dev gh-pages
# Add to package.json: "homepage": "https://username.github.io/repo-name"
npm run deploy
```

### Docker
```dockerfile
FROM node:18-alpine
WORKDIR /app
COPY . .
RUN npm install && npm run build
EXPOSE 3000
CMD ["npm", "start"]
```

## 🔐 Security

- **Never commit API keys** to version control
- Use environment variables for production
- API keys are sent only to Anthropic's servers
- Implement rate limiting for production use
- Consider adding user authentication

## ⚙️ System Requirements

- **Minimum:** 2GB RAM, 1GB storage
- **Recommended:** 4GB RAM, 2GB storage
- **Internet:** Stable connection for API calls

## 📊 Performance

- **First Load:** ~2-3 seconds
- **Voice Recognition:** Real-time (latency depends on speech length)
- **API Response:** 1-5 seconds (depending on response complexity)
- **Voice Output:** Generated locally (no additional latency)

## 🐛 Troubleshooting

### "Microphone not working"
- Check browser permissions (Settings > Privacy > Microphone)
- Try a different browser
- Ensure microphone is not in use by another app

### "API Key Error"
- Verify your key at [Anthropic Console](https://console.anthropic.com)
- Check that you're using the correct key
- Ensure your account has API access enabled

### "Speech not being recognized"
- Speak clearly and at normal pace
- Reduce background noise
- Check if your language setting matches your speech language
- Try a shorter phrase first

### "No audio output"
- Check device volume settings
- Ensure speakers/headphones are connected
- Try unmuting the browser tab
- Check browser permissions for audio playback

## 📈 Future Enhancements

- [ ] Multiple language support with auto-detection
- [ ] Voice cloning for personalized responses
- [ ] Conversation memory (persistent history)
- [ ] Custom system prompts
- [ ] Multi-turn context awareness
- [ ] Rate limiting and usage tracking
- [ ] Dark/light theme toggle
- [ ] Export conversation history

## 📝 License

MIT License - feel free to use this project for personal and commercial purposes

## 🤝 Contributing

Contributions are welcome! Feel free to:
1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

## 📞 Support

- 📖 [Claude API Docs](https://docs.claude.com)
- 🆘 [MDN Web Speech API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Speech_API)
- 💬 [Discord Community](https://discord.gg/anthropic)

## 🎉 Showcase

This project is perfect for showcasing on:
- **GitHub** - Great starter project for voice AI
- **LinkedIn** - Impressive portfolio piece
- **HackerNews** - Interesting tech demo
- **Product Hunt** - Potential feature product

---

**Made with ❤️ using React and Claude AI**

[⬆ back to top](#-ai-voice-assistant)

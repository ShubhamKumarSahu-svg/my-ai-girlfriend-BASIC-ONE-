# My AI Girlfriend – Quick Guide

A modern Next.js app for chatting with an AI girlfriend using voice and text.

## Features

- **Voice input (STT):** Speak to the app, your speech is transcribed to text.
- **AI chat (Gemini):** Your text is sent to Google Gemini for a smart reply.
- **Voice output (TTS):** The AI's reply is spoken back to you using ElevenLabs TTS.

---

## How It Works (Flow Diagram)

```mermaid
flowchart LR
    A[🎤 User speaks] --> B[STT: Speech-to-Text (browser)]
    B --> C[Gemini API (AI chat)]
    C --> D[TTS: Text-to-Speech (ElevenLabs)]
    D --> E[🔊 AI voice reply]
```

---

## Project Structure

- `src/app/api/gemini/route.ts` – Handles chat with Gemini (AI)
- `src/app/api/tts/route.ts` – Handles text-to-speech (TTS)
- `src/components/SpeechClient.tsx` – Main UI, manages voice and chat
- `src/types/global.d.ts` – Types for browser speech APIs

---

## Setup

1. **Install dependencies:**
   ```bash
   npm install
   ```
2. **Add API keys:**
   - Create `.env.local` in the project root:
     ```env
     GEMINI_API_KEY=your_gemini_key
     EL_API_KEY=your_elevenlabs_key
     ```
3. **Run the app:**
   ```bash
   npm run dev
   ```
   Open [http://localhost:3000](http://localhost:3000)

---

## Usage

- Click the microphone button to start speaking.
- Your speech is transcribed and sent to Gemini.
- The AI's reply is spoken back to you.

---

## Customization

- Change AI personality: Edit the prompt in `SpeechClient.tsx`.
- Change TTS voice: Edit the ElevenLabs voice ID in `tts/route.ts`.

---

## Troubleshooting

- **No sound?** Check your browser permissions and API keys.
- **API errors?** See logs in your terminal and browser console.

---

## Learn More

- [Next.js Docs](https://nextjs.org/docs)
- [Google Gemini API](https://ai.google.dev/)
- [ElevenLabs TTS](https://docs.elevenlabs.io/)

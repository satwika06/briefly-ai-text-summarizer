# Briefly AI — Text Summarizer

A small student project that turns pasted text into a concise summary using the Gemini API.

## Features
- Paste text (40–20,000 characters)
- Choose quick bullets, balanced summary, or detailed summary
- Sample text for quick testing
- Loading and error states
- Copy generated summary
- Prompt instructions to avoid inventing facts and treat source text as data
- API key kept on the server in `.env`, not in browser JavaScript

## Requirements
- Node.js 18 or newer
- Internet connection
- Gemini API key from Google AI Studio: https://aistudio.google.com/apikey

## Run locally
1. Extract the project folder and open it in VS Code.
2. Open a terminal in the `ai-text-summarizer` folder.
3. Run `npm install`.
4. Copy `.env.example` to a new file named `.env`.
5. Open `.env` and replace `put_your_own_key_here` with your own Gemini API key. Do not share the key or upload `.env` to GitHub.
6. Run `npm start`.
7. Open `http://localhost:3000` in your browser.

## How it works
1. The user pastes source text and selects a summary style in the browser.
2. Frontend JavaScript sends the text and style to `POST /api/summarize` on the local Express server.
3. The server validates the input and builds instructions for the AI model.
4. The server calls Gemini using the API key stored in an environment variable.
5. The server sends the summary back as JSON, and the browser displays it.

## Limitations and responsible use
- This is a local interview demo, not a production-deployed service.
- Model output may omit context or contain errors. Compare it with the original source.
- Do not submit confidential, personal, or client data.
- API availability, model access, quotas, and charges depend on the user's Google AI Studio account and current terms.
- The model identifier is configured in `server.js`; update it if Google changes available model names.

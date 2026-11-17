# Jarvis voice assistant

## Build
- Replace the template home screen with a polished Jarvis chat console: conversation history, text entry, microphone input, and spoken replies.
- Connect Groq chat completion and ElevenLabs text-to-speech through server-side calls, keeping credentials private. Use the active Groq GPT-OSS 120B model selected for the requested free-tier preference.
- Use browser speech recognition for microphone input when supported; keep text entry available as a fallback. Provide a voice on/off control and clear connection and error states.
- Add route-specific metadata and design tokens suited to a focused, modern voice-assistant workspace.
- Keep this first version account-free; conversation history lives only for the current page session.

## Technical details
- Groq calls go through the linked Groq connector gateway; ElevenLabs calls use its linked server-only API key.
- Add validated TanStack server functions for chat and speech generation. Do not expose keys to the browser or persist conversation content.
- Keep the generated Cloud auth bearer middleware intact; no user login is added for this single-user assistant experience.

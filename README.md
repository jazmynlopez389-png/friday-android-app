# FRIDAY Android Assistant — AI-connected starter

This is a native Android/Jetpack Compose starter with a secure-backend pattern.

## Included
- Futuristic dark navy/cyan FRIDAY dashboard
- Chat UI with recent conversation context sent to the backend
- Android speech recognition (tap microphone; Android handles recognition)
- Android text-to-speech replies
- Built-in voice-style controls (Calm, Bright, Deep; actual voices depend on the phone's installed TTS engine)
- Reminder-entry prototype (not yet scheduled as notifications)

## Important limitations
- The app does not clone a movie character's exact voice. It uses adjustable built-in Android speech synthesis.
- Voice input is tap-to-talk, not an always-listening wake word.
- Reminders are not yet scheduled as Android notifications.
- Do not put an AI provider API key in the Android app. The included server keeps it on the server.

## Configure the AI server
1. Install Node.js 20 or newer on a computer/server.
2. Open the `server` folder and run `npm install`.
3. Set environment variables on the server:
   - `OPENAI_API_KEY` = your private API key
   - `OPENAI_MODEL` = `gpt-4.1-mini` (or another model enabled for your account)
4. Run `npm start`.
5. Deploy the server behind HTTPS. Do not expose it as an unauthenticated public endpoint in a real deployment; add user authentication, request limits, and abuse protection.
6. In `MainActivity.kt`, replace `https://YOUR-SERVER.example.com` with your deployed HTTPS base URL.
7. Rebuild and run the Android app.

The server uses the OpenAI Responses API. API usage may incur charges; review pricing and account settings before enabling it. Keep keys private and ask a trusted adult to help with account setup if needed.

## Run Android app
1. Open this project folder in Android Studio.
2. Let Gradle sync.
3. Run on an Android 8.0/API 26+ device or emulator.
4. Grant microphone permission when prompted.

## Production checklist
- Add authentication and per-user authorization
- Add rate limiting and usage caps
- Use HTTPS only
- Add privacy notice and delete-chat controls
- Implement Android notification scheduling with permission handling
- Add tests and persistent encrypted local history if desired

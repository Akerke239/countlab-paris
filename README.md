# CountLab Paris — Rose Edition (Vercel)

Modern Paris-inspired design with warm rose, terracotta, cream and sage accents. Includes the Pascal–Fermat letter intro, animated white pigeon, Paris lesson map, six location lessons with contextual Pierre AI chat, 10-question randomized assessment, answer key, local quiz history and text-only Groq AI tutor. **Photo uploads have been removed**.

## Deploy
1. Extract this ZIP. Upload its contents (including `api/tutor.js`) to the root of a GitHub repository.
2. In Vercel, import the repository as a project (Framework Preset: Other).
3. Under Project Settings → Environment Variables, set `GROQ_API_KEY` to your private key. Optionally set `GROQ_MODEL=openai/gpt-oss-120b`.
4. Redeploy to apply the environment variable.
5. Test the **text-only** AI Tutor and the **Ask Pierre** chat inside a Paris location. Do not paste your API key into chat or GitHub.

## Notes
- Vision models and `GROQ_VISION_MODEL` are no longer used.
- AI requests use `/api/tutor`; opening `index.html` locally will not activate AI.
- The white pigeon carrying Pascal and Fermat's letter is fictional; their correspondence in 1654 is historical.
- Browser sound may require clicking the sound toggle first.
- The AI integration requires a valid Groq key and may be subject to rate limits. AI can make mathematical errors.

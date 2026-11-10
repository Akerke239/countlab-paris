# CountLab — Groq AI Math Tutor

Main text model: `openai/gpt-oss-120b`. Image transcription model: `qwen/qwen3.8-27b` (vision-capable). Both are accessed through Groq. The main GPT-OSS model cannot directly process photos.

## Deploy
1. Create a Groq API key at https://console.groq.com/keys. Do not paste it into HTML, GitHub or chat.
2. Upload the complete folder to a Git repository, then in Netlify choose **Add new project → Import an existing project**. Keep `netlify.toml` and `netlify/functions/tutor.js`.
3. In Netlify **Project configuration → Environment variables**, create `GROQ_API_KEY` with your secret. Optionally set `GROQ_MODEL=openai/gpt-oss-120b` and `GROQ_VISION_MODEL=qwen/qwen3.8-27b`. Ensure Functions can access the variables.
4. Redeploy, then open the HTTPS site URL (not a `file://` page). Test Guided Feedback with text and a photo.
5. If a model is unavailable to your account, inspect Groq's current model list and adjust the corresponding environment variable. Check **Netlify → Logs → Functions → tutor** for errors.

## Privacy, safety and limits
- Uploaded photos and question text are sent to Groq. Do not upload private student information.
- The secret key remains in the Netlify Function, not the browser. Never commit `.env` files.
- This example does not implement login or server-side request throttling. A public site may consume API quota or incur charges; set usage limits and add abuse protection before sharing widely.
- Quiz history is stored only in the current browser's localStorage.
- Mathematical outputs may be wrong; verify them.
- MathJax uses a CDN and requires internet access.
- Static file previews cannot call Netlify Functions. Deploy the complete project.


Paris redesign: The illustrated map is a stylized learning map, not a navigation map. All scenarios at landmarks are fictional teaching examples. The Groq API and Netlify setup are unchanged.

Opening intro: Pascal/Fermat correspondence historical; pigeon delivery is fictional. Audio is synthesized in-browser only after click. Replay button on hero.


INTERACTIVE EDITION: Modern visual redesign, six animated location stories, general formulas and worked examples, redesigned quiz answer key, optional Web Audio sounds, and Pascal/Fermat intro. Audio requires user interaction.

IMPORTANT: Netlify function needs GROQ_API_KEY in site environment variables, followed by a fresh deployment. The image-reading model can vary by Groq account; GROQ_VISION_MODEL may need adjustment. The public endpoint has no per-user authentication; configure access controls and usage limits before sharing widely.

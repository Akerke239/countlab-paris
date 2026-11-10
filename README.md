# CountLab Paris — Cinematic Website

This is a working website project, not a static design mockup. Open `index.html` locally for the intro, illustrated map, six location scenes, formula lessons, and randomized quiz. Groq AI needs a Netlify deployment with a server-side key.

## Deployment
1. Upload the complete project to GitHub (keep `assets/`, `netlify/functions/tutor.js`, `netlify.toml`, and `index.html`).
2. Import the repository into Netlify.
3. In Netlify project environment variables, add `GROQ_API_KEY` with your Groq Console key; keep it secret.
4. Redeploy. Use a currently available vision model in `GROQ_VISION_MODEL` if image recognition is needed.
5. Test the tutor at the live site, and inspect Netlify Function logs if an error occurs.

The illustration assets are integrated as real website imagery; UI text, lesson formulas, scene buttons, quizzes and AI calls are HTML/JS, not part of an image. The scenes are fictional educational examples. The intro pigeon courier is fictional; Pascal and Fermat's 1654 correspondence is historical.

Audio effects start only after a user enables Sound. API integration has not been live-tested with a private key.

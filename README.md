# CountLab Paris — Vercel + Groq

A clean, modern CountLab website with Paris-themed probability lessons, randomized 10-question quiz, answer key, local history, and a real Groq AI tutor. The Paris scenarios and pigeon Pierre are fictional. Pascal and Fermat exchanged letters in 1654.

## Deploy on Vercel (GitHub)
1. Extract this ZIP. Create a new GitHub repository and upload **all contents of this folder at the repository root**. The root must contain `index.html`, `vercel.json`, and the `api/tutor.js` file inside an `api` folder.
2. At https://vercel.com/new choose **Import Git Repository**, select the repository. Framework Preset: **Other**; Root Directory: `./`; Build Command: leave blank; Output Directory: leave blank. Deploy.
3. At https://console.groq.com/keys create a Groq API key. Never put it in GitHub, HTML, screenshots or chat.
4. In Vercel: Project → Settings → Environment Variables, add `GROQ_API_KEY` (value is the secret key) and enable **Production** (and Preview if needed).
5. Redeploy in Deployments. Visit the deployed HTTPS URL, open **AI Tutor**, and try `How many ways can 3 students be chosen from 8?`. Expected result: C(8,3)=56.
6. Test photo uploads separately. `openai/gpt-oss-120b` is the primary **text** model; images are transcribed first by the vision model. The default vision model is `meta-llama/llama-4-scout-17b-16e-instruct`. Groq model availability can change; if needed set `GROQ_VISION_MODEL` to an available vision model in your Groq account. Optional `GROQ_MODEL=openai/gpt-oss-120b`.

## Troubleshooting
- `GROQ_API_KEY is missing`: key was not added for Production, or deployment was not rebuilt after adding it.
- 404 at `/api/tutor`: verify `api/tutor.js` exists in GitHub at the repository root and redeploy.
- 401 from Groq: invalid/revoked key; create a new one.
- 429: rate limit; wait or review quota.
- Model unavailable: verify current Groq model IDs and account access.
- Inspect Vercel Project → Logs for server errors.
- Opening `index.html` locally can display the UI but **cannot run AI**.

## Notes
This example has no authentication or rate limiting. Public AI access may consume your Groq quota; add abuse protection before sharing broadly. Images/text sent to Groq for inference; do not upload personal student data. Quiz history stays in browser localStorage. AI can make mathematical mistakes; verify results. MathJax requires internet.

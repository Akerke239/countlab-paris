# CountLab Paris — Vercel (Groq vision fix)

This version preserves the original clean CountLab design, adds an opening pigeon-and-letter animation and clickable Paris learning map, and adds photo removal and Clear / New question controls.

## Deploy
1. Unzip and upload **all files and folders**, including `api/tutor.js`, to a GitHub repository.
2. Import the repository at https://vercel.com/new (Framework: Other).
3. In Vercel Project → Settings → Environment Variables set:
   - `GROQ_API_KEY`: your private Groq key (never add to source code)
   - `GROQ_MODEL`: `openai/gpt-oss-120b`
   - `GROQ_VISION_MODEL`: `qwen/qwen3.8-27b`
4. Set variables for Production and Redeploy the project. Environment changes do not affect already-built deployments.
5. Test a typed math question and an image question separately. If a model is unavailable to your account, inspect Vercel Function logs and check Groq Models.

Model reference: https://console.groq.com/docs/vision

Sound is a short synthesized chime activated by user click; browsers block automatic audio. Pierre is a fictional courier. Images are processed by Groq. Math explanations may contain mistakes.

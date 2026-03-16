# CV & Cover Letter Generator

AI-powered job application toolkit. Upload your CV + paste a job description → get a tailored CV, cover letter, recruiter email, and "About Me" in seconds.

**Live at:** `https://your-app.vercel.app`

---

## Stack

- **Frontend:** Vanilla HTML/CSS/JS — no framework, no build step
- **Backend:** Vercel Serverless Function (`/api/generate.js`) — proxies Anthropic API
- **AI:** Claude (`claude-opus-4-5`) via Anthropic API
- **PDF:** jsPDF (client-side)

The API key lives in Vercel environment variables. It never touches the browser.

---

## Deploy in 5 minutes

### 1. Push to GitHub

```bash
cd cv-generator
git init
git add .
git commit -m "Initial commit"

# Create repo on github.com, then:
git remote add origin https://github.com/YOUR_USERNAME/cv-generator.git
git branch -M main
git push -u origin main
```

### 2. Deploy to Vercel

Go to [vercel.com/new](https://vercel.com/new) → Import your GitHub repo → click **Deploy**.

Or via CLI:
```bash
npm i -g vercel
vercel login
vercel --prod
```

### 3. Add your API key

In the Vercel dashboard:
- Go to your project → **Settings** → **Environment Variables**
- Add: `ANTHROPIC_API_KEY` = `sk-ant-api03-...`
- Click **Save**, then **Redeploy**

That's it. Your app is live.

---

## Local development

```bash
npm i -g vercel
vercel dev   # runs both frontend and serverless functions locally on port 3000
```

Set up a local `.env` file:
```
ANTHROPIC_API_KEY=sk-ant-api03-...
```

---

## Project structure

```
cv-generator/
├── api/
│   └── generate.js       # Serverless function — Anthropic proxy
├── public/
│   └── index.html        # Full frontend app
├── vercel.json           # Routing config
├── package.json
└── README.md
```

---

## Features

- Upload CV (PDF or TXT) — AI reads your real experience
- Paste any job description
- Tone options: Executive, Technical, Creative, Academic
- Generates: ATS CV · Cover letter · Recruiter email · About Me (3 lengths)
- Download as PDF, HTML (for Word), or copy plain text
- Clean Harvard/MIT black & white CV format
- No login, no database, no tracking

---

## License

MIT

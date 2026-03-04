# 🏫 SFHS Chatbot

An AI-powered chatbot for San Francisco High School built with Groq AI + Vercel.

---

## 📁 File Structure

```
sfhs-chatbot/
├── index.html        ← Frontend (the chat UI)
├── api/
│   └── chat.js       ← Backend (talks to Groq API)
├── vercel.json       ← Vercel config
├── .gitignore        ← Keeps your API key safe
└── README.md
```

---

## 🚀 Setup & Deployment

### 1. Get Your Groq API Key
1. Go to https://console.groq.com
2. Sign up (free, no credit card)
3. Click **API Keys** → **Create API Key**
4. Copy and save it somewhere safe

### 2. Add Your School Info
Open `api/chat.js` and fill in the `systemPrompt` section with real SFHS data:
- History, mission, vision
- Academic strands
- Facilities
- Contact info

### 3. Push to GitHub
```bash
git init
git add .
git commit -m "initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/sfhs-chatbot.git
git push -u origin main
```

### 4. Deploy on Vercel
1. Go to https://vercel.com → Sign up with GitHub
2. Click **Add New Project** → Import your repo
3. Before deploying, go to **Environment Variables** and add:
   - **Name:** `GROQ_API_KEY`
   - **Value:** your Groq API key
4. Click **Deploy** ✅

### 5. Test Locally (Optional — needs Node.js)
```bash
npm i -g vercel
vercel dev
# Runs on http://localhost:3000
```

For Ngrok (to share localhost publicly):
```bash
# Sign up at ngrok.com, get your auth token, then:
ngrok config add-authtoken YOUR_NGROK_TOKEN
ngrok http 3000
```

---

## ⚠️ Important
- **NEVER** put your API key directly in `index.html` or any frontend file
- The key is safe in Vercel's environment variables (that's the whole point of the backend)
- The `.gitignore` prevents any `.env` files from being pushed to GitHub

# DishDecoder — deploy in 5 minutes for $0

## What's in this folder

```
dishdecoder/
├── index.html        ← the entire frontend
├── api/
│   └── scan.js       ← serverless function (hides your OpenAI key)
├── vercel.json       ← routing config
└── README.md
```

## Deploy steps

### 1. Get a free OpenAI API key
Go to https://platform.openai.com/api-keys → Create new secret key → copy it.
Add $5 credit at https://platform.openai.com/settings/billing (that's ~600 scans).

### 2. Push to GitHub
```bash
git init
git add .
git commit -m "dishdecoder mvp"
# create a repo on github.com, then:
git remote add origin https://github.com/YOUR_USERNAME/dishdecoder.git
git push -u origin main
```

### 3. Deploy to Vercel (free)
1. Go to https://vercel.com → Sign up with GitHub (free)
2. Click "Add New Project" → import your dishdecoder repo
3. Before deploying, click "Environment Variables"
4. Add: OPENAI_API_KEY = sk-your-key-here
5. Click Deploy

That's it. Vercel gives you a live URL like https://dishdecoder.vercel.app

### 4. Share the link
Send it to friends. Every scan costs you ~$0.01.
At 500 scans/month your cost is $5. Vercel hosting is free.

## Cost breakdown
| Users/month | Scans (avg 3/user) | OpenAI cost | Hosting |
|-------------|-------------------|-------------|---------|
| 10          | 30                | $0.25       | $0      |
| 100         | 300               | $2.50       | $0      |
| 1,000       | 3,000             | $25.00      | $0      |
| 10,000      | 30,000            | $250.00     | $0      |

Add a $4/month paywall at 100 users → profitable immediately.

## When you outgrow this
- **Rate limiting**: add Upstash Redis (free tier) to limit scans per IP
- **Auth + paywall**: add Supabase (free) + Stripe
- **Custom domain**: buy on Namecheap (~$10/yr), add in Vercel dashboard

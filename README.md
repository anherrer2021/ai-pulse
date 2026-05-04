# AI Pulse

AI industry news site with Wall Street Journal-style design. Features real-time AI news, top AI stock tracker, and an AI chatbot powered by Claude.

## Stack

- **Frontend:** HTML/CSS/JS — served by Nginx on Linode
- **Backend:** Node.js + Express — proxies Anthropic API calls securely
- **CI/CD:** GitHub Actions → auto-deploy to Linode on every push to `main`
- **CDN/WAF:** Akamai (configured separately)

## Local Development

### Backend
```bash
cd backend
cp .env.example .env
# Add your ANTHROPIC_API_KEY to .env
npm install
npm run dev
```

### Frontend
Open `frontend/index.html` in your browser. The API calls point to `http://localhost:3001`.

## Deployment

See `.github/workflows/deploy.yml`. Requires these GitHub Secrets:

| Secret | Description |
|--------|-------------|
| `LINODE_HOST` | Your Linode server IP |
| `LINODE_USER` | SSH username (e.g. `root`) |
| `LINODE_SSH_KEY` | Private SSH key (the full key content) |

## Environment Variables

See `backend/.env.example`.

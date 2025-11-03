# Google AP2 - Complete E-Commerce Payment System

A full-stack e-commerce platform implementing the **AP2 (Agent Payment Protocol)** with Stripe integration, AI-powered shopping search, and modern web technologies.

## 🎯 Project Overview

This repository contains **two integrated systems**:

### 1. **Merchant Agent** (`Merchant agent/`)
- **StreetStride**: Premium sneakers e-commerce catalog
- AP2 Payment Protocol implementation
- Stripe payment integration
- 360+ product catalog
- Full cart management
- Order processing with cryptographic mandates

### 2. **Shopping Agent** (`shopping agent/`)
- **AI-Powered Shopping Search**: Natural language product search
- MCP (Model Context Protocol) orchestration via Metorial
- Web scraping with Firecrawl
- Complete AP2 chain: IntentMandate → CartMandate → PaymentMandate → PaymentProof
- MetaMask wallet integration
- React + Vite frontend

## 🚀 Quick Start

### Prerequisites
- **Node.js** v18+ and npm
- **Git** (for GitHub upload)
- API keys (Stripe, Metorial, OpenAI, Perplexity, Firecrawl)
- MetaMask browser extension (for wallet features)

### 1. Merchant Agent Setup

```bash
cd "Merchant agent"
npm install
cp env.example .env
# Edit .env with your Stripe keys
npm start
```

Backend runs on `http://localhost:3000`

### 2. Shopping Agent Setup

**Backend:**
```bash
cd "shopping agent/backend"
npm install
cp env.example.txt .env
# Edit .env with your API keys (Metorial, OpenAI, Stripe, etc.)
npm start
```

**Frontend:**
```bash
cd "shopping agent/frontend"
npm install
npm run dev
```

Backend: `http://localhost:3001` | Frontend: `http://localhost:5173`

## 📁 Project Structure

```
Google_AP2/
├── Merchant agent/              # StreetStride E-commerce
│   ├── server.js               # Express backend
│   ├── index.html              # Main frontend
│   ├── app.js                  # Frontend logic
│   ├── src/ap2/                # AP2 protocol modules
│   ├── secrets/                # JWK keys (merchant)
│   └── package.json
│
└── shopping agent/             # AI Shopping Search
    ├── backend/
    │   ├── server.js           # Express + MCP
    │   ├── routes/             # API routes
    │   ├── services/           # Business logic
    │   └── package.json
    └── frontend/
        ├── src/                # React components
        └── package.json
```

## 🔐 Environment Variables

### Merchant Agent (`.env`)
```env
STRIPE_SECRET_KEY=sk_test_...
STRIPE_PUBLISHABLE_KEY=pk_test_...
STRIPE_WEBHOOK_SECRET=whsec_...
PORT=3000
FRONTEND_URL=http://localhost:8000
```

### Shopping Agent Backend (`.env`)
```env
METORIAL_API_KEY=...
PERPLEXITY_DEPLOYMENT_ID=...
FIRECRAWL_DEPLOYMENT_ID=...
STRIPE_MCP_DEPLOYMENT_ID=...
OPENAI_API_KEY=...
STRIPE_SECRET_KEY=sk_test_...
STRIPE_PUBLISHABLE_KEY=pk_test_...
PORT=3001
```

### Shopping Agent Frontend (`.env`)
```env
VITE_STRIPE_PUBLISHABLE_KEY=pk_test_...
VITE_BACKEND_URL=http://localhost:3001
```

## 📦 GitHub Upload Instructions (5 Minutes)

### Option 1: Using Git Command Line

```bash
# 1. Initialize Git repository (if not already done)
git init

# 2. Create .gitignore file (if doesn't exist)
# Add these entries:
echo "node_modules/" >> .gitignore
echo ".env" >> .gitignore
echo "*.log" >> .gitignore
echo ".DS_Store" >> .gitignore
echo "secrets/*.jwk.json" >> .gitignore
echo "watch.log" >> .gitignore

# 3. Stage all files
git add .

# 4. Commit
git commit -m "Initial commit: Google AP2 E-commerce System"

# 5. Add your GitHub repository as remote
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git

# 6. Push to GitHub
git branch -M main
git push -u origin main
```

### Option 2: Using GitHub Desktop

1. **Open GitHub Desktop**
2. **File → Add Local Repository**
3. Select `C:\Users\harsh\Desktop\Google_AP2`
4. **Publish repository** (choose your GitHub account)
5. Enter repository name and click **Publish Repository**

### Option 3: Using VS Code

1. **Open VS Code** in the project folder
2. Click **Source Control** (left sidebar)
3. Click **Publish to GitHub**
4. Choose visibility (Public/Private)
5. Click **Publish**

### ⚠️ Important: Before Uploading

1. **Create `.gitignore`** to exclude sensitive files:
```
node_modules/
.env
*.log
.DS_Store
secrets/*.jwk.json
watch.log
dist/
build/
.cache/
```

2. **Don't commit sensitive data:**
   - `.env` files (already ignored)
   - Private keys in `secrets/`
   - API keys

3. **Use `env.example` files** for documentation:
   - `Merchant agent/env.example`
   - `shopping agent/backend/env.example.txt`

## 🔄 AP2 Protocol Flow

The complete AP2 chain implemented:

```
1. IntentMandate (User signs with MetaMask)
   ↓
2. CartMandate (Merchant signs)
   ↓
3. PaymentMandate (User signs with MetaMask)
   ↓
4. PaymentProof (Processor signs)
```

All mandates are cryptographically signed and verified.

## 🛠️ Technology Stack

- **Backend**: Node.js, Express.js
- **Frontend**: React 19, Vite, Vanilla JS
- **Payment**: Stripe Elements, Stripe API
- **Blockchain**: Ethers.js, MetaMask
- **AI/ML**: OpenAI, Perplexity, Firecrawl (via Metorial MCP)
- **Protocol**: AP2 (Agent Payment Protocol)

## 📚 Documentation

Each component has detailed READMEs:
- `Merchant agent/README.md` - Merchant agent documentation
- `shopping agent/README.md` - Shopping agent documentation
- Additional docs in each folder (DEPLOYMENT.md, API_REFERENCE.md, etc.)

## 🧪 Testing

### Merchant Agent
```bash
cd "Merchant agent"
npm test
```

### Shopping Agent
```bash
cd "shopping agent/backend"
npm test  # (if tests are configured)
```

## 🚢 Deployment

### Merchant Agent
- **Vercel**: See `VERCEL_DEPLOYMENT_GUIDE.md`
- **Local**: See `START_SERVERS.md`

### Shopping Agent
- Backend: Deploy to any Node.js hosting (Vercel, Railway, Render)
- Frontend: Deploy to Vercel, Netlify, or GitHub Pages

## 🔗 API Endpoints

### Merchant Agent
- `POST /api/create-payment-intent` - Create Stripe payment
- `POST /api/webhook` - Stripe webhooks
- `GET /api/products` - Product search
- `POST /api/cart` - Cart management
- `POST /api/mandate` - AP2 mandate creation

### Shopping Agent
- `POST /api/search` - AI product search (SSE stream)
- `POST /api/mandate/issue` - Issue Intent Mandate
- `POST /api/cart/create` - Create Cart Mandate
- `POST /api/processor/pay` - Process payment
- `GET /api/processor/payment-proof/:id` - Get PaymentProof

## 🐛 Troubleshooting

1. **Port already in use**: Change `PORT` in `.env`
2. **CORS errors**: Ensure backend allows frontend origin
3. **MetaMask not detected**: Install browser extension
4. **API keys missing**: Check all `.env` files
5. **MCP connection fails**: Verify Metorial credentials

## 📝 License

ISC

## 🤝 Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Open Pull Request

## 📞 Support

- Check component-specific READMEs for detailed help
- Review API documentation in each folder
- Check console logs for errors

---

**Built with ❤️ using AP2 Protocol, Stripe, React, and AI/ML**

## ⚡ Quick Reference

| Component | Port | URL |
|-----------|------|-----|
| Merchant Agent | 3000 | http://localhost:3000 |
| Shopping Backend | 3001 | http://localhost:3001 |
| Shopping Frontend | 5173 | http://localhost:5173 |

---

**Status**: ✅ Production Ready  
**Last Updated**: November 2025


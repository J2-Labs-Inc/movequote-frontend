# MoveQuote Frontend Deployment Guide

## ✅ What's Been Done

1. **Frontend Created** - Full MoveQuote frontend built with:
   - Blue branding (#3b82f6)
   - Moving-specific quote calculator
   - Dashboard with stats and quote management
   - Mobile-responsive design

2. **GitHub Repository** - Code pushed to:
   - https://github.com/J2-Labs-Inc/movequote-frontend

3. **API Integration** - Connected to:
   - https://api-production-e5b3.up.railway.app

## 🚀 Deploy to Vercel (Recommended - Free & Easy)

### Option 1: Vercel Web Dashboard (Easiest)
1. Go to https://vercel.com/new
2. Sign in with GitHub
3. Import `J2-Labs-Inc/movequote-frontend`
4. Configure:
   - **Framework Preset:** Other
   - **Root Directory:** `./` (leave as is)
   - **Build Command:** (leave empty - no build needed)
   - **Output Directory:** `public`
5. Click **Deploy**
6. Your site will be live at: `movequote-frontend.vercel.app`

### Option 2: Vercel CLI
```bash
cd /tmp/movequote-frontend
vercel login
vercel --prod
```

## 🚂 Deploy to Railway (Alternative)

### Via Railway Dashboard
1. Go to https://railway.app/new
2. Click "Deploy from GitHub repo"
3. Select `J2-Labs-Inc/movequote-frontend`
4. Railway will auto-detect the configuration from `railway.json`
5. Your site will be live at: `movequote-frontend.up.railway.app`

### Via Railway CLI
```bash
cd /tmp/movequote-frontend
railway login
railway init
railway up
```

## 🐳 Deploy to Fly.io (Alternative)

```bash
cd /tmp/movequote-frontend
fly launch --name movequote-frontend
fly deploy
```

## 🌐 Custom Domain

After deployment, add your custom domain:

### Vercel
1. Go to Project Settings → Domains
2. Add your domain (e.g., `www.movequote.com`)
3. Update DNS records as instructed

### Railway
1. Go to project → Settings → Domains
2. Add custom domain
3. Add CNAME record pointing to Railway

## 🧪 Test the Deployment

After deploying, test the full flow:

1. **Landing Page** - Calculator should work
2. **Signup** - Create test account
3. **Login** - Sign in with test account
4. **Create Quote** - Fill form and submit
5. **View Quotes** - Check dashboard shows the quote

## 🔧 Configuration

If you need to change the API URL:

1. Edit `public/auth.html` line 586
2. Edit `public/app.html` line 687
3. Commit and push changes

```javascript
const API_URL = 'https://your-api-url.com';
```

## 📊 API Endpoints Used

- `POST /api/auth/signup` - User registration
- `POST /api/auth/login` - User authentication
- `GET /api/quotes` - Fetch user's quotes
- `POST /api/quotes` - Create new quote
- `POST /api/subscription/checkout` - Upgrade to Pro (placeholder)

## 🎨 Branding Customization

To customize branding in the future:

1. **Colors** - Search for `--primary: #3b82f6` in all files and replace
2. **Logo** - Replace inline SVG in header sections
3. **Text** - Update copy in HTML files

## 🐛 Troubleshooting

### "API request failed"
- Check that backend API is running at https://api-production-e5b3.up.railway.app
- Open browser console to see detailed error
- Verify CORS is enabled on backend

### "Can't create quote"
- Ensure you're logged in (check localStorage for `mq_token`)
- Check browser console for errors
- Verify all required fields are filled

### "Dashboard not loading"
- Clear localStorage: `localStorage.clear()`
- Try logging in again
- Check browser console for API errors

## 📝 Next Steps After Deployment

1. **Test Full Flow** - Signup → Create Quote → View Dashboard
2. **Add Custom Domain** - Configure DNS for your domain
3. **Monitor Usage** - Track signups and quote creation
4. **Set Up Analytics** (optional) - Add Google Analytics or similar
5. **Configure Email** (future) - For sending quotes to clients

## 🔐 Security Notes

- JWT tokens stored in localStorage (keys: `mq_token`, `mq_user`)
- API handles all authentication and authorization
- Frontend is stateless - all data fetched from API

## 📞 Support

For issues or questions:
- GitHub Issues: https://github.com/J2-Labs-Inc/movequote-frontend/issues
- Backend Repo: https://github.com/J2-Labs-Inc/movequote (if API issues)

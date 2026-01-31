# MoveQuote Frontend

Professional moving quote software for moving companies.

## Features

- Quick quote generation (origin/destination, truck size, movers, hours)
- Client management
- Dashboard with analytics
- Responsive design
- Mobile-friendly

## Tech Stack

- Vanilla HTML/CSS/JavaScript (no build process)
- Connected to MoveQuote API at https://api-production-e5b3.up.railway.app

## Local Development

```bash
npm start
# Or use any static server:
npx serve public -p 3000
```

Open http://localhost:3000

## Deployment

### Railway
1. Create new Railway project
2. Connect this GitHub repo
3. Set root directory to `/public`
4. Deploy automatically

### Vercel
1. Connect repo to Vercel
2. Set output directory to `public`
3. Deploy

## API Endpoints

- POST /api/auth/signup
- POST /api/auth/login
- GET /api/quotes
- POST /api/quotes
- POST /api/subscription/checkout

## Configuration

API URL is hardcoded in:
- `public/auth.html` (line ~586)
- `public/app.html` (line ~687)

Change to your API URL if needed.

## License

Proprietary - J2 Labs Inc

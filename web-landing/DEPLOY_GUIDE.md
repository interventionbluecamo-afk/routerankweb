# Deploying the Landing Page

## Quick Setup - New Git Repo

The landing page is currently in `web-landing/` folder. Here's how to deploy it:

### Option 1: Deploy as Separate Project (Recommended)

1. **Create a new GitHub repo:**
   - Go to github.com → New repository
   - Name it: `routerank-landing` (or whatever you want)
   - **Don't** initialize with README (we'll push existing code)

2. **Push the landing page:**
   ```bash
   cd web-landing
   git init
   git add .
   git commit -m "Initial commit: RouteRank landing page"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/routerank-landing.git
   git push -u origin main
   ```

3. **Deploy to Vercel:**
   - Go to vercel.com
   - Import the new `routerank-landing` repo
   - Vercel will auto-detect Next.js
   - Click Deploy
   - Done! You'll get a URL like `routerank-landing.vercel.app`

### Option 2: Keep in Same Repo (Subfolder)

If you want to keep everything in one repo:

1. **The landing page is already in `web-landing/`**
   
2. **Deploy separately to Vercel:**
   - In Vercel dashboard → Add Project
   - Import your main `routerank` repo
   - **Root Directory**: Set to `web-landing`
   - Deploy

### Option 3: Static HTML (Simplest)

If you want a super simple landing page without Next.js:

1. **Create simple HTML files:**
   ```bash
   cd web-landing
   # Create index.html, styles.css, etc.
   ```

2. **Deploy to:**
   - **Netlify Drop**: Drag and drop folder
   - **Vercel**: Just point to HTML file
   - **GitHub Pages**: Push and enable Pages in repo settings

## What You Need to Do

Since `web-landing/` currently has some files from the old app, you have two choices:

### A) Clean It Up First:
```bash
cd web-landing
# Remove the copied Next.js files
# Create a fresh, simple landing page
```

### B) Set Up as Full Next.js Project:
```bash
cd web-landing
# Initialize as new Next.js project
npx create-next-app@latest . --yes
# Copy your landing components into it
```

## Recommended Structure

```
web-landing/
├── public/          # Images, assets
├── pages/           # Next.js pages (or just index.html)
├── components/      # Landing page components
└── styles/         # CSS files
```

## Quick Deploy Commands

**If using Next.js:**
```bash
cd web-landing
npm run build
# Deploy to Vercel (automatic if connected to GitHub)
```

**If using static HTML:**
- Just upload the folder to Netlify Drop or Vercel

## Domain Setup

After deploying:
1. Add custom domain in Vercel/Netlify settings
2. Update DNS records
3. Wait for SSL certificate (automatic)


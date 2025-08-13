# Deployment Guide for Render.com

This guide will help you deploy your collaborative calendar to Render.com for free.

## Prerequisites

1. A GitHub account
2. A Render.com account (free)

## Step-by-Step Deployment

### 1. Push Code to GitHub

First, you need to get your code into a GitHub repository:

1. Go to [GitHub.com](https://github.com) and create a new repository
2. Name it something like "collaborative-calendar"
3. Make it public (required for free Render deployments)
4. Don't initialize with README since you already have one

### 2. Upload Your Code

Option A: Use GitHub's web interface
1. Download all your files from Replit
2. Upload them to your new GitHub repository

Option B: Use Git commands (if you have Git installed)
```bash
git init
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/collaborative-calendar.git
git branch -M main
git push -u origin main
```

### 3. Deploy on Render

1. Go to [Render.com](https://render.com) and sign up/sign in
2. Connect your GitHub account
3. Click "New +" → "Web Service"
4. Select your collaborative-calendar repository
5. Render will automatically detect the `render.yaml` configuration

### 4. Configure the Service

Render should automatically fill in these settings from the `render.yaml` file:
- **Build Command**: `npm install && npm run build`
- **Start Command**: `npm start`
- **Environment**: Node
- **Plan**: Free

Click "Create Web Service"

### 5. Wait for Deployment

- First deployment takes 5-10 minutes
- You'll see build logs in real-time
- Once complete, you'll get a URL like `https://your-app-name.onrender.com`

## Important Notes

### Free Plan Limitations
- Service goes to sleep after 15 minutes of inactivity
- Takes 30-60 seconds to wake up when accessed
- 750 hours/month of runtime (enough for personal use)

### WebSocket Support
The app includes WebSocket support for real-time collaboration, which works perfectly on Render's free tier.

### Custom Domain (Optional)
You can add a custom domain in the Render dashboard under "Settings" → "Custom Domains"

## Troubleshooting

### Build Fails
- Check that all files are uploaded to GitHub
- Ensure `package.json` and `render.yaml` are in the root directory

### App Won't Start
- Check the logs in Render dashboard
- Verify the build completed successfully

### WebSocket Issues
- Ensure you're using HTTPS (Render provides this automatically)
- Check browser console for connection errors

## Files Included for Deployment

- `render.yaml` - Render configuration
- `Dockerfile` - Container configuration (backup option)
- `README.md` - Project documentation
- `.gitignore` - Files to exclude from version control

Your collaborative calendar will be live and accessible to anyone with the URL!

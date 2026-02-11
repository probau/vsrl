# GitHub Pages Deployment Guide

## Step 1: Add Your Logo
1. Copy your `vsrl-logo.png` file into the `/Users/gerritmcgowan/Desktop/vsrl-website/` folder

## Step 2: Create GitHub Repository

### Option A: Using GitHub Website (Easiest)
1. Go to https://github.com/new
2. Repository name: `vsrl-website` (or `visceralreality.de` if you want a custom domain)
3. Make it **Public**
4. **DO NOT** check "Add a README file" (we already have one)
5. Click "Create repository"

### Option B: Using Command Line (if you have GitHub CLI)
```bash
cd /Users/gerritmcgowan/Desktop/vsrl-website
gh repo create vsrl-website --public --source=. --remote=origin
```

## Step 3: Initialize Git and Push

Open Terminal and run these commands:

```bash
# Navigate to the website folder
cd /Users/gerritmcgowan/Desktop/vsrl-website

# Initialize git repository
git init

# Add all files
git add .

# Create first commit
git commit -m "Initial commit: VSRL landing page"

# Add your GitHub repository as remote (replace YOUR-USERNAME)
git remote add origin https://github.com/YOUR-USERNAME/vsrl-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

## Step 4: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** → **Pages** (in the left sidebar)
3. Under "Source", select:
   - Branch: `main`
   - Folder: `/ (root)`
4. Click **Save**

Wait 1-2 minutes, then your site will be live at:
`https://YOUR-USERNAME.github.io/vsrl-website/`

## Step 5: Custom Domain (Optional)

If you want to use `visceralreality.de`:

1. In GitHub Pages settings, add your custom domain: `visceralreality.de`
2. In your domain registrar (GoDaddy), add these DNS records:
   - **A Record**: `185.199.108.153`
   - **A Record**: `185.199.109.153`
   - **A Record**: `185.199.110.153`
   - **A Record**: `185.199.111.153`
   - **CNAME Record**: `www` → `YOUR-USERNAME.github.io`

3. Create a file named `CNAME` in your repository with just:
   ```
   visceralreality.de
   ```

## Troubleshooting

- **Logo not showing?** Make sure `vsrl-logo.png` is in the same folder as `index.html`
- **404 error?** Check that GitHub Pages is enabled and the branch is set to `main`
- **Changes not showing?** Wait a few minutes and hard refresh (Cmd+Shift+R)

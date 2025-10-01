# GitHub Pages Deployment Guide

This guide will help you deploy your React portfolio website to GitHub Pages.

---

## 🚀 Quick Deployment Steps

### 1. Repository Setup

1. **Create a new repository** on GitHub:

    - Repository name: `Services-Showcase-Website` (or your preferred name)
    - Make it public (required for free GitHub Pages)
    - Don't initialize with README, .gitignore, or license

2. **Push your code** to the repository:
    ```bash
    git init
    git add .
    git commit -m "Initial commit"
    git branch -M main
    git remote add origin https://github.com/ahmed-maher77/Services-Showcase-Website.git
    git push -u origin main
    ```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. Scroll down to **Pages** section
4. Under **Source**, select **GitHub Actions**
5. The workflow will automatically deploy when you push to main branch

### 3. Manual Deployment (Alternative)

If you prefer manual deployment:

```bash
# Install dependencies
npm install

# Build the project
npm run build

# Deploy to GitHub Pages
npm run deploy
```

---

## 🔧 Configuration Details

### Vite Configuration

The `vite.config.js` is configured with:

-   **Base path**: `/Services-Showcase-Website/` (matches your repository name)
-   **Build optimization**: Code splitting, minification, and asset optimization
-   **Output directory**: `dist` (standard for Vite)

### Package.json Scripts

-   `npm run dev` - Start development server
-   `npm run build` - Build for production
-   `npm run deploy` - Deploy to GitHub Pages
-   `npm run predeploy` - Pre-deployment build

### GitHub Actions Workflow

The `.github/workflows/deploy.yml` file handles:

-   Automatic deployment on push to main branch
-   Node.js 18 setup
-   Dependency installation
-   Production build
-   GitHub Pages deployment

---

## 🌐 Access Your Website

Once deployed, your website will be available at:
**https://ahmed-maher77.github.io/Services-Showcase-Website/**

---

## 🔄 Updating Your Website

To update your website:

1. **Make changes** to your code
2. **Commit and push** to main branch:
    ```bash
    git add .
    git commit -m "Update website"
    git push origin main
    ```
3. **GitHub Actions** will automatically rebuild and deploy
4. **Wait 2-3 minutes** for deployment to complete

---

## 🛠️ Troubleshooting

### Common Issues:

1. **Build fails with terser error**:

    ```bash
    npm install --save-dev terser
    ```

2. **404 errors on GitHub Pages**:

    - Check that `base` path in `vite.config.js` matches your repository name
    - Ensure all internal links use relative paths

3. **Assets not loading**:

    - Verify the base path configuration
    - Check that all images and assets are in the `public` folder

4. **Deployment not triggering**:
    - Check GitHub Actions tab for workflow status
    - Ensure you're pushing to the correct branch (main/master)

### Debug Steps:

1. **Check build locally**:

    ```bash
    npm run build
    npm run preview
    ```

2. **Verify GitHub Actions**:

    - Go to Actions tab in your repository
    - Check for failed workflows
    - Review build logs for errors

3. **Test deployment**:
    - Visit your GitHub Pages URL
    - Check browser console for errors
    - Test all navigation and functionality

---

## 📝 Important Notes

-   **Repository must be public** for free GitHub Pages hosting
-   **Branch name** should be `main` or `master` (update workflow if different)
-   **Base path** in `vite.config.js` must match your repository name exactly
-   **Homepage URL** in `package.json` should match your GitHub Pages URL
-   **Deployment takes 2-3 minutes** after pushing to main branch

---

## 🎯 Next Steps

1. **Customize your domain** (optional):

    - Add a `CNAME` file in the `public` folder
    - Configure custom domain in GitHub Pages settings

2. **Add analytics** (optional):

    - Google Analytics
    - GitHub Pages analytics

3. **Optimize performance**:
    - Image optimization
    - Code splitting
    - Caching strategies

---

_Happy deploying! 🚀_

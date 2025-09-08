# Deployment Guide: PCS Pet Shipper Website to Netlify

This guide will help you deploy your PCS Pet Shipper website to Netlify using GitHub.

## 📋 Prerequisites
- GitHub account
- Netlify account (free)
- Domain: www.pcspetshipper.com

## 🚀 Step-by-Step Deployment

### 1. Push to GitHub Repository

1. **Create a new GitHub repository:**
   - Go to [GitHub.com](https://github.com)
   - Click "New" or "New Repository"
   - Repository name: `pcs-pet-shipper-website`
   - Description: `Professional pet transportation website for PCS Pet Shipper`
   - Set to **Public** (for free Netlify hosting)
   - Don't initialize with README (we already have one)

2. **Upload your files:**
   - Option A: **GitHub Web Interface**
     - Click "Upload files"
     - Drag and drop all files from `/home/charveyiii3/pcs-pet-shipper-website/`
     - Commit with message: "Initial website deployment"
   
   - Option B: **Git Command Line** (if you have Git installed)
     ```bash
     cd /home/charveyiii3/pcs-pet-shipper-website
     git init
     git add .
     git commit -m "Initial website deployment"
     git branch -M main
     git remote add origin https://github.com/YOUR_USERNAME/pcs-pet-shipper-website.git
     git push -u origin main
     ```

### 2. Connect GitHub to Netlify

1. **Sign up for Netlify:**
   - Go to [netlify.com](https://netlify.com)
   - Click "Sign up" → "Sign up with GitHub"
   - Authorize Netlify to access your GitHub

2. **Deploy from Git:**
   - Click "New site from Git"
   - Choose "GitHub" as your Git provider
   - Select your `pcs-pet-shipper-website` repository
   - Leave build settings as default:
     - **Build command:** (leave empty)
     - **Publish directory:** (leave empty, uses root)
   - Click "Deploy site"

3. **Your site is now live!**
   - Netlify will provide a random URL like `https://amazing-curie-123456.netlify.app`
   - The site will auto-deploy whenever you push changes to GitHub

### 3. Configure Custom Domain

1. **In Netlify Dashboard:**
   - Go to your site settings
   - Click "Domain management" → "Add custom domain"
   - Enter: `pcspetshipper.com` (without www)
   - Click "Verify"

2. **Update DNS Settings:**
   - Go to your domain registrar (where you bought pcspetshipper.com)
   - Update DNS settings:
     ```
     Type: A Record
     Name: @ (or pcspetshipper.com)
     Value: 75.2.60.5 (Netlify's IP)
     
     Type: CNAME
     Name: www
     Value: your-site-name.netlify.app
     ```

3. **Enable HTTPS:**
   - In Netlify: Go to "Domain management" → "HTTPS"
   - Click "Verify DNS configuration"
   - Enable "Force HTTPS redirect"

### 4. Final Verification

✅ **Test these URLs:**
- https://pcspetshipper.com
- https://www.pcspetshipper.com

✅ **Verify functionality:**
- All pages load correctly
- Images display properly
- Forms work (booking form)
- Navigation functions
- Mobile responsiveness

## 🔧 Post-Deployment Options

### Analytics (Optional)
Add Google Analytics:
1. Get your GA tracking code
2. Add to all HTML files before `</head>`
3. Push changes to GitHub (auto-deploys)

### Form Handling (Optional)
Enable Netlify Forms:
1. Add `netlify` attribute to forms in HTML
2. Forms will be handled by Netlify automatically

### Performance Optimization
- Netlify automatically provides CDN
- Gzip compression enabled
- Automatic HTTPS

## 📞 Support
If you encounter issues:
- Netlify Support: [support.netlify.com](https://support.netlify.com)
- GitHub Support: [support.github.com](https://support.github.com)

## 🎉 You're Live!
Your PCS Pet Shipper website is now professionally hosted and accessible at www.pcspetshipper.com

---
*Professional pet transportation services you can trust.*
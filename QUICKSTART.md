# 🚀 QUICK START GUIDE

Get your Avionne Photography website up and running in 15 minutes!

## Step 1: Install Dependencies (2 minutes)

```bash
cd avionnephotography
npm install
```

## Step 2: Start Local Development (30 seconds)

```bash
npm run dev
```

Visit: http://localhost:4321

You should see your site running! 🎉

## Step 3: Add Your Images (5 minutes)

### Logo:
1. Save your logo as `/public/logo.svg` or `/public/logo.png`
2. Open `src/components/Header.astro`
3. Replace line 8-11 with:
   ```astro
   <img src="/logo.svg" alt="Avionne Photography" class="h-8" />
   ```

### Portfolio Images:
1. Optimize 3-4 of your best photos (see `/public/images/portfolio/README.md`)
2. Save them as: `hero-1.jpg`, `hero-2.jpg`, `hero-3.jpg`, `hero-4.jpg`
3. Place in: `/public/images/portfolio/`
4. Open `src/components/Hero.astro`
5. Replace lines 8-22 with actual image tags (example in README)

## Step 4: Test Everything (3 minutes)

- [ ] Homepage loads and looks good
- [ ] All navigation links work
- [ ] "Book Now" button goes to book.avionnephotography.com
- [ ] Prep checklist page loads
- [ ] PDF download button works
- [ ] Test on your phone (use your local IP address)

## Step 5: Deploy to GitHub (5 minutes)

```bash
# Initialize git (if not done yet)
git init
git add .
git commit -m "Initial commit"

# Create repository on GitHub
# Then push:
git remote add origin https://github.com/YOUR_USERNAME/avionnephotography.git
git branch -M main
git push -u origin main
```

## Step 6: Enable GitHub Pages

1. Go to your repo → Settings → Pages
2. Source: "GitHub Actions"
3. Wait 2-3 minutes for deployment
4. Your site will be live at: `https://YOUR_USERNAME.github.io/avionnephotography`

## Step 7: Add Custom Domain (Optional)

1. In GitHub Pages settings, add custom domain: `avionnephotography.com`
2. Update your DNS (see main README for details)
3. Wait 24-48 hours for DNS propagation

---

## 🆘 Need Help?

**Site not loading?**
- Make sure you ran `npm install`
- Check that Node.js 18+ is installed: `node --version`

**Images not showing?**
- Check file paths (must start with `/`)
- Ensure images are in `/public/` folder
- Clear browser cache

**Can't push to GitHub?**
- Make sure you created the repository first
- Check you're using the correct repository URL

**Deployment failing?**
- Check the Actions tab in GitHub for error details
- Ensure `deploy.yml` is in `.github/workflows/`

---

## ✨ You're Done!

Your professional photography website is now live. Time to start booking clients! 📸

Next steps:
- Share your new site with potential clients
- Add more portfolio images as you get them
- Consider adding a blog or gallery page later

# Avionne Photography Website

Luxury real estate photography website built with Astro.js and Tailwind CSS.

## 🎨 Color Palette: Sophisticated Slate

- **Primary (Charcoal):** `#2C3539`
- **Accent (Warm Gold):** `#C9A961`
- **Background (Soft Cream):** `#F8F6F3`
- **Text (Rich Black):** `#1A1A1A`

## 🚀 Getting Started

### Prerequisites

- Node.js 18+ installed
- Git installed
- GitHub account

### Local Development

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Start development server:**
   ```bash
   npm run dev
   ```
   
   Your site will be available at `http://localhost:4321`

3. **Build for production:**
   ```bash
   npm run build
   ```

4. **Preview production build:**
   ```bash
   npm run preview
   ```

## 📁 Project Structure

```
/
├── public/
│   ├── images/
│   │   └── portfolio/     # Add your portfolio images here
│   └── favicon.svg        # Add your favicon
├── src/
│   ├── components/
│   │   ├── Header.astro
│   │   ├── Footer.astro
│   │   ├── Hero.astro
│   │   ├── Services.astro
│   │   ├── Coverage.astro
│   │   └── About.astro
│   ├── layouts/
│   │   └── Layout.astro
│   └── pages/
│       ├── index.astro
│       └── prep-checklist.astro
└── package.json
```

## 🖼️ Adding Your Images

### 1. Logo
- Place your logo in `/public/` as `logo.svg` or `logo.png`
- Update the Header.astro component (line 8) to use your logo:
  ```astro
  <img src="/logo.svg" alt="Avionne Photography" class="h-8" />
  ```

### 2. Portfolio Images for Hero Carousel
Replace the gradient placeholders in `src/components/Hero.astro` with your actual images:

1. Add 3-4 high-quality portfolio images to `/public/images/portfolio/`
2. Name them: `hero-1.jpg`, `hero-2.jpg`, `hero-3.jpg`, etc.
3. Update Hero.astro (around lines 8-22):
   ```astro
   <div class="carousel-slide active">
     <img 
       src="/images/portfolio/hero-1.jpg" 
       alt="Luxury real estate photography" 
       class="w-full h-full object-cover"
     />
     <div class="absolute inset-0 bg-black bg-opacity-40"></div>
   </div>
   ```

**Image Optimization Tips:**
- Format: WebP or JPEG
- Size: 1920px wide (max)
- Quality: 80-85%
- File size: Under 500KB each

## 🌐 Deploying to GitHub Pages

### Step 1: Create GitHub Repository

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/avionnephotography.git
git push -u origin main
```

### Step 2: Create GitHub Actions Workflow

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [ main ]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      
      - name: Setup Node
        uses: actions/setup-node@v4
        with:
          node-version: 20
      
      - name: Install dependencies
        run: npm ci
      
      - name: Build
        run: npm run build
      
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: ./dist

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Step 3: Configure GitHub Pages

1. Go to your repository on GitHub
2. Settings → Pages
3. Source: "GitHub Actions"
4. Save

### Step 4: Configure Custom Domain

1. In GitHub Settings → Pages → Custom domain
2. Enter: `avionnephotography.com`
3. Click "Save"

### Step 5: Update DNS Records

In your domain registrar (where you bought avionnephotography.com):

**If using root domain (avionnephotography.com):**
```
A     @     185.199.108.153
A     @     185.199.109.153
A     @     185.199.110.153
A     @     185.199.111.153
```

**Add CNAME for www:**
```
CNAME www   YOUR_GITHUB_USERNAME.github.io
```

**IMPORTANT:** Don't touch your existing CNAME records for Spiro:
- `book.avionnephotography.com`
- `download.avionnephotography.com`
- `property.avionnephotography.com`
- `editor.avionnephotography.com`
- `track.avionnephotography.com`
- `company.avionnephotography.com`
- `photog.avionnephotography.com`
- `admin.avionnephotography.com`
- `staffedit.avionnephotography.com`

### Step 6: Enable HTTPS

GitHub Pages will automatically provision an SSL certificate. This may take a few minutes after DNS propagation.

## ✅ Checklist Before Going Live

- [ ] Replace logo placeholder with your actual logo
- [ ] Add 3-4 portfolio images for hero carousel
- [ ] Update hero carousel in `Hero.astro` to use real images
- [ ] Test all links work (especially book.avionnephotography.com)
- [ ] Test on mobile devices
- [ ] Verify prep checklist PDF downloads correctly
- [ ] Check that all text reads professionally
- [ ] Ensure DNS records are correct
- [ ] Test site on multiple browsers

## 🎯 Content To Customize

You may want to adjust:

1. **Hero tagline** (`src/components/Hero.astro`, line 24)
2. **About section copy** (`src/components/About.astro`)
3. **Service descriptions** (`src/components/Services.astro`)
4. **Coverage area details** (`src/components/Coverage.astro`)
5. **Footer links** (`src/components/Footer.astro`)

## 📱 Testing

- **Lighthouse:** Aim for 90+ scores
- **Mobile:** Test on iPhone and Android
- **Browsers:** Chrome, Safari, Firefox, Edge
- **Links:** Verify all external links work

## 🆘 Troubleshooting

**Issue:** Images not loading
- Check file paths are correct
- Ensure images are in `/public/` folder
- Use leading slash: `/images/photo.jpg`

**Issue:** GitHub Pages not deploying
- Check Actions tab for error messages
- Verify workflow file is in `.github/workflows/`
- Ensure Pages is enabled in Settings

**Issue:** Custom domain not working
- Wait 24-48 hours for DNS propagation
- Verify DNS records with `dig avionnephotography.com`
- Check GitHub Pages custom domain settings

## 📝 License

© 2024 Avionne Photography. All rights reserved.

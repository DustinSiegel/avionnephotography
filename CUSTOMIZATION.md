# 🎨 Customization Guide

Quick reference for making common changes to your site.

## 📝 Text Changes

### Hero Section Tagline
**File:** `src/components/Hero.astro`
**Line:** 24-30

```astro
<p class="text-xl md:text-2xl text-background mb-4 opacity-90">
  Exceptional Quality. Professional Results. Unbeatable Value.
</p>
<p class="text-lg text-background mb-10 opacity-80">
  Serving Northern New Jersey
</p>
```

### Services List
**File:** `src/components/Services.astro`
**Line:** 3-77

Add, remove, or edit services in the `services` array.

### Coverage Area
**File:** `src/components/Coverage.astro`
**Lines:** 40-55

Update county names and towns as you expand.

### About Section
**File:** `src/components/About.astro`
**Lines:** 8-17

Change the main pitch and value propositions.

## 🎨 Design Changes

### Colors
**File:** `tailwind.config.mjs`

```js
colors: {
  primary: '#2C3539',    // Main dark color
  accent: '#C9A961',     // Gold accent
  background: '#F8F6F3', // Page background
  'text-dark': '#1A1A1A', // Text color
}
```

### Fonts
**File:** `tailwind.config.mjs`

```js
fontFamily: {
  sans: ['Your Font', '-apple-system', 'sans-serif'],
}
```

Add Google Fonts in `src/layouts/Layout.astro` in the `<head>`.

### Logo
**File:** `src/components/Header.astro`
**Lines:** 8-11

```astro
<!-- Replace the text with your logo image -->
<img src="/logo.svg" alt="Avionne Photography" class="h-8" />
```

## 📸 Image Changes

### Hero Carousel Images
**File:** `src/components/Hero.astro`
**Lines:** 8-22

Replace gradient placeholders with:

```astro
<div class="carousel-slide active absolute inset-0">
  <img 
    src="/images/portfolio/hero-1.jpg" 
    alt="Real estate photography example" 
    class="w-full h-full object-cover"
  />
  <div class="absolute inset-0 bg-black bg-opacity-40"></div>
</div>
```

Repeat for each image (hero-2.jpg, hero-3.jpg, etc.)

### Carousel Speed
**File:** `src/components/Hero.astro`
**Line:** 53

```javascript
setInterval(nextSlide, 5000); // Change 5000 to milliseconds you want
```

## 🔗 Links

### Book Now Button
Search for: `https://book.avionnephotography.com`

Replace with your actual booking link if it changes.

### Download Link
**File:** `src/components/Footer.astro`
**Line:** 30

```astro
<a href="https://download.avionnephotography.com">Download Photos</a>
```

## 📱 Social Media (Optional Addition)

Add social media icons to the footer:

**File:** `src/components/Footer.astro`

Add before the copyright section:

```astro
<div class="flex justify-center gap-6 mb-6">
  <a href="https://instagram.com/yourhandle" class="text-background hover:text-accent">
    <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24">
      <!-- Instagram icon SVG -->
    </svg>
  </a>
  <!-- Add more social icons -->
</div>
```

## 📋 Prep Checklist

### Add/Edit Checklist Items
**File:** `src/pages/prep-checklist.astro`
**Lines:** 7-55

Edit the `checklistItems` array to add, remove, or modify preparation steps.

## 🔧 Advanced Customizations

### Add a New Page

1. Create new file: `src/pages/yourpage.astro`
2. Use the Layout component:
   ```astro
   ---
   import Layout from '../layouts/Layout.astro';
   import Header from '../components/Header.astro';
   import Footer from '../components/Footer.astro';
   ---
   
   <Layout title="Your Page Title">
     <Header />
     <main class="py-20 px-6">
       <!-- Your content -->
     </main>
     <Footer />
   </Layout>
   ```
3. Add link in Header and Footer navigation

### Add Contact Form

Consider using:
- **FormSubmit.co** (free, email-based)
- **Formspree** (free tier available)
- **Netlify Forms** (if deploying to Netlify)

### Add Analytics

**Google Analytics:**

Add to `src/layouts/Layout.astro` in `<head>`:

```astro
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-XXXXXXXXXX');
</script>
```

## 🚀 Performance Tips

### Image Optimization
- Use WebP format
- Compress to 80-85% quality
- Max width: 1920px
- Target file size: <500KB

### Lazy Loading Images
Add to image tags:

```astro
<img src="/image.jpg" loading="lazy" alt="Description" />
```

### Minimize Build Size
- Remove unused Tailwind classes (automatic)
- Compress images before uploading
- Use SVG for logos when possible

## 🔍 SEO Optimization

### Page Titles & Descriptions
**File:** Each page's Layout component call

```astro
<Layout 
  title="Your Page Title | Avionne Photography"
  description="Specific description for this page"
>
```

### Add Open Graph Images
**File:** `src/layouts/Layout.astro`

Add to `<head>`:

```astro
<meta property="og:image" content="/images/og-image.jpg" />
<meta property="og:title" content={title} />
<meta property="og:description" content={description} />
```

## 📞 Support

If you need help with any customizations, the Astro documentation is excellent:
https://docs.astro.build

For Tailwind CSS reference:
https://tailwindcss.com/docs

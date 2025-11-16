# Portfolio Images

Place your 3-4 best portfolio images here for the homepage hero carousel.

## Image Requirements:

- **Format:** WebP or JPEG (WebP preferred for smaller file sizes)
- **Dimensions:** 1920px wide (max), maintain aspect ratio
- **Quality:** 80-85%
- **File Size:** Under 500KB per image
- **Naming:** 
  - hero-1.jpg
  - hero-2.jpg
  - hero-3.jpg
  - hero-4.jpg (optional)

## How to Optimize:

### Using Online Tools:
1. Go to https://squoosh.app/
2. Upload your image
3. Choose WebP format
4. Adjust quality to 80-85
5. Resize to 1920px wide
6. Download and save here

### Using Photoshop:
1. File → Export → Save for Web
2. JPEG, Quality: 80
3. Resize: 1920px wide
4. Save to this folder

## Next Steps:

After adding your images here, update `src/components/Hero.astro` to use them instead of the gradient placeholders.

Replace lines 8-22 with:

```astro
<div class="carousel-slide active absolute inset-0 transition-opacity duration-1000">
  <img 
    src="/images/portfolio/hero-1.jpg" 
    alt="Luxury real estate photography" 
    class="w-full h-full object-cover"
  />
  <div class="absolute inset-0 bg-black bg-opacity-40"></div>
</div>
<!-- Repeat for hero-2.jpg, hero-3.jpg, etc. -->
```

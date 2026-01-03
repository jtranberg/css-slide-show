# CSS-Only Slideshow (HTML + CSS)

A simple slideshow built with **only HTML + CSS** (no JavaScript).  
It displays **10 images**, one at a time, inside a 300×300 frame.

## Project Structure

Make sure your folders/files look like this:

project-root/
├─ index.html
├─ styles.css
└─ images/
└─ slides/
├─ 1.jpg
├─ 2.jpg
├─ 3.jpg
├─ 4.jpg
├─ 5.jpg
├─ 6.jpg
├─ 7.jpg
├─ 8.jpg
├─ 9.jpg
└─ 10.jpg

markdown
Copy code

✅ **Important:** Folder names are case-sensitive on many systems  
`images` is not the same as `Images`.

## How to Run

1. Open `index.html` in your browser:
   - double-click it, or
   - right-click → **Open With** → Chrome / Edge / Firefox

That’s it — the slideshow should start automatically.

## Image Requirements

- Put exactly **10 images** in `images/slides/`
- Recommended size: **300×300** (or larger)
- If images are larger, the CSS uses `object-fit: cover` to crop nicely.

If your files are not named `1.jpg` → `10.jpg`, update the `<img src="...">` paths in `index.html`.

## Slideshow Timing (How It Works)

This slideshow uses one shared animation timeline:

- **2 seconds per slide**
- **10 slides**
- **20 seconds total cycle**

Each image runs the same animation, but starts at a different `animation-delay`.

### Example math
- Slide 1 delay: `0s`
- Slide 2 delay: `2s`
- Slide 3 delay: `4s`
- ...
- Slide 10 delay: `18s`

## Accessibility: Reduced Motion

This project supports users who prefer reduced motion:

```css
@media (prefers-reduced-motion: reduce) { ... }
If the slideshow looks “stuck” on the first image:
Your system/browser may have Reduce Motion enabled, which disables animations by design.

To test quickly, you can temporarily comment out the prefers-reduced-motion block in styles.css.

Styling
The slideshow frame includes:

border-radius: 8px

border: 1px solid black

overflow: hidden (so images clip to rounded corners)
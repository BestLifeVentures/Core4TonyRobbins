# Your Core Four - Deployment Guide

## Overview
This is a static single-page application for the "Your Core Four" inner guidance system. It features:
- 6-page flow with voice recording capabilities
- Web Speech API integration for voice-to-text
- Responsive design optimized for desktop and mobile
- Distinctive typography and animations
- Results generation and download functionality

## Deployment to Cloudflare Pages via GitHub

### Prerequisites
- GitHub account
- Cloudflare account
- GitHub repository already synced to Cloudflare Pages

### Step 1: Upload to GitHub Repository

1. **Add the file to your GitHub repository:**
   ```bash
   git add index.html
   git commit -m "Add Your Core Four application"
   git push origin main
   ```

   Or if you prefer, you can:
   - Go to your GitHub repository
   - Click "Add file" > "Upload files"
   - Drag and drop the `index.html` file
   - Commit changes

### Step 2: Cloudflare Pages Configuration

Since this is a **static site** with just HTML, CSS, and JavaScript:

1. **In your Cloudflare Pages dashboard:**
   - Your project should already be connected to your GitHub repository
   - Cloudflare will automatically detect changes when you push to GitHub

2. **Build Settings:**
   - **Framework preset:** None
   - **Build command:** (leave empty)
   - **Build output directory:** `/` (root directory)
   - **Root directory:** `/` (or wherever index.html is located)

3. **Environment Variables:**
   - None required for this static site

### Step 3: Deploy

After pushing to GitHub:
1. Cloudflare Pages will automatically trigger a new deployment
2. Wait 1-2 minutes for the build to complete
3. Your site will be live at: `your-project-name.pages.dev`

### Important Notes

#### NO API or Wrangler Required
- This is a **pure static site** - no server-side code
- No Cloudflare Workers needed
- No API endpoints
- No Wrangler configuration required

#### Audio Files Setup
The application has placeholders for audio files on pages 2-5. To add your meditation audio:

1. Upload your audio files (MP3 or OAV format recommended) to your repository
2. Update the audio source paths in index.html:
   ```html
   <!-- Page 2 (Warrior) -->
   <audio id="audio2" src="path/to/warrior-meditation.mp3"></audio>
   
   <!-- Page 3 (Magician) -->
   <audio id="audio3" src="path/to/magician-meditation.mp3"></audio>
   
   <!-- Page 4 (Lover) -->
   <audio id="audio4" src="path/to/lover-meditation.mp3"></audio>
   
   <!-- Page 5 (Sage) -->
   <audio id="audio5" src="path/to/sage-meditation.mp3"></audio>
   ```

3. Recommended folder structure:
   ```
   /
   ├── index.html
   └── audio/
       ├── warrior-meditation.mp3
       ├── magician-meditation.mp3
       ├── lover-meditation.mp3
       └── sage-meditation.mp3
   ```

#### YouTube Video Embeds
To add YouTube videos, replace the placeholder divs with YouTube iframe embeds:

```html
<!-- Replace this: -->
<div class="video-frame">
    <span>YouTube Video Embed Frame</span>
</div>

<!-- With this: -->
<div class="video-frame">
    <iframe 
        width="100%" 
        height="100%" 
        src="https://www.youtube.com/embed/YOUR_VIDEO_ID" 
        frameborder="0" 
        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
        allowfullscreen
        style="border-radius: 8px;">
    </iframe>
</div>
```

## Browser Compatibility

### Voice Recording Feature
The voice recording feature uses the Web Speech API, which is supported in:
- ✅ Chrome (desktop & mobile)
- ✅ Edge
- ✅ Safari (iOS 14.5+)
- ❌ Firefox (not currently supported)

Users on unsupported browsers can still type their answers manually.

## Features

### Page 1: Welcome
- BLV ID field (optional)
- Name and Email (required)
- Start Session button

### Pages 2-5: The Four Archetypes
Each page covers one archetype:
- Page 2: The Warrior
- Page 3: The Magician
- Page 4: The Lover
- Page 5: The Sage

Features per page:
- Video embed frame
- "Enter Optimal State" audio meditation button
- Three questions with voice recording or text input
- 1000 character limit per answer
- Next button to proceed

### Page 6: Results
- Compiled results from all four archetypes
- "Copy for AI" button (copies to clipboard)
- "Download Result" button (saves as .txt file)
- Pre-formatted prompt for AI interaction

## Customization

### Changing Colors
The site uses CSS variables for easy color customization. Edit these in the `<style>` section:

```css
:root {
    --bg-primary: #2d2d2d;        /* Main background */
    --bg-secondary: #3a3a3a;      /* Card backgrounds */
    --text-primary: #e8e8e8;      /* Main text */
    --text-secondary: #b8b8b8;    /* Secondary text */
    --accent-gold: #d4af37;       /* Gold accent */
    --accent-bronze: #cd7f32;     /* Bronze accent */
    --border-color: #4a4a4a;      /* Borders */
}
```

### Changing Fonts
The site uses Google Fonts:
- **Cinzel** for headings (serif, elegant)
- **Cormorant Garamond** for body text (serif, readable)

To change fonts, update the Google Fonts link and CSS font-family properties.

## Troubleshooting

### Site Not Updating
1. Check GitHub - ensure your commit was successful
2. Check Cloudflare Pages dashboard for build status
3. Clear browser cache (Ctrl+Shift+R or Cmd+Shift+R)

### Voice Recording Not Working
1. Ensure you're using Chrome, Edge, or Safari
2. Grant microphone permissions when prompted
3. Check that you're using HTTPS (required for Web Speech API)

### Past API/Wrangler Issues
This project avoids previous issues by:
- Being purely static (no server-side code)
- No Workers or API routes
- No build process required
- No dependencies to install

## File Structure

```
your-repository/
├── index.html          # Complete application (single file)
├── README.md           # This file
└── audio/              # (Create this folder for meditation audio)
    ├── warrior.mp3
    ├── magician.mp3
    ├── lover.mp3
    └── sage.mp3
```

## Support

For issues with:
- **Cloudflare Pages:** Check Cloudflare dashboard for build logs
- **GitHub sync:** Verify repository connection in Cloudflare
- **Voice recording:** Test in Chrome first, ensure HTTPS
- **Mobile display:** Test on actual devices, not just browser dev tools

## License

Customize as needed for Magic With Miles.

---

**Built for Magic With Miles**  
Framework by Tony Robbins

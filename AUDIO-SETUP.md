# Audio Files Setup Guide

## File Naming Convention

Place your meditation audio files in an `/audio` folder with these names:

```
audio/
├── warrior-meditation.mp3
├── magician-meditation.mp3
├── lover-meditation.mp3
└── sage-meditation.mp3
```

## Supported Audio Formats

- **MP3** - Best compatibility (recommended)
- **OGG** - Good compression, wide support
- **WAV** - Highest quality but larger file size
- **M4A** - Good for iOS devices

## File Size Recommendations

For optimal performance:
- **Target:** 1-3 MB per file
- **Maximum:** 10 MB per file
- **Bitrate:** 128-192 kbps for speech/meditation

Compress larger files using tools like:
- Audacity (free, open source)
- Online audio converters
- FFmpeg

## Implementation Steps

### Step 1: Prepare Your Audio Files

1. Export/convert your meditation audio to MP3 format
2. Name them according to the convention above
3. Optimize file size if needed

### Step 2: Upload to GitHub

```bash
# Create audio folder
mkdir audio

# Add your audio files to the folder
# Then commit and push
git add audio/
git commit -m "Add meditation audio files"
git push origin main
```

Or via GitHub web interface:
1. Create new folder called "audio"
2. Upload your audio files
3. Commit changes

### Step 3: Update index.html

The audio sources are already configured in index.html:

```html
<!-- Page 2 - The Warrior -->
<audio id="audio2" src="audio/warrior-meditation.mp3"></audio>

<!-- Page 3 - The Magician -->
<audio id="audio3" src="audio/magician-meditation.mp3"></audio>

<!-- Page 4 - The Lover -->
<audio id="audio4" src="audio/lover-meditation.mp3"></audio>

<!-- Page 5 - The Sage -->
<audio id="audio5" src="audio/sage-meditation.mp3"></audio>
```

Just make sure your files match these paths!

## Alternative: Using External Audio Hosting

If you prefer to host audio files elsewhere (like AWS S3, Cloudflare R2, or a CDN):

1. Upload your audio files to your hosting service
2. Get the public URL for each file
3. Update the `src` attributes in index.html:

```html
<audio id="audio2" src="https://your-cdn.com/warrior-meditation.mp3"></audio>
```

### Benefits of External Hosting:
- Faster page loads
- Better for large files
- CDN distribution
- Separate from code repository

### Recommended Services:
- **Cloudflare R2** - Free tier, fast delivery
- **Amazon S3** - Reliable, scalable
- **Backblaze B2** - Cost-effective
- **Google Cloud Storage** - Good integration

## Testing Audio Playback

After deployment:

1. Visit each page (2-5)
2. Click "Enter Optimal State" button
3. Verify audio plays correctly
4. Test on both desktop and mobile
5. Check different browsers (Chrome, Safari, Edge)

## Troubleshooting

### Audio Not Playing
- Check file path is correct
- Verify file uploaded successfully
- Ensure HTTPS (some browsers block HTTP audio)
- Check browser console for errors

### Audio Too Quiet/Loud
- Normalize audio levels in your editing software
- Aim for -3dB to -6dB peak levels
- Use compression/limiting if needed

### Large File Sizes
- Convert to MP3 at 128-192 kbps
- Use mono instead of stereo for voice
- Trim silence from beginning/end
- Use tools like Audacity to compress

## Audio Content Suggestions

### Recommended Meditation Length
- **Optimal:** 3-5 minutes per archetype
- **Minimum:** 2 minutes
- **Maximum:** 10 minutes

### Content Structure
1. **Opening** (15-30 seconds)
   - Breathing instruction
   - Setting intention

2. **Core Guidance** (2-4 minutes)
   - Archetype-specific visualization
   - Connecting to inner wisdom

3. **Closing** (15-30 seconds)
   - Gentle return
   - Prompt to answer questions

### Voice and Music
- Use calm, steady voice
- Optional: soft background music or nature sounds
- Avoid jarring transitions
- Keep volume consistent

## Future Enhancements

Consider adding:
- Volume controls
- Playback speed adjustment
- Download audio option
- Audio transcripts for accessibility
- Multiple language options

---

**Need Help?**

If you need assistance:
1. Test audio locally first (open index.html in browser)
2. Check browser console for error messages
3. Verify file paths match exactly
4. Ensure files are committed to GitHub repository

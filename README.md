# Dual n-Back Training Game

A web-based implementation of the Dual n-Back working memory training task, hosted on Cloudflare Pages at [dnb.tannerwj.com](https://dnb.tannerwj.com).

## What is Dual n-Back?

Dual n-Back is a cognitive training exercise that challenges working memory by requiring simultaneous tracking of visual and auditory stimuli. Research suggests it may improve fluid intelligence and working memory capacity with regular practice.

## How to Play

1. **Watch and Listen**: A blue square appears in one of nine grid positions while a letter is spoken
2. **Remember**: Keep track of the position and letter from previous trials
3. **Respond**: Indicate whether the current position or letter matches the one from **n** turns ago

### Response Options

- **Neither**: Current position and letter don't match n-back
- **Position**: Only the position matches n-back
- **Audio**: Only the letter matches n-back
- **Both**: Both position and letter match n-back

### Keyboard Shortcuts

- `Space`: Neither
- `L`: Position only
- `A`: Audio only
- `B`: Both

## Features

- **Manual n-level selection** (1-back through 5-back)
- **Configurable trial count** (20, 40, or 60 trials)
- **Real-time accuracy tracking**
- **Detailed performance statistics**
- **Responsive design** for desktop and mobile
- **Browser-based text-to-speech** (no audio files needed)

## Game Mechanics

- **Timing**: 2.5 seconds per trial (500ms stimulus + 2000ms response window)
- **Letters**: C, H, K, L, Q, R, S, T (8 distinct consonants)
- **Grid**: 3×3 grid (9 positions)
- **Scoring**: Tracks overall, position-only, audio-only, and dual-match accuracy

## Local Development

Simply open `index.html` in a modern web browser. No build process or server required.

```bash
# Clone the repository
git clone https://github.com/yourusername/dnb.git
cd dnb

# Open in browser (example)
open index.html  # macOS
xdg-open index.html  # Linux
start index.html  # Windows
```

## Deployment to Cloudflare Pages

### Option 1: GitHub Integration (Recommended)

1. Push this repository to GitHub
2. Log into [Cloudflare Dashboard](https://dash.cloudflare.com)
3. Go to **Pages** → **Create a project**
4. Connect your GitHub repository
5. Configure build settings:
   - Build command: (leave empty)
   - Build output directory: `/`
6. Click **Save and Deploy**
7. Add custom domain `dnb.tannerwj.com` in project settings

### Option 2: Direct Upload with Wrangler

```bash
# Install Wrangler CLI
npm install -g wrangler

# Login to Cloudflare
wrangler login

# Deploy
wrangler pages deploy . --project-name=dnb-tannerwj
```

Then configure the custom domain in Cloudflare Dashboard.

## Browser Compatibility

Requires a modern browser with:
- CSS Grid support
- Web Speech API (SpeechSynthesis)
- ES6 JavaScript

Tested in Chrome, Firefox, Safari, and Edge.

## Technical Details

- **Pure vanilla JavaScript** - no frameworks or dependencies
- **Single HTML file** - all CSS and JS embedded
- **Client-side only** - no backend required
- **Speech Synthesis API** - for text-to-speech audio

## Performance Tips

- Use headphones for clearer audio
- Start with 2-back before advancing to higher levels
- Aim for 70-80% accuracy (indicates optimal difficulty)
- Take breaks between sessions
- Practice regularly for best results

## Future Enhancements

Potential features for future versions:
- Adaptive difficulty adjustment
- Session history tracking
- Multiple game modes
- Custom audio/visual options
- Leaderboards

## References

- [Gwern's Dual n-Back FAQ](https://gwern.net/dnb-faq) - Comprehensive information about DNB training
- [Brain Workshop](https://brainworkshop.sourceforge.io/) - Popular desktop DNB implementation

## License

MIT License - feel free to use and modify as needed.

# 🎂 bdy - Interactive Birthday Wish Card

A beautiful, interactive single-page application that transforms the simple act of sending birthday wishes into a magical, personalized experience. Celebrate special moments with smooth animations, floating emojis, interactive candles, and voice activation.

**🎉 Live Demo:** https://zelvior.github.io/bdy/

Share a personalized link like `zelvior.github.io/bdy/?to=Alice&from=Bob` to create an instant birthday celebration!

---

## ✨ Features

### 🎯 Core Functionality
- **5-Step Interactive Wizard**: Guided flow through a magical birthday experience
- **Personalization**: Customize recipient name and sender name
- **Custom Wish Messages**: Write heartfelt wishes up to 200 characters
- **Bottle Sealing**: Interactive bottle-tapping mechanic to seal your wish
- **Interactive Candles**: Click individual candles or use voice activation to blow them out
- **Voice Activation**: Hold a button and blow into your mic to extinguish candles with audio detection

### 🎨 Visual Experience
- **Glass-Morphism Design**: Frosted glass UI with soft gradients and elegant shadows
- **Smooth Animations**: Sophisticated card transitions with ease curves and fade effects
- **Floating Emojis**: Continuously spawning birthday-themed emojis that rise and fade
- **Flickering Candles**: Animated candles with realistic staggered flicker effects
- **Interactive Bottle**: Visual feedback when sealing your wish with golden glow
- **Confetti Burst**: Explosive celebratory confetti animation with 80+ emoji pieces
- **Progress Tracking**: Visual step dots that highlight as you move through the wizard
- **Responsive Layout**: Perfectly adapted for mobile (320px), tablet (768px), and desktop (1920px+)

### 🎤 Interactive Elements
- **Microphone Blow Detection**: Hold a button and blow—the app detects audio volume and blows out all remaining candles
- **Volume Visualization**: Real-time gradient bar showing audio input level (green → yellow → red)
- **Tap-to-Blow Candles**: Click individual candles for instant gratification, or let the voice system handle it
- **Sealing Interaction**: Tap the bottle to seal your wish with satisfying animation and confirmation
- **Character Counter**: Live character count (0–200) with visual progress
- **Animated Step Dots**: Clear visual progress through the 5-step journey

### 🔗 Sharing & URL Parameters
- **Shareable Links**: Generate personalized URLs with recipient and sender names
- **URL Parameters**: Support for `to` and `from` query parameters
- **Export to Gallery**: Save the birthday card as an image (900×900px PNG) with:
  - Decorative elements and emoji stickers
  - Your wish in beautiful typography
  - Personalized greeting with recipient name
  - Date stamp
  - Download directly to device gallery
- **Native Share**: Uses device share sheet (if available) or copies text to clipboard
- **No Backend Required**: All processing happens client-side—perfect for static hosting

---

## 🚀 Quick Start

### Option 1: Local Development
1. Clone the repository:
   ```bash
   git clone https://github.com/zelvior/bdy.git
   cd bdy
   ```
2. Open `index.html` in your browser (works with any modern browser)

### Option 2: GitHub Pages
The app is already live at **https://zelvior.github.io/bdy/**

### Option 3: Any Web Server
Deploy `index.html` to your server and access via HTTP/HTTPS—no build step required!

---

## 📋 Step-by-Step Walkthrough

### **Step 0: Animated Loader** 🎂
- Welcoming splash screen with pulsing cake emoji
- Multi-stage progress bar with status updates:
  - "Preheating the oven..." → 15%
  - "Mixing the batter..." → 40%
  - "Baking the layers..." → 65%
  - "Frosting the cake..." → 85%
  - "Lighting the candles! 🕯️" → 100%
- Auto-proceeds to Step 1 after ~4.2 seconds

### **Step 1: Welcome & Personalization** 🎉
**Displays:**
- Recipient's name (from URL param or default "Star")
- Personalized greeting: "Hey [Name]! Today is entirely yours..."
- Sender attribution: "A surprise from [Sender Name]"

**URL Parameters:**
- `to`: Birthday person's name (default: "Star")
- `from`: Sender's name (default: "Someone Special")

**Action:**
- Click "Let's Go! 🚀" to proceed to wish writing

### **Step 2: Write Your Wish** ✍️
**Features:**
- **Textarea Editor**: Write your heartfelt wish (max 200 characters)
- **Placeholder**: "Type your deepest birthday wish here..."
- **Character Counter**: Live count (0 / 200) with bold amber text
- **Inspirational Prompt**: "Think big. The universe is listening."
- **Font Style**: Uses Dancing Script cursive font for that personal touch
- **Word of Caution**: "Be specific. Be bold."

**Validation:**
- Minimum 3 characters required
- Button disabled until requirement is met
- "Seal the Wish 🔒" button enables on valid input

**Navigation:**
- "Seal the Wish 🔒" → Step 3
- "← Back" → Step 1

### **Step 3: Seal Your Wish** 🌊
**Interactive Bottle Mechanic:**
- **Visual Element**: Bottle emoji (🍾) with dashed gold border
- **Interaction**: Tap the bottle to seal your wish
- **Animation Sequence**:
  1. Bottle rotates 25° and scales up (1.25x) with golden glow
  2. Bottle emoji transforms to lock (🔒)
  3. "✅ Wish sealed inside!" message appears in green
  4. Dashed border converts to solid green border
  5. Mini confetti burst (20 floating emojis)
- **Preview Display**: Your wish text appears truncated in the bottle area
- **State Tracking**: Can only seal once; state persists during step

**Navigation:**
- "Blow Out the Candles 🕯️" → Step 4 (enabled after sealing)
- "← Back" → Step 2 (resets bottle state)

### **Step 4: Blow the Candles** 🕯️
**Visual Setup:**
- **Candle Count**: 5 candles display as emoji rows with flames (🔥) and wax (🕯️)
- **Flame Animation**: Each candle flickers independently with staggered timing
- **Status Label**: "5 candles burning..." (updates as you blow them out)

**Two Methods to Extinguish:**

**Method 1: Manual Tap**
- Click any individual candle to blow it out
- "Blow ring" animation expands and fades when candle is clicked
- Character emoji for each extinguished flame
- No touch, no time limit

**Method 2: Microphone Voice Activation**
- **UI**: "🎤 Hold to Blow" button in golden gradient section
- **Flow**:
  1. Tap and hold the button to activate microphone
  2. Browser prompts for microphone permission (first time only)
  3. Audio context starts listening for sound
  4. Volume bar fills in gradient (green → yellow → red) as you blow
  5. At 55% volume threshold, all remaining candles blow out automatically
- **Visual Feedback**:
  - Button changes to "💨 Blowing..." state
  - Button shines with breathing animation
  - Volume bar shows real-time audio level
  - Hint text updates: "Blow hard! Watch the bar fill up."
- **Fallback**: "Mic access denied — tap candles instead!" if permission denied
- **Release**: Release the button to stop listening and close audio context

**Status Updates:**
- Live label shows remaining candles: "5 candles burning..." → "1 candle still burning..." → "🎉 All candles out!"
- When all 5 candles are extinguished, the status turns green and the next button enables

**Navigation:**
- "Make It Official ✨" → Step 5 (enabled after all candles blow out)
- "← Back" → Step 3 (resets candles state)

### **Step 5: Celebration** 🥳
**Final Screen Display:**
- **Celebration Emoji**: Shining, bouncing 🥳 with glow effect
- **Title**: "It's Official!" in Dancing Script cursive font (amber color)
- **Message**: "The candles are out, the wish is sealed, and the universe is already working on it. May this be your most magical year yet! 🌟"
- **Wish Display**: Your full wish shown in elegant typography in a gradient box (amber to pink)
- **Footer**: "Happy Birthday from [Sender Name] 🎂"

**Confetti Celebration:**
- 80 confetti pieces (emojis: 🎈, ✨, 🎊, ⭐, 🎉, 🌟, 🍰, 🎁) burst onto screen
- Each piece falls with rotation, opacity fade, and scale change
- Duration: ~3 seconds per piece

**Action Buttons:**
- **📸 Share Your Wish**: 
  - Uses native share sheet (if available) with formatted text
  - Fallback: Copies wish to clipboard with "✅ Copied!" confirmation (2s)
  - Format: "🎂 My birthday wish: "[wish]" — made on [date]"
- **🔄 Start Over**: Reloads the page to begin fresh
- **🖼️ Save to Gallery**: Exports the birthday card as high-quality PNG image (see below)

---

## 🎨 Export to Gallery Feature

### Generate Custom Birthday Card Image
The **"🖼️ Save to Gallery"** button creates a beautiful 900×900px PNG:

**Design Elements:**
- Gradient background (gold → yellow → pink)
- Decorative blurred circles (semi-transparent colored orbs)
- White frosted glass card with border and shadow
- Scattered emoji decorations around the card edges (🎈, 🎉, ✨, 🌟, 🎊, 🍰, 🎁, ⭐)

**Card Content:**
- Large cake emoji (🎂) centered at top
- Personalized heading: "Happy Birthday, [Name]!" in Dancing Script
- Decorative divider lines with gradient effect
- Section label: "✦ YOUR WISH ✦"
- Your wish text wrapped and formatted in Dancing Script cursive
- Another divider line
- Footer: "With love, [Sender Name] 🎀"
- Date stamp: Current date in long format (e.g., "June 10, 2026")

**Font Rendering:**
- Primary: "Dancing Script" loaded via FontFace API at runtime
- Fallback: System sans-serif if custom font fails to load
- Text shadows for depth and readability

**Export Process:**
1. Button shows "⏳ Generating..." while image is created
2. Button disabled during generation (~2-3 seconds)
3. Automatic download triggered (filename: `birthday-wish-[name].png`)
4. Button shows "✅ Saved!" for 2.5 seconds
5. Button returns to "🖼️ Save to Gallery"

**Compatibility:**
- Works on all modern browsers with Canvas API support
- Supported on mobile (downloads to Photos/Gallery app)
- Uses PNG format for high quality and transparency support

---

## 🔧 Configuration & Customization

### URL Parameters
```
https://zelvior.github.io/bdy/?to=Alice&from=Bob
```

| Parameter | Description | Example | Default |
|-----------|-------------|---------|---------|
| `to` | Birthday person's name | `Alice` | `Star` |
| `from` | Sender's name | `Bob` | `Someone Special` |

**Example URLs:**
```
https://zelvior.github.io/bdy/?to=Sarah&from=Mom
https://zelvior.github.io/bdy/?to=John&from=Friends&to=Dad
```

### Font Customization

The application uses Google Fonts. Modify the font import (line 9):

```html
@import url('https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600;700&family=Quicksand:wght@400;500;600;700&display=swap');
```

- **Dancing Script**: Elegant cursive font for headings and wish text
- **Quicksand**: Clean, rounded sans-serif for body text and UI

### Color Scheme Customization

Edit the CSS gradients and colors in the `<style>` section:

```css
/* Background gradient (body) */
background: linear-gradient(135deg, #fef3c7 0%, #fde68a 40%, #fce7f3 100%);

/* Primary colors */
--gold: #f59e0b;        /* Main accent (buttons, active states) */
--gold-light: #fbbf24;  /* Lighter gold for hover states */
--success: #10b981;     /* Green for completion/sealed */
--danger: #ef4444;      /* Red for mic listening state */
```

### Message Customization

**Loader Stages** (around line 388):
```javascript
const loaderStages = [
  [15, 'Preheating the oven...'],
  [40, 'Mixing the batter...'],
  [65, 'Baking the layers...'],
  [85, 'Frosting the cake...'],
  [100,'Lighting the candles! 🕯️'],
];
```

**Background Float Emojis** (line 327):
```javascript
const EMOJIS_BG = ['🎈','🎉','✨','🎊','⭐','🌟','🍰','🎁'];
```

**Confetti Emojis** (line 591):
```javascript
const pieces = ['🎈','✨','🎊','⭐','🎉','🌟','🍰','🎁','🎀'];
```

---

## 📱 Responsive Design

### Mobile (320px–480px)
- Reduced flame emoji size (1.2rem) and wax emoji (1.4rem)
- Optimized card padding (1.5rem 1.25rem)
- Touch-friendly tap targets for candles and buttons
- Adjusted layout for smaller screens

### Tablet (481px–1024px)
- Standard layout with full spacing
- Touch-optimized interactions
- All animations enabled

### Desktop (1024px+)
- Full feature set enabled
- Hover effects on buttons
- Optimized for mouse input
- Maximum animation visual fidelity
- Flex layout for side-by-side buttons on final screen

---

## 🔐 Browser Support

| Browser | Support | Notes |
|---------|---------|-------|
| Chrome/Edge | ✅ Full | Latest versions |
| Firefox | ✅ Full | Latest versions |
| Safari | ✅ Full | iOS 12+ |
| Mobile Safari (iOS) | ✅ Full | Works great on iPhones |
| Chrome (Android) | ✅ Full | Native support |

**Requirements:**
- ES6+ JavaScript support
- Web Audio API (for microphone voice activation)
- Web Animations API
- Clipboard API (for copy/share features)
- Canvas API (for image export)
- CSS Backdrop Filter support (for glass morphism)

**Permission Requirements:**
- Microphone access (optional, requested on first use for voice activation feature)

---

## 📦 Dependencies

All dependencies are loaded from **CDN**—no npm, no build step required!

| Dependency | Purpose | CDN |
|-----------|---------|-----|
| Tailwind CSS | Utility styling | `https://cdn.tailwindcss.com` |
| Google Fonts | Typography (Dancing Script, Quicksand) | Google Fonts API |
| Web APIs | Native browser APIs | Built-in |

---

## 🎯 State Management

The application uses simple global variables for state:

```javascript
let wish = '';              // User's written wish (max 200 chars)
let candlesBlown = 0;       // Number of candles extinguished
let sealed = false;         // Whether the bottle has been sealed
let audioCtx = null;        // Audio context for microphone
let analyser = null;        // Audio analyser node
let micStream = null;       // Microphone stream
let micActive = false;      // Is microphone currently listening?
let micTimer = null;        // Timer for audio level polling
```

---

## 🎭 Animation Library

### CSS Keyframe Animations
- **`floatUp`**: Emojis float upward with rotation, scaling, and opacity fade (4.5s)
- **`pulse`**: Cake emoji pulses on loader screen (1.4s)
- **`flicker`**: Candle flames flicker realistically with staggered timing (0.55s)
- **`blowOut`**: Ring animation that expands when candle is blown out (0.5s)
- **`breathe`**: Microphone button gently scales up/down when listening (1s infinite)
- **`shine`**: Star emoji shines with brightness and glow effect (2s infinite)
- **`confettiFall`**: Confetti pieces fall, rotate, and fade (1.5–3.5s)

### JavaScript Animations
- **Web Animations API**: Used for smooth card transitions and fade effects
- **setTimeout-based**: Sequenced multi-step animations (loader stages, confetti bursts)
- **requestAnimationFrame**: Used for rendering class changes to optimize DOM repaints

---

## 📊 Performance Characteristics

- **Bundle Size**: ~25 KB (unminified HTML single file with embedded styles and scripts)
- **Load Time**: <2s on modern networks (including CDN dependencies)
- **Frame Rate**: Consistent 60fps animations on modern devices
- **Memory**: Minimal footprint (floating emojis auto-cleanup after 5s, confetti after 4s)
- **Audio Processing**: Efficient real-time audio analysis with 256-point FFT
- **Canvas Rendering**: Hardware-accelerated image export for 900×900px PNG

---

## 🛠️ Technical Architecture

### File Structure
```
bdy/
├── index.html          # Single-file monolithic application (~800 lines)
└── README.md           # This documentation
```

### Code Organization
1. **HTML** (lines 199–321): Semantic structure with 6 card steps (0–5)
2. **CSS** (lines 8–197): Embedded styles with clear comments for each section
3. **JavaScript** (lines 323–797):
   - Configuration (lines 324–340)
   - URL parameter parsing (lines 329–334)
   - State variables (lines 336–340)
   - Floating emoji system (lines 342–353)
   - Step dots rendering (lines 355–365)
   - Card transition logic (lines 367–383)
   - Loader sequence (lines 385–420)
   - Step navigation (lines 422–442)
   - Wish input handling (lines 426–442)
   - Bottle sealing interaction (lines 444–466)
   - Candle system (lines 485–527)
   - Microphone voice activation (lines 529–579)
   - Celebration & confetti (lines 581–605)
   - Canvas image export (lines 607–783)
   - Native share functionality (lines 785–796)

### Key JavaScript Functions
| Function | Purpose |
|----------|---------|
| `spawnFloat(intense)` | Create floating emoji particles with animation |
| `renderDots(containerId, currentStep)` | Update progress indicator dots |
| `goTo(fromId, toId, dotStep)` | Transition between cards with fade effect |
| `startMic()` | Initialize microphone and audio analysis |
| `stopMic()` | Close audio context and cleanup mic stream |
| `buildCandles()` | Create 5 interactive candle elements |
| `blowCandle(candle)` | Mark candle as blown and trigger animation |
| `updateCandleLabel()` | Update status text based on remaining candles |
| `triggerBigConfetti()` | Spawn 80 confetti emoji pieces |
| `drawExportCard()` | Render birthday card to canvas for export |
| `wrapText(ctx, text, x, y, maxW, lineH)` | Wrap text on canvas for export image |
| `roundRect(ctx, x, y, w, h, r)` | Draw rounded rectangle on canvas |

---

## 🚀 Deployment Options

### GitHub Pages (Recommended - Already Live!)
The app is deployed at https://zelvior.github.io/bdy/
- Simply push to the `main` branch
- GitHub Pages automatically serves `index.html`

### Netlify
1. Connect repository to Netlify
2. Set build command to: (leave empty)
3. Set publish directory to: (root)
4. Deploy

### Vercel
1. Import project from GitHub
2. One-click deploy with zero configuration
3. Get automatic HTTPS and custom domains

### Traditional Web Hosting
Simply upload `index.html` to your web server via FTP/SSH.

---

## 💡 Usage Tips & Best Practices

### For Best Experience
- **Desktop**: Use the microphone feature for a fun hands-free experience
- **Mobile**: Tap candles manually or use voice activation (if supported)
- **Full Screen**: Maximizes the floating emoji animation background
- **Share**: Save the card as an image to share on social media or messaging apps
- **Multiple Uses**: Create and export different wish cards for multiple people

### Voice Activation Tips
- **Positioning**: Hold phone/laptop mic close to your mouth for better detection
- **Force**: Blow firmly but naturally—the app detects volume levels, not specific sounds
- **Timing**: You have as long as you want after pressing the button
- **Fallback**: If microphone doesn't work, just tap the candles manually

### Personalization Ideas
- **For Family**: Use recipient and sender names directly
- **For Colleagues**: Keep it professional with formal names
- **For Friends**: Use nicknames and inside jokes
- **For Long Distance**: Export and send as a beautiful image

### Creative Uses
- Digital birthday cards for remote friends and family
- Social media birthday posts (export to gallery)
- Email birthday messages
- Printed cards (screenshot or export and print)
- Event website birthday feature
- Corporate team celebrations
- Surprise birthday reveals (send link to group chat)

---

## 🐛 Troubleshooting

### Microphone Not Working
- Check browser console (F12) for errors
- Verify microphone permission is granted (check browser settings)
- Test with another device or browser
- Ensure you're on HTTPS (some browsers require this for audio)
- Try tapping candles instead as fallback

### Volume Bar Not Responding
- Check microphone volume level on your device
- Blow harder or position mic closer to your mouth
- Test microphone with system audio settings first
- Threshold is 55% of max volume—may need adjustment based on device

### Confetti Not Showing
- Check browser DevTools console (F12) for errors
- Ensure JavaScript is enabled in browser settings
- Verify browser supports DOM manipulation
- Try a different browser

### Animations Stuttering
- Close other browser tabs to free memory
- Enable hardware acceleration in browser settings
- Test on a device with better GPU capabilities
- Check browser performance in DevTools

### Image Export Not Working
- Verify browser has Canvas API support
- Check browser console for errors
- Try in a different browser
- Ensure sufficient disk space for file download
- Clear browser cache if stuck in "Generating..." state

### Fonts Not Loading
- Check internet connection (fonts load from CDN)
- Wait a few seconds for Google Fonts to load
- Check browser console for CORS errors
- Fallback fonts will still display even if custom fonts fail

### URL Parameters Not Loading
- Ensure parameters are URL-encoded (spaces = `%20`)
- Verify parameter names are lowercase (`to`, `from`)
- Check browser console for parsing errors
- Test with simple parameter values first

---

## 📝 Code Examples

### Generate a Personalized Link Programmatically
```javascript
const params = new URLSearchParams({
  to: 'Alice',
  from: 'Bob'
});
const link = `https://zelvior.github.io/bdy/?${params.toString()}`;
console.log(link);
```

### Customize Loader Messages
```javascript
const loaderStages = [
  [15, 'Starting the celebration...'],
  [40, 'Warming up the joy...'],
  [65, 'Preparing the magic...'],
  [85, 'Setting up the fun...'],
  [100,'Ready to celebrate! 🎉'],
];
```

### Add More Floating Emojis
```javascript
const EMOJIS_BG = ['🎈','🎉','✨','🎊','⭐','🌟','🍰','🎁','🎀','💝','🎀'];
```

### Adjust Microphone Sensitivity
```javascript
// Current threshold: 55% (in startMic function)
if (pct > 55) { // Change 55 to adjust sensitivity
  // blow all remaining candles
}
```

---

## 🎁 Features Roadmap

Potential future enhancements (not yet implemented):
- Multiple candle count selection
- Audio visualization (equalizer during mic input)
- Video recording of the celebration
- Animated GIF export
- Multi-language support
- Dark mode toggle
- Custom background patterns
- Wish history/saved wishes
- Social media integration (Twitter, Instagram sharing)
- Leaderboard for voice activation (who blew candles fastest)
- Birthday date scheduling
- Email delivery of wish cards

---

## 📄 License

This project is provided as-is for personal and commercial use. Feel free to modify, customize, and share!

---

## 🤝 Contributing

This is a personal project, but you're welcome to:
- Fork and create your own version
- Use it as a template for similar projects
- Share your creative customizations
- Report issues or suggest improvements via GitHub Issues

---

## 💕 Credits & Inspiration

Made with love for celebrating special people in special ways. Perfect for:
- Long-distance friendships
- Remote team celebrations
- Digital-first relationships
- Memorable moments that deserve something extra
- Making birthdays more interactive and fun

---

## 📞 Support

For questions or issues:
1. Check the **Troubleshooting** section above
2. Review browser console for error messages (F12)
3. Ensure JavaScript is enabled in your browser settings
4. Test in a different browser or device
5. Open a GitHub Issue with details about the problem

---

**Happy celebrating! 🎂✨🎉**

*Made with 💕 and code magic by [zelvior](https://github.com/zelvior)*

*Visit the live app: https://zelvior.github.io/bdy/*

# 🎂 bdy - Interactive Birthday Wish Card

A beautiful, interactive single-page application that transforms the simple act of sending birthday wishes into a magical, personalized experience. Celebrate special moments with smooth animations, floating particles, and heartfelt personalization.

**🎉 Live Demo:** https://zelvior.github.io/bdy/

Share a personalized link like `zelvior.github.io/bdy/?to=Alice&from=Bob&wish=Happy%20Birthday!` to create an instant birthday celebration!

---

## ✨ Features

### 🎯 Core Functionality
- **6-Step Wizard**: Guided flow through an immersive birthday card creation experience
- **Personalization Engine**: Customize recipient name, sender name, relationship, and personal message
- **Theme Selection**: Choose from 6 distinct emotional vibes (Romantic, Fun, Heartfelt, Funny, Poetic, Bold & Brave)
- **Character-Aware Messaging**: Theme-specific starter phrases and inspirational quotes tailored to your celebration style
- **Emoji Signature**: Pick from 12 unique emojis to personalize your message

### 🎨 Visual Experience
- **Glass-Morphism Design**: Modern frosted glass UI with soft gradients and elegant shadows
- **Smooth Animations**: Sophisticated card transitions with ease curves and fade effects
- **Floating Particles**: Continuously spawning birthday-themed particles that rise and fade
- **Flickering Candles**: Animated birthday candles with staggered flicker effects
- **Confetti Burst**: Explosive celebratory confetti animation with 80+ pieces
- **Progress Tracking**: Visual step dots and progress bar that evolve as you move through the wizard
- **Responsive Layout**: Perfectly adapted for mobile (320px), tablet (768px), and desktop (1920px+)

### 🎪 Interactive Elements
- **Playful "No" Button**: A humorous button that:
  - Displays increasingly desperate messages as you click it ("Not yet…" → "The cake is crying 😢")
  - Rotates with each interaction
  - Makes the "Blow out the candles!" button progressively grow larger
  - Creates a fun, lighthearted tension
- **Smart Form Validation**: Real-time field validation with animated shake feedback
- **Character Counter**: Live character count with visual warning when approaching the 280-character limit
- **Multiple Share Options**: Copy text to clipboard, share via WhatsApp, or generate a shareable link

### 🔗 Sharing & URL Parameters
- **Shareable Links**: Generate personalized URLs that skip directly to the candle-blowing step
- **URL Parameters**: Support for `to`, `from`, `wish`, `emoji`, and `theme` query parameters
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
- Welcoming splash screen with bouncing cake emoji
- Animated progress bar with status updates ("Lighting the candles…" → "Candles lit! ✨")
- Auto-proceeds after ~3.2 seconds

### **Step 1: Personalization** 🎁
**Fields:**
- **Their name** (max 30 chars): The birthday person's name
- **Your name** (max 30 chars): Your name or nickname
- **Relationship**: 8 options including best friend, sibling, partner, parent, colleague, child, cousin, or "Someone special"

**Validation:** All fields are required; missing fields shake and highlight on attempt to proceed

### **Step 2: Theme Selection** 🎨
Choose from 6 emotional themes, each with a unique color palette and vibes:
- **💕 Romantic**: Rose/pink gradients - "You mean the world to me"
- **🎉 Super Fun**: Yellow/gold gradients - "Party time! 🥳"
- **💜 Heartfelt**: Purple gradients - "Watching you grow has been my greatest joy"
- **😂 Funny**: Green/mint gradients - "Congratulations on surviving another trip around the sun"
- **🌙 Poetic**: Blue gradients - "May the stars carry your wishes skyward"
- **🔥 Bold & Brave**: Orange gradients - "The best is yet to come — go claim it"

Each theme unlocks theme-specific starter phrases and closing quotes.

### **Step 3: Craft Your Wish** ✍️
**Features:**
- **Starter Phrases**: Quick-insert buttons with theme-appropriate suggestions
- **Message Editor**: 280-character textarea with live character counter and warning indicator (turns red at 240+ chars)
- **Emoji Picker**: 12-emoji grid to choose your signature emoji (`🌟`, `💖`, `🎉`, `✨`, `🎂`, `🥂`, `🌺`, `🎈`, `💫`, `🦋`, `🌈`, `🔥`)
- **Theme Label**: Displays your selected theme as a visual reminder

### **Step 4: Preview & Share** 👀
- **Live Preview**: See exactly how your birthday card will appear with flickering candles, cake, your message, and emoji signature
- **Delivery Options**:
  - 🔗 **Share Link**: Copy a personalized URL to clipboard (skips to step 5)
  - 📋 **Copy Text**: Copy the formatted message for pasting anywhere
  - 💬 **WhatsApp**: Opens WhatsApp with your pre-filled message
- **Back Button**: Return to edit your message at any time

### **Step 5: Make a Wish** 🌬️
- **Candle Display**: Large flickering candles (🕯️) ready to be blown out
- **Playful "No" Button**: Gets progressively harder to click with messages like:
  - "Not yet…"
  - "Still thinking…"
  - "Almost! 🤔"
  - "The candles are melting! 🕯️"
  - "Just blow! 😅"
  - "The cake is crying 😢"
  - And more...
- **Button Growth**: The "Blow out the candles!" button grows with each "No" click
- **Secret Wish Moment**: Encourages the birthday person to make a silent wish

### **Step 6: Celebration** 🥳
- **Confetti Explosion**: 80 colorful confetti pieces burst across the screen
- **Celebratory Message**: Personalized congratulatory message
- **Inspirational Quote**: Theme-based quote displayed in a gold box
- **Signature Emojis**: Your chosen emoji repeated 5 times
- **Replay Options**:
  - 🔄 **Make Another**: Reload and start fresh
  - 🎊 **Celebrate Again**: Trigger another confetti burst

---

## 🔧 Configuration & Customization

### URL Parameters (Shareable Link Format)
```
https://zelvior.github.io/bdy/?to=Alice&from=Bob&wish=HappyBirthday&emoji=💖&theme=romantic
```

| Parameter | Description | Example | Default |
|-----------|-------------|---------|---------|
| `to` | Birthday person's name | `Alice` | `Star` |
| `from` | Sender's name | `Bob` | `Someone special` |
| `wish` | Custom message (URL encoded) | `Happy%20Birthday` | `Wishing you the most wonderful day!` |
| `emoji` | Signature emoji | `💖` | `🌟` |
| `theme` | Theme choice | `romantic` | `heartfelt` |

**Example URLs:**
```
https://zelvior.github.io/bdy/?to=Sarah&from=Mom&theme=romantic
https://zelvior.github.io/bdy/?to=John&from=Friends&wish=Here%27s%20to%20another%20amazing%20year
```

### Color Scheme Customization

Edit the CSS variables in the `<style>` section (lines 11–19):

```css
:root {
  --rose: #e11d48;        /* Primary accent color (buttons, active states) */
  --rose-light: #ffe4e6;  /* Light rose for backgrounds */
  --gold: #f59e0b;        /* Secondary accent color (theme picker) */
  --gold-light: #fef3c7;  /* Light gold for quote backgrounds */
  --plum: #7c3aed;        /* Tertiary accent color (toggle selections) */
  --plum-light: #ede9fe;  /* Light plum for backgrounds */
  --mint: #059669;        /* Success/completion color (progress dots) */
  --bg: #fff9f0;          /* Main background color */
}
```

### Font Customization

The application uses Google Fonts (line 9). Modify the font import to customize typography:

```html
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,600;1,9..144,400&family=DM+Sans:wght@400;500;600&display=swap" rel="stylesheet">
```

- **Fraunces**: Elegant serif font for headings
- **DM Sans**: Clean sans-serif for body text

### Message Customization

**"No" Button Phrases** (around line 618):
```javascript
const noPhrases=[
  "Not yet…",
  "Still thinking…",
  "Almost! 🤔",
  "The candles are melting! 🕯️",
  "Just blow! 😅",
  "The cake is crying 😢",
  // ... add more messages
];
```

**Theme-Specific Starters** (lines 418–425):
```javascript
const STARTERS = {
  romantic: ["You mean the world to me", "Every day with you is a gift", "My heart is fuller because of you"],
  fun: ["Party time! 🥳", "You're officially another year awesome", "Today's forecast: 100% cake and happiness"],
  heartfelt: ["Watching you grow has been my greatest joy", "You make every room brighter", "I'm so proud of who you've become"],
  funny: ["Congratulations on surviving another trip around the sun", "Age is just a number, but yours is getting big", "You're not old, you're vintage"],
  poetic: ["May the stars carry your wishes skyward", "Another chapter begins today, write it beautifully", "You are made of stardust and wonder"],
  adventurous: ["The best is yet to come — go claim it", "This year, dream bigger and dare harder", "Here's to the bold choices ahead of you"]
};
```

**Closing Quotes** (lines 427–434):
```javascript
const QUOTES = {
  romantic: "\"Where there is love, there is life.\"",
  fun: "\"Life is short — eat the cake first.\"",
  heartfelt: "\"The most precious gift we can offer anyone is our attention.\"",
  funny: "\"Age is an issue of mind over matter. If you don't mind, it doesn't matter.\"",
  poetic: "\"We are all made of stardust.\"",
  adventurous: "\"The biggest adventure you can take is to live the life of your dreams.\""
};
```

### Emoji Customization

Add or modify emojis in the emoji picker (line 416):
```javascript
const EMOJIS = ['🌟','💖','🎉','✨','🎂','🥂','🌺','🎈','💫','🦋','🌈','🔥'];
```

---

## 🎨 Theming Details

Each theme provides a cohesive visual and emotional experience:

| Theme | Primary Color | Sample Starter | Quote | Best For |
|-------|---------------|--------|-------|----------|
| Romantic | Rose (#e11d48) | "You mean the world to me" | "Where there is love, there is life." | Partners, close loved ones |
| Fun | Gold (#f59e0b) | "Party time! 🥳" | "Life is short — eat the cake first." | Friends, energetic celebrations |
| Heartfelt | Plum (#7c3aed) | "Watching you grow..." | "The most precious gift we can offer anyone is our attention." | Family, meaningful bonds |
| Funny | Mint (#059669) | "Congratulations on surviving..." | "Age is an issue of mind over matter. If you don't mind, it doesn't matter." | Friends, colleagues |
| Poetic | Sky Blue | "May the stars carry..." | "We are all made of stardust." | Dreamers, artists |
| Bold & Brave | Orange | "The best is yet to come" | "The biggest adventure you can take is to live the life of your dreams." | Go-getters, explorers |

---

## 📱 Responsive Design

### Mobile (320px–480px)
- Single-column layout with optimized spacing
- Touch-friendly button sizing (48px+ tap targets)
- Adjusted emoji grid (5 columns instead of 6)
- Compact card padding
- All animations remain smooth

### Tablet (481px–1024px)
- Optimized spacing and readability
- Full emoji grid
- Comfortable thumb-reach buttons

### Desktop (1024px+)
- Full feature set enabled
- Hover effects on all interactive elements
- Playful button rotation on hover
- Maximum animation visual fidelity

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
- Web Animations API
- Clipboard API (for copy/share features)
- CSS Grid & Flexbox support

---

## 📦 Dependencies

All dependencies are loaded from **CDN**—no npm, no build step required!

| Dependency | Purpose | CDN |
|-----------|---------|-----|
| Tailwind CSS | Utility styling | `https://cdn.tailwindcss.com` |
| Google Fonts | Typography (Fraunces, DM Sans) | Google Fonts API |
| Web APIs | Native browser APIs | Built-in |

---

## 🎯 State Management

The application uses a single global state object:

```javascript
const state = {
  to: '',           // Birthday person's name
  from: '',         // Sender's name
  relation: '',     // Relationship type
  theme: '',        // Selected theme
  wish: '',         // Custom message (max 280 chars)
  emoji: '🌟',      // Signature emoji
  delivery: 'link', // Delivery method (link/copy/whatsapp)
  currentStep: 0    // Current wizard step (0–6)
};
```

---

## 🎭 Animation Library

### CSS Keyframe Animations
- **`rise`**: Particles float upward with rotation and opacity fade
- **`cardIn`**: Cards fade in from below with scale effect
- **`flicker`**: Candles flicker realistically (staggered with `--d` variable)
- **`spinBounce`**: Celebratory emoji bounce and spin (cake on loader, star on celebration)
- **`confFall`**: Confetti pieces fall and rotate across screen

### JavaScript Animations
- **Web Animations API**: Used for button shake effects on validation errors
- **setTimeout-based**: Sequenced multi-step animations for complex scenes (confetti, transitions)

---

## 📊 Performance Characteristics

- **Bundle Size**: ~8 KB (minified HTML single file)
- **Load Time**: <1s on modern networks (CDN dependencies)
- **Frame Rate**: Consistent 60fps animations
- **Memory**: Minimal footprint (particles auto-cleanup after 8s, confetti after 3s)
- **Accessibility**: Semantic HTML, good color contrast, keyboard navigable (Tab + Enter supported)

---

## 🛠️ Technical Architecture

### File Structure
```
bdy/
└── index.html     # Single-file monolithic application (~690 lines)
```

### Code Organization
1. **HTML** (lines 1–227): Semantic structure with 7 card steps (0–6)
2. **CSS** (lines 10–221): Modular style sections with clear comments
3. **JavaScript** (lines 407–689):
   - State management (lines 408–416)
   - Particle system (lines 436–446)
   - Step navigation & validation (lines 458–524)
   - Theme logic (lines 526–531)
   - Wish crafting (lines 533–571)
   - Preview & share (lines 573–608)
   - Candle blow interaction (lines 610–667)
   - Confetti system (lines 648–660)
   - URL parameter handling (lines 669–688)

### Key JavaScript Functions
| Function | Purpose |
|----------|---------|
| `goTo(step)` | Navigate to a specific step (with validation) |
| `transition(from, to)` | Smooth animated card transition with fade effects |
| `validateStep(step)` | Field validation with error feedback (shake animation) |
| `collectStep(step)` | Gather user input from current step into state |
| `pickTheme(el)` | Theme selection handler |
| `buildStep3()` | Dynamically populate wish step with starters and emojis |
| `buildPreview()` | Render preview card with final formatting |
| `pickDelivery(el)` | Select delivery method (link/copy/whatsapp) |
| `sendWish()` | Handle sharing (copy/WhatsApp/link) |
| `buildBlowStep()` | Prepare candle-blowing step with personalization |
| `nudgeNoBtn()` | Handle "No" button clicks (rotate, grow yes button) |
| `makeWish()` | Trigger candle blow-out celebration and confetti |
| `buildCelebration()` | Build final celebration screen with quote and emojis |
| `confettiBurst()` | Spawn 80 confetti pieces with staggered timing |
| `celebrateAgain()` | Trigger another confetti burst and return to step 5 |
| `spawnParticle()` | Create floating background particles |
| `updateProgress(step)` | Update progress bar and step dots |

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
- **Desktop**: Hover over theme buttons and the "No" button to see hover effects
- **Mobile**: Tap the "No" button repeatedly to see the progressive button growth challenge
- **Full Screen**: Maximizes the particle animation background
- **Share**: Use the link option to let recipients experience the full wizard from step 5
- **WhatsApp**: Send directly to individuals or groups for instant birthday celebrations

### Personalization Ideas
- **For Colleagues**: Use the "Funny" theme with the relationship set to "Colleague"
- **For Loved Ones**: Use "Romantic" or "Heartfelt" with custom quotes
- **For Friends**: Use "Super Fun" with party-themed messages
- **For Mentors**: Use "Poetic" or "Bold & Brave" for inspirational vibes

### Creative Uses
- Digital birthday cards for remote friends and family
- Team celebrations in work Slack channels (share the link)
- Social media birthday posts (WhatsApp share)
- Email signature birthday wishes
- Event website birthday feature
- Corporate recognition moments
- Surprise birthday reveals (send link to group chat)

---

## 🐛 Troubleshooting

### Confetti Not Showing
- Check browser DevTools console (F12) for errors
- Ensure z-index conflicts don't exist with other elements
- Verify JavaScript is enabled in browser settings

### Animations Stuttering
- Close other browser tabs to free memory
- Enable hardware acceleration in browser settings
- Test on a device with better GPU capabilities
- Check browser performance in DevTools

### WhatsApp Share Not Working
- Ensure you're on a device with WhatsApp installed (or WhatsApp Web)
- Check that your browser allows pop-ups (disable pop-up blockers)
- Verify you're on an HTTPS connection (required for WhatsApp links)

### URL Parameters Not Loading
- Ensure all parameter values are URL-encoded (spaces = `%20`, quotes = `%27`)
- Verify parameter names are lowercase (`to`, `from`, `wish`, `emoji`, `theme`)
- Check browser console for parsing errors
- Test with simple parameters first

### Name/Message Not Persisting
- The wizard resets when you reload the page (except for URL parameters)
- Use the "Back" buttons to edit without losing data
- Copy your link before sharing to preserve personalization

---

## 📝 Code Examples

### Generate a Personalized Link Programmatically
```javascript
const params = new URLSearchParams({
  to: 'Alice',
  from: 'Bob',
  wish: 'Happy Birthday! Have an amazing day!',
  emoji: '💖',
  theme: 'romantic'
});
const link = `https://zelvior.github.io/bdy/?${params.toString()}`;
console.log(link);
```

### Customize Theme Starter Phrases
```javascript
STARTERS.custom = [
  "Your custom starter message",
  "Another personalized message",
  "And another one"
];
```

### Add a New Theme
```javascript
STARTERS.mystical = ["The stars align for you", "Magic flows through your veins", "This year, anything is possible"];
QUOTES.mystical = "\"Magic is real.\"";
```

### Add More Emojis to the Picker
```javascript
EMOJIS.push('💝', '🎀', '🎊', '⭐');
```

---

## 🎁 Features Roadmap

Potential future enhancements (not yet implemented):
- Voice message support
- Photo collage integration
- Countdown timer before send
- Analytics tracking (e.g., how many people clicked a link)
- Multi-language support
- Dark mode toggle
- Custom background upload
- Email integration
- Database persistence
- Social sharing preview cards (OG meta tags)
- Multiple recipients (send to group)
- Scheduled send times

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

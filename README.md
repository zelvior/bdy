# 🎂 bdy - Interactive Birthday Wish Card

A beautiful, interactive birthday celebration webpage that creates a magical experience for the birthday person. Features smooth animations, confetti celebrations, and a playful "yes/no" button interaction.

## ✨ Features

- **Animated Loader**: A charming cake-themed loading screen that sets the festive mood
- **Glass-Morphism Design**: Modern frosted glass UI with smooth transitions
- **Personalized Greeting**: Customize the birthday person's name and sender name via URL parameters
- **Floating Decorations**: Continuously floating birthday emojis (balloons, confetti, stars, cakes) in the background
- **Playful No Button**: A humorous "Not yet" button that:
  - Shakes and moves away from cursor on hover (desktop)
  - Changes text messages as you try to click it
  - Makes the "Make a Wish!" button grow larger with each attempt
- **Email Notifications**: Integrates with EmailJS to send a notification when the wish is made
- **Confetti Celebration**: Explosive confetti animation when the birthday person confirms their wish
- **Responsive Design**: Optimized for mobile, tablet, and desktop devices
- **Candle Animation**: Flickering animated birthday candles on the main card

## 🚀 Quick Start

### Basic Usage

Simply open `index.html` in your browser or deploy it to any web server.

### Personalization via URL Parameters

Customize the birthday card by adding query parameters to the URL:

```
https://yoursite.com/index.html?to=Alice&from=Bob
```

- `to`: Name of the birthday person (default: "Star")
- `from`: Name of the person sending the wish (default: "Someone Special")

### Example URLs

```
https://yoursite.com/index.html?to=Sarah&from=Mom
https://yoursite.com/index.html?to=John
```

## 🔧 Configuration

### EmailJS Setup (Optional)

To enable email notifications when a wish is made:

1. Sign up for a free account at [EmailJS](https://www.emailjs.com/)
2. Create an email service and template
3. Update the configuration in `index.html` (lines 173-175):

```javascript
const EMAILJS_PUBLIC_KEY = "YOUR_PUBLIC_KEY";
const EMAILJS_SERVICE_ID = "YOUR_SERVICE_ID";
const EMAILJS_TEMPLATE_ID = "YOUR_TEMPLATE_ID";
```

**Note**: If these keys are not configured, the card will still work fine—only the email notification will fail silently.

## 🎨 Customization

### Color Scheme

The gold color scheme can be customized in the CSS variables (lines 12-15):

```css
:root {
    --gold-main: #f59e0b;
    --gold-light: #fcd34d;
}
```

### Fonts

- Primary font: Quicksand (body text)
- Script font: Dancing Script (celebration text)

Both are imported from Google Fonts. You can replace these in the CSS import (line 10).

### Messages

The "No Button" messages can be customized in the JavaScript (line 229):

```javascript
const noMessages = ["Not yet", "Are you sure?", "Really? 🥺", ...];
```

## 📱 Responsive Behavior

- **Mobile**: Touch-friendly buttons with adaptive sizing
- **Desktop**: Hover effects and playful button movement
- **All devices**: Safe keyboard navigation and accessibility features

## 🔐 Browser Compatibility

- Chrome/Edge: ✅ Full support
- Firefox: ✅ Full support
- Safari: ✅ Full support (including iOS)
- Mobile browsers: ✅ Full support

## 📦 Dependencies

- **Tailwind CSS**: Via CDN (styling)
- **EmailJS**: Via CDN (optional, for email notifications)
- **Google Fonts**: Via CDN (Typography)

All dependencies are loaded from CDN—no installation required!

## 📄 File Structure

```
bdy/
├── index.html      # Main application file
└── README.md       # This file
```

## 🎯 How It Works

1. **Loading Phase**: User sees an animated loader with a pulsing cake emoji
2. **Main Card**: After ~3.5 seconds, the birthday greeting appears with two buttons
3. **Playful Interaction**: The "Not yet" button runs away, creating a fun challenge
4. **Celebration**: Clicking "Make a Wish!" triggers:
   - Email notification (if configured)
   - Confetti animation explosion
   - Success message display
5. **Restart**: User can click "Celebrate Again" to reload and start over

## 🌐 Deployment

### GitHub Pages

1. Enable GitHub Pages in repository settings
2. Set source to `main` branch
3. Access at `https://username.github.io/bdy`

### Any Web Server

Simply copy `index.html` to your server and access via HTTP/HTTPS.

### Using Query Parameters with Hosting

Share personalized links:
```
https://username.github.io/bdy/?to=YourName&from=MySender
```

## 🎉 Share Your Wishes

Send this link to the birthday person:

```
https://yoursite.com/bdy/?to=[TheirName]&from=[YourName]
```

They'll be greeted with a personalized, animated birthday message!

## 💡 Tips

- **Best experienced on desktop**: The "no button" chase is more fun with a mouse!
- **Full screen recommended**: Maximizes the floating animation effects
- **Mobile-friendly**: Still works great on phones and tablets with touch interactions
- **Works offline**: All functionality (except email) works without internet

## 📝 Notes

- The email functionality is optional and gracefully fails if not configured
- Floating emojis are generated continuously for a dynamic background
- All animations use CSS keyframes and JavaScript Web Animations API for smooth performance
- The design uses modern glassmorphism with backdrop filters

## 🎁 License

Feel free to use and customize this birthday card for your loved ones!

---

**Made with 💕 and 🎂**

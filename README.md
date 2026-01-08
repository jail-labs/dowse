# Dowse Landing Page

Production-ready landing page for dowse.ai

## Quick Deploy to Vercel

1. Push this folder to a GitHub repo
2. Connect the repo to Vercel
3. Deploy (Vercel will auto-detect it as a static site)

Or use the Vercel CLI:
```bash
npm i -g vercel
vercel
```

## Setup Checklist

### 1. Form Submissions (Required)

The form uses [Formspree](https://formspree.io) for submissions. To set it up:

1. Create a free account at formspree.io
2. Create a new form
3. Copy your form ID (looks like `xyzabcde`)
4. In `public/index.html`, find this line:
   ```javascript
   const FORM_ENDPOINT = 'https://formspree.io/f/YOUR_FORM_ID';
   ```
5. Replace `YOUR_FORM_ID` with your actual form ID

Formspree free tier includes:
- 50 submissions/month
- Email notifications
- Spam filtering

### 2. Social Sharing Image (Recommended)

Create an image for social sharing (when people share your link on LinkedIn/Twitter):

- Size: 1200x630px
- Save as `og-image.png` in the `public` folder
- The meta tags are already set up to use it

### 3. Analytics (Recommended)

Uncomment one of the analytics options in `index.html`:

**Google Analytics:**
```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');
</script>
```

**Plausible (privacy-friendly):**
```html
<script defer data-domain="dowse.ai" src="https://plausible.io/js/script.js"></script>
```

### 4. Favicon Sizes (Optional)

The SVG favicon works in most modern browsers. For full compatibility, generate PNG versions:

1. Go to [realfavicongenerator.net](https://realfavicongenerator.net)
2. Upload `public/favicon.svg`
3. Download the generated package
4. Add the files to the `public` folder

### 5. Custom Domain

In Vercel:
1. Go to your project settings
2. Click "Domains"
3. Add `dowse.ai`
4. Update your DNS records as instructed

## File Structure

```
dowse-deploy/
├── public/
│   ├── index.html      # Main landing page
│   ├── favicon.svg     # Browser tab icon
│   └── og-image.png    # Social sharing image (you create this)
└── README.md
```

## Customization

### Colors
Edit the CSS variables at the top of `index.html`:
```css
:root {
    --bg-primary: #F7F3EB;
    --gold: #B8860B;
    --rust: #8B4513;
    /* etc */
}
```

### Copy
All text is in the HTML. Search and replace as needed.

### Form Fields
The form collects:
- Name
- Work email
- Agency name  
- Monthly placements (1-5, 5-20, 20+)

Modify the form HTML to add/remove fields.

## Support

Questions? Email hello@dowse.ai

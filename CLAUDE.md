# Mood Studios AI — Website Project

## Overview
- **Brand:** Mood Studios AI — AI-powered visuals for beauty & fashion brands
- **Site:** https://moodstudiosai.com
- **Repo:** github.com/taylormadecreative/moodai-website
- **Hosting:** GitHub Pages (main branch, root `/`)
- **Deploy:** `git push origin main` — GitHub Pages auto-builds. Do NOT use Netlify.

## Domain & SSL
- **Root:** `moodstudiosai.com` → GitHub Pages IPs (185.199.x.x)
- **www:** `www.moodstudiosai.com` → 301 redirects to root
- **HTTPS:** Enforced, SSL cert covers both root + www (expires June 23, 2026)
- **CNAME file:** `moodstudiosai.com` (in repo root)

## Email
- **Site contact email:** info@moodstudiosai.com
- **Gmail inbox:** moodstudiosai@gmail.com
- **Email forwarding:** info@moodstudiosai.com should forward to moodstudiosai@gmail.com (configured at domain provider)

## Contact Form
- **Service:** FormSubmit.co (free, no backend needed)
- **Endpoint:** `https://formsubmit.co/ajax/moodstudiosai@gmail.com`
- **Status:** ACTIVE — submissions deliver to moodstudiosai@gmail.com
- **Spam protection:** Honeypot field (`_honey`)
- **Email subject:** "New Inquiry — moodstudiosai.com"
- **Email format:** Table template
- **Submission method:** AJAX (no page redirect)
- **Success message:** "Thank you! We will get back to you within 24–48 hours." (displays 6 seconds below button)
- **Required fields (* marked):** First Name, Last Name, Email, Phone, Project Details, How Did You Hear About Us?
- **Optional fields:** Website, Social Media, Timeline
- **Instruction text:** "All areas with a * must be filled in order to send."
- **Website field:** `type="text"` — accepts `www.site.com` or `site.com` (no https:// required)

### If form stops working
FormSubmit may require re-activation if the email changes. Submit the form once, then check moodstudiosai@gmail.com (and spam) for a confirmation email from FormSubmit. Click the activation link.

## Social Media
- **Instagram:** https://www.instagram.com/moodstudiosai/
- **TikTok:** https://www.tiktok.com/@moodstudiosai
- Links appear in the contact section (icon buttons)

## Tech Stack
- Single `index.html` file (~75KB) — no framework, no build step
- Pure HTML/CSS/JS
- CSS custom properties for theming
- FormSubmit.co for contact form (client-side only)

## Brand Design
- **Gradient:** orange (#e07a3d) → mauve (#9a6b8c) → blue (#2d7fb8)
- **Background:** black (#0a0a0a)
- **Text:** white with varying opacity levels for hierarchy
- **Asterisks on required fields:** orange (gradient-orange color)
- **Font variables:** `--font-display` (headings) and `--font-body` (body text) — defined in CSS `:root`

## Key Sections
1. **Hero** — Full-screen image with logo overlay + tagline "Forget the rules. Follow the MOOD."
2. **Services** — 4 cards: Campaign Visuals, Creative Direction, AI Virtual Models, Motion & Short-Form Video
3. **About** — Brand story with "Work With Us" CTA
4. **The Work** — 6 portfolio cards (Cartier, Dior, Fenty Beauty, Moon Boot, Beautyblender, David Yurman)
5. **Marquee** — Subtle scrolling text divider: "AI VISUALS · MOOD · BEAUTY · FASHION · LUXURY" — transparent bg, small uppercase, 35% opacity, luxury editorial feel
6. **Contact** — Split layout: left side has heading + email + location + socials, right side has form
7. **Footer** — Logo + back to top + copyright

## Location Display
- Shows: **Dallas · LA · NYC · Worldwide** (with orange dot separators + globe icon next to Worldwide)
- Styled: uppercase, letter-spaced, 40% opacity, display font

## File Structure
```
moodai/
├── index.html          # The entire site
├── CNAME               # GitHub Pages custom domain
├── CLAUDE.md           # This file
├── og-image.png        # Open Graph social share image
├── og-image.html       # OG image generator
├── favicon/            # Favicon files
├── mood logo/          # Logo assets
├── portfolio images/   # Work section images
├── screenshots/        # Site screenshots
└── docs/               # Documentation
```

## Schema Markup
- JSON-LD structured data in `<head>` for local business
- Address set to Los Angeles (schema), but site displays Dallas · LA · NYC · Worldwide
- Email: info@moodstudiosai.com
- Knows about: AI Generated Images, Fashion Photography, Beauty Campaigns, Luxury Brand Visuals

## Common Tasks

### Update contact email
Search for the current email in `index.html` — appears in 2 places:
1. Schema markup (line ~53)
2. Contact section mailto link (line ~1762)

### Update social links
Search for `instagram.com` and `tiktok.com` in `index.html` — each appears once in the contact section.

### Update FormSubmit target email
Search for `formsubmit.co/ajax/` in the JavaScript section near the bottom of `index.html`.

### Add/remove required fields
1. Add/remove `required` attribute on the input
2. Add/remove the label's `for` value in the CSS `::after` selector that adds the `*` (search for `content: ' *'`)

## Deployment Checklist
1. Make changes to `index.html`
2. `git add index.html`
3. `git commit -m "description of change"`
4. `git push origin main`
5. Wait ~30 seconds for GitHub Pages to rebuild
6. Hard refresh (Cmd+Shift+R) to bypass cache

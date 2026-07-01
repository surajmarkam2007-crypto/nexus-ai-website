# 🤖 AGENTS.md — NEXUS AI Website
> **This file is the single source of truth for all AI agents (Antigravity, Google AI Studio, Claude).**
> Read this FIRST before touching any file. Do NOT change anything without checking this file.

---

## 🎯 PROJECT OVERVIEW

| Field | Value |
|---|---|
| **Project Name** | NEXUS AI — Official Website |
| **Owner** | Suraj |
| **Type** | Futuristic AI Agency Landing Page |
| **Goal** | Generate ₹1,00,000 in 60 days through client acquisition |
| **Tech Stack** | Pure HTML5 + CSS3 + Vanilla JavaScript + GSAP |
| **No Framework** | No React, No Vue, No Angular — pure HTML/CSS/JS only |
| **Deploy Target** | Netlify (free tier, drag-and-drop) |
| **Status** | 🚧 In Development (10-Day Sprint: Jul 30 – Aug 9, 2026) |

---

## 🎨 DESIGN SYSTEM (NEVER CHANGE THESE)

### Color Palette
```css
:root {
  --primary-orange:  #FF6B35;   /* CTA buttons, highlights, visor glow */
  --deep-navy:       #0A1929;   /* Main background, dark sections */
  --accent-gold:     #FFD700;   /* Halo ring, premium tier, star accents */
  --pure-white:      #FFFFFF;   /* Body text, card backgrounds */
  --dark-gray:       #333333;   /* Secondary text */
  --deep-red:        #CC0000;   /* Jellyfish ambient, energy accents */
  --card-bg:         #0D2137;   /* Service/Pricing card backgrounds */
  --border-glow:     rgba(255, 107, 53, 0.3);  /* Subtle orange borders */
  --gold-glow:       rgba(255, 215, 0, 0.3);   /* Gold box-shadow glow */
}
```

### Typography
```css
/* Display / Headings */
font-family: 'Orbitron', sans-serif;
/* Google Font import: https://fonts.google.com/specimen/Orbitron */

/* Body / Paragraphs */
font-family: 'Inter', sans-serif;
/* Google Font import: https://fonts.google.com/specimen/Inter */

/* UI Elements / Buttons / Labels */
font-family: 'Space Grotesk', sans-serif;
/* Google Font import: https://fonts.google.com/specimen/Space+Grotesk */
```

### Glow Effects (Standard)
```css
/* Orange glow — CTA buttons, hero elements */
box-shadow: 0 0 40px rgba(255, 107, 53, 0.35);

/* Gold glow — Halo, premium card, Most Popular badge */
box-shadow: 0 0 30px rgba(255, 215, 0, 0.3);

/* Red glow — Jellyfish, energy accents */
box-shadow: 0 0 25px rgba(204, 0, 0, 0.25);

/* Text glow — Section headings */
text-shadow: 0 0 20px rgba(255, 107, 53, 0.5);
```

---

## 🏗️ WEBSITE STRUCTURE — 9 SECTIONS

### File: `index.html` (single page, all sections)

```
index.html
├── Section 1:  <nav>        — Fixed Navbar
├── Section 2:  <section id="hero">      — Hero (Visor video)
├── Section 3:  <section id="about">     — About (Halo + Jellyfish)
├── Section 4:  <section id="services">  — Services (6 cards)
├── Section 5:  <section id="process">   — Process (4-step timeline)
├── Section 6:  <section id="portfolio"> — Portfolio (4 case studies)
├── Section 7:  <section id="pricing">   — Pricing (3 packages)
├── Section 8:  <section id="contact">   — Contact/CTA
└── Section 9:  <footer>     — Footer
```

---

## 📋 SECTION-BY-SECTION SPECIFICATION

### SECTION 1 — NAVBAR (Fixed, Transparent → Blur on scroll)
```
Position:     fixed, top: 0, z-index: 9999
Background:   transparent → backdrop-filter: blur(20px) on scroll
Logo:         "NEXUS AI" in Orbitron font, color: --accent-gold
Nav Links:    Home | About | Services | Process | Portfolio | Pricing | Contact
CTA Button:   "Start Project" → WhatsApp link
              Background: linear-gradient(135deg, #FF6B35, #FFD700)
              Border-radius: 50px
Scroll behavior: Add class 'scrolled' after 80px scroll
                 .scrolled { background: rgba(10,25,41,0.95); }
```

### SECTION 2 — HERO (Most Complex — Visor Scroll-Scrub)
```
Layout:       2-column (60% text left, 40% video right)
Background:   --deep-navy (#0A1929)
Particle overlay: Low opacity ambient particles (canvas or CSS)

LEFT SIDE (text content):
  Badge:      "AI-Powered Digital Agency" — gold pill badge
  H1:         "Transform Your Business with AI"
  Subheading: "We build AI Voice Agents, Automation Systems, and 
               Stunning Websites that generate real revenue"
  CTA Primary:   "Start Your Project" → WhatsApp
                 Gradient: #FF6B35 → #FFD700, border-radius: 50px
                 Shimmer animation on button (white light sweep)
  CTA Secondary: "View Our Work" → #portfolio section
                 Border: 2px solid #FF6B35, transparent bg
  Trust Badges:  Row of 3:
                 ✅ 150+ Projects | ⭐ 98% Satisfaction | 🚀 60-Day Delivery

RIGHT SIDE (video):
  Element:    <video id="heroVideo" muted playsinline preload="auto">
  Source:     videos/visor-scroll-scrub.mp4
  Behavior:   SCROLL-SCRUBBING (video plays with scroll position)
  Width:      500px × 600px
  Border-radius: 20px
  Glow:       box-shadow: 0 0 60px rgba(255,107,53,0.4)

ANIMATION:
  On load:    Fade-in text from bottom (opacity 0→1, y: 30px→0)
  On scroll:  Video time = scroll progress × video duration
              Text fades slightly as user scrolls down
```

### SECTION 3 — ABOUT (Halo Ring + Jellyfish Ambient)
```
Background:   Dark navy with subtle gradient
Layout:       2-column (video left, text right)

LEFT SIDE (Halo video):
  Element:    <video id="haloVideo" muted playsinline loop>
  Source:     videos/halo-orbital.mp4
  Size:       450px × 450px
  Animation:  Fade-in + scale (0.9→1.0) when section enters viewport
  Behavior:   Loop continuously once in view

AMBIENT BACKGROUND (Jellyfish):
  Element:    <div class="jellyfish-ambient">
                <video autoplay muted loop playsinline>
                  <source src="videos/jellyfish-loop.mp4">
                </video>
              </div>
  Position:   absolute, top: -80px, right: -50px
  Size:       400px × 400px
  Opacity:    0.18
  Mix-blend:  mix-blend-mode: screen
  Filter:     filter: blur(2px)
  Mobile:     display: none (hidden on < 768px)

RIGHT SIDE (text content):
  H2:         "Who We Are"
  Paragraph:  NEXUS AI mission statement
  Stats (animated counters on scroll):
    - 150+ Projects Delivered
    - 98% Client Satisfaction
    - 60-Day Delivery Guarantee
    - 5+ Industries Served
  Counter animation: 0 → target number, 2s duration, ease-out

SECTION ANIMATION:
  Trigger:    When section enters viewport (ScrollTrigger)
  Text:       Fade in from right (x: 50→0, opacity: 0→1)
  Video:      Fade in + scale from left
```

### SECTION 4 — SERVICES (6 Cards — 2×3 Grid + Tilt Animation)
```
Background:   Slightly lighter navy (#0D2137)
Layout:       CSS Grid, 3 columns × 2 rows, gap: 24px

SERVICES LIST:
  1. AI Voice Agents       → Icon: sound-wave spiral (orange)
  2. AI Automation         → Icon: rotating gears (gold)
  3. Website Development   → Icon: globe with nodes (orange+gold)
  4. AI Video Generation   → Icon: film reel with light (orange)
  5. AI Poster Design      → Icon: layered frames (gold)
  6. Lead Generation       → Icon: target rings (red-orange)

CARD SPEC:
  Background:   #0D2137
  Border:       2px solid transparent (→ var(--primary-orange) on hover)
  Border-radius: 16px
  Padding:      28px
  Icon:         64px × 64px (3D generated image)
  Title:        Orbitron font, 18px, white
  Description:  Inter font, 14px, #aaa
  Hover CTA:    "Learn More →" — appears on hover

CARD ANIMATIONS:
  Library:      Vanilla Tilt.js (CDN)
  Settings:     { max: 15, speed: 400, scale: 1.05, glare: true, "max-glare": 0.2 }
  GSAP scroll:  Cards fade in staggered (0.15s delay between each card)
                gsap.from(".service-card", {
                  opacity: 0, y: 60, duration: 0.8,
                  stagger: 0.15, ease: "power2.out",
                  scrollTrigger: { trigger: "#services", start: "top 70%" }
                })
  Border glow:  On hover, border glows orange
  Icon float:   CSS @keyframes float (y: 0 → -8px → 0, 3s infinite)
```

### SECTION 5 — PROCESS (4-Step Animated Timeline)
```
Background:   --deep-navy (#0A1929)
Layout:       Horizontal timeline (desktop) / Vertical (mobile)

STEPS:
  1. Discovery    (🔴 Red node)     — "We understand your business goals"
  2. Design       (🟠 Orange node)  — "Create the perfect solution"
  3. Build        (🟡 Gold node)    — "Fast execution with AI tools"
  4. Launch       (✨ Bright node)  — "Deploy and start generating revenue"

TIMELINE LINE:
  Background: linear-gradient(90deg, #CC0000, #FF6B35, #FFD700, #FFFDE7)
  Height:     4px
  Animation:  Width draws from 0% → 100% as user scrolls
              GSAP ScrollTrigger scrub: true

NODE ANIMATION:
  Each node:  Circle, 20px diameter, glows when "reached" by line
  Glow pulse: @keyframes pulse (box-shadow 0→30px→0, 1.5s infinite)
  Text:       Fades in from below when node is activated

GSAP CODE:
  gsap.to(".timeline-progress", {
    width: "100%",
    ease: "none",
    scrollTrigger: {
      trigger: "#process",
      start: "top 60%",
      end: "bottom 60%",
      scrub: true
    }
  });
```

### SECTION 6 — PORTFOLIO (4 Case Studies)
```
Background:   #0D2137
Layout:       2×2 grid (desktop), 1 column (mobile)

CASE STUDIES:
  1. Bright Future Coaching    → Orange accent
     Problem:  No online presence, losing students to competitors
     Solution: Website + WhatsApp Chatbot + Lead Funnel
     Result:   50+ inquiries/month, ₹5L monthly revenue

  2. Dr. Sharma's Clinic       → Gold accent
     Problem:  50+ missed calls/day, no appointment system
     Solution: AI Voice Agent + Appointment Automation
     Result:   0 missed calls, 300+ patients/month

  3. Pizza Palace Restaurant   → Red accent
     Problem:  Manual order taking, high error rate
     Solution: WhatsApp Order Bot + Kitchen Automation
     Result:   200+ daily orders, 40% time saved

  4. Prime Properties (Real Estate) → Orange+Gold accent
     Problem:  Losing leads due to slow follow-up
     Solution: CRM Automation + AI Lead Scoring
     Result:   ₹20L additional deals closed in 30 days

CARD SPEC:
  Background image: Blurred industry photo (opacity 0.3 overlay)
  Overlay:     Dark gradient (bottom-to-top)
  Accent border: Left border 4px solid (accent color per case)
  Stats:       Large numbers with gold color (animated counter)
  Hover:       Image brightens, scale: 1.02, border glows

ANIMATION:
  gsap.from(".portfolio-card", {
    opacity: 0, y: 80, duration: 1,
    stagger: 0.2, ease: "power3.out",
    scrollTrigger: { trigger: "#portfolio", start: "top 65%" }
  });
```

### SECTION 7 — PRICING (3 Packages)
```
Background:   --deep-navy (#0A1929)
Layout:       3-column flex (desktop), 1-column (mobile)

PACKAGES:
  Starter (₹7,000 – ₹10,000):
    Color:      --primary-orange (#FF6B35)
    Border:     2px solid #FF6B35
    Glow:       0 0 15px rgba(255,107,53,0.2)
    Includes:   Basic Website, 5 Pages, WhatsApp Integration,
                Basic SEO, 1 Month Support
    CTA:        "Get Started"

  Growth (₹18,000 – ₹25,000):  ← MOST POPULAR
    Color:      --accent-gold (#FFD700)
    Border:     2px solid #FFD700
    Glow:       0 0 30px rgba(255,215,0,0.4)
    Scale:      transform: scale(1.05) (slightly bigger)
    Badge:      "⭐ MOST POPULAR" ribbon (top-right corner)
    Includes:   Everything in Starter + AI Voice Agent,
                WhatsApp Bot, Social Media Content (30 days),
                3 Months Support, Analytics Dashboard
    CTA:        "Start Growing" (gradient button)

  Premium (₹35,000 – ₹50,000+):
    Color:      Bright gold gradient
    Border:     2px solid #FFD700
    Glow:       0 0 20px rgba(255,215,0,0.3)
    Includes:   Everything in Growth + Custom AI Automation,
                Video Generation, Lead Gen System, 6 Months Support,
                Monthly Strategy Calls, Priority Delivery
    CTA:        "Go Premium"

FAQ Accordion (below pricing cards):
  Q1: How fast do you deliver?
  Q2: Do you offer EMI payment?
  Q3: What if I'm not satisfied?
  Q4: Do you provide ongoing support?
  Q5: Can I upgrade my package later?

ANIMATION:
  Cards: stagger fade-in from bottom
  Most Popular: subtle continuous glow pulse animation
```

### SECTION 8 — CONTACT / CTA
```
Background:   Linear gradient (--deep-navy → slightly lighter)
Layout:       Centered, full-width

Content:
  H2:         "Ready to Transform Your Business?"
  Subtext:    "Join 150+ businesses already growing with AI"

  PRIMARY CTA (WhatsApp):
    Text:     "💬 Start Your Project on WhatsApp"
    Link:     https://wa.me/91XXXXXXXXXX (replace with real number)
    Style:    gradient(#FF6B35 → #FFD700), 50px border-radius
    Glow:     0 0 20px rgba(255,107,53,0.4)
    Animation: Shimmer sweep on button + hover lift effect

  TRUST BADGES:
    ✅ 150+ Projects Delivered
    ⭐ 98% Client Satisfaction
    🔒 100% Confidential
    ⚡ Response Within 2 Hours
```

### SECTION 9 — FOOTER
```
Background:   #050F1A (deepest navy)
Layout:       4-column grid

Column 1 — Brand:
  Logo:       "NEXUS AI" (Orbitron, gold)
  Tagline:    "AI-Powered Growth for Your Business"
  Social icons: LinkedIn | Instagram | WhatsApp

Column 2 — Services:
  AI Voice Agents | AI Automation | Website Development
  AI Video | Poster Design | Lead Generation

Column 3 — Company:
  About | Portfolio | Pricing | Contact

Column 4 — Contact:
  WhatsApp: +91 XXXXXXXXXX
  Email: [your email]
  Location: India

Bottom bar:
  © 2026 NEXUS AI. All Rights Reserved.
```

---

## 🎬 VIDEO INTEGRATION SPECS

### VIDEO 1 — VISOR (Hero Section — Scroll Scrubbing)
```
File:         videos/visor-scroll-scrub.mp4
Duration:     5-6 seconds
Resolution:   1920×1080 (16:9)
Size target:  < 8MB (compress with HandBrake)
Behavior:     currentTime updates with scroll progress (NOT autoplay)
Color theme:  Orange (#FF6B35) primary glow
Concept:      Dormant → Activated awakening

HTML:
<video id="heroVideo" muted playsinline preload="auto">
  <source src="videos/visor-scroll-scrub.mp4" type="video/mp4">
</video>

GSAP Code:
gsap.registerPlugin(ScrollTrigger);
const heroVideo = document.getElementById('heroVideo');
heroVideo.addEventListener('loadedmetadata', () => {
  ScrollTrigger.create({
    trigger: "#hero",
    start: "top top",
    end: "bottom top",
    scrub: true,
    onUpdate: (self) => {
      heroVideo.currentTime = self.progress * heroVideo.duration;
    }
  });
});
```

### VIDEO 2 — HALO RING (About Section — Fade-In Loop)
```
File:         videos/halo-orbital.mp4
Duration:     5-6 seconds
Resolution:   1080×1080 (1:1 square)
Size target:  < 6MB
Behavior:     Autoplay loop once in viewport, pause when leaving
Color theme:  Gold (#FFD700) primary glow
Concept:      Orbital camera arc revealing divine ring

HTML:
<video id="haloVideo" muted playsinline loop preload="auto">
  <source src="videos/halo-orbital.mp4" type="video/mp4">
</video>

GSAP Code:
ScrollTrigger.create({
  trigger: "#about",
  start: "top 80%",
  onEnter: () => {
    gsap.fromTo("#haloVideo",
      { opacity: 0, scale: 0.9 },
      { opacity: 1, scale: 1, duration: 1.2, ease: "power2.out" }
    );
    document.getElementById('haloVideo').play();
  },
  onLeaveBack: () => {
    document.getElementById('haloVideo').pause();
  }
});
```

### VIDEO 3 — JELLYFISH (About Ambient Background)
```
File:         videos/jellyfish-loop.mp4
Duration:     7 seconds (seamless loop)
Resolution:   1080×1080 (1:1 square)
Size target:  < 5MB
Behavior:     Autoplay loop, ambient background element
Color theme:  Red-Orange (#CC0000 → #FF4500) bioluminescent
Concept:      Neural flow, pulsing energy background

HTML:
<div class="jellyfish-ambient">
  <video autoplay muted loop playsinline>
    <source src="videos/jellyfish-loop.mp4" type="video/mp4">
  </video>
</div>

CSS:
.jellyfish-ambient {
  position: absolute;
  top: -80px;
  right: -50px;
  width: 400px;
  height: 400px;
  opacity: 0.18;
  mix-blend-mode: screen;
  pointer-events: none;
  overflow: hidden;
  filter: blur(2px);
  border-radius: 50%;
}
@media (max-width: 768px) {
  .jellyfish-ambient { display: none; }
}

GSAP Fade:
ScrollTrigger.create({
  trigger: "#about",
  start: "top 60%",
  end: "bottom 40%",
  onEnter: () => gsap.to(".jellyfish-ambient", { opacity: 0.18, duration: 0.8 }),
  onLeaveBack: () => gsap.to(".jellyfish-ambient", { opacity: 0, duration: 0.8 })
});
```

---

## 🎭 ANIMATION MASTER PLAN

### Libraries (CDN — paste in <head>)
```html
<!-- GSAP Core -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/gsap.min.js"></script>
<!-- ScrollTrigger Plugin -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.12.2/ScrollTrigger.min.js"></script>
<!-- Vanilla Tilt (Service Cards) -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/vanilla-tilt/1.7.0/vanilla-tilt.min.js"></script>
<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Inter:wght@300;400;600&family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet">
```

### Animation Checklist Per Section
```
Navbar:     ✅ Blur + bg-color transition on scroll (CSS only)
Hero:       ✅ Text fade-in on load | Video scroll-scrub (GSAP)
About:      ✅ Halo fade-in + play (GSAP) | Stat counter (JS)
            ✅ Jellyfish ambient fade (GSAP) | Text slide from right
Services:   ✅ Cards stagger fade-in (GSAP) | Tilt hover (Vanilla Tilt)
            ✅ Icon float (CSS) | Border glow on hover (CSS)
Process:    ✅ Line draw animation (GSAP scrub) | Node pulse (CSS)
            ✅ Text fade per step (GSAP stagger)
Portfolio:  ✅ Cards stagger fade-in (GSAP) | Image brighten on hover
            ✅ Counter animation for stats (JS Intersection Observer)
Pricing:    ✅ Cards fade-in stagger (GSAP) | Glow pulse on Popular
            ✅ FAQ accordion (vanilla JS toggle)
Contact:    ✅ Shimmer button (CSS) | Lift on hover (CSS transform)
Footer:     ✅ Fade-in on scroll (GSAP) | Social icon hover glow (CSS)
```

### Service Card Tilt Init Code
```javascript
VanillaTilt.init(document.querySelectorAll(".service-card"), {
  max: 15,
  speed: 400,
  scale: 1.05,
  glare: true,
  "max-glare": 0.2,
  perspective: 1000
});
```

### Stat Counter Function
```javascript
function animateCounter(element, target, duration = 2000) {
  let start = 0;
  const increment = target / (duration / 16);
  const timer = setInterval(() => {
    start += increment;
    if (start >= target) {
      element.textContent = target + "+";
      clearInterval(timer);
    } else {
      element.textContent = Math.floor(start) + "+";
    }
  }, 16);
}

// Trigger on scroll
const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      animateCounter(document.getElementById('stat-projects'), 150);
      animateCounter(document.getElementById('stat-clients'), 98);
      observer.disconnect();
    }
  });
}, { threshold: 0.5 });
observer.observe(document.getElementById('about'));
```

### Navbar Scroll Behavior
```javascript
window.addEventListener('scroll', () => {
  const navbar = document.querySelector('nav');
  if (window.scrollY > 80) {
    navbar.classList.add('scrolled');
  } else {
    navbar.classList.remove('scrolled');
  }
});
```

---

## 📁 FILE STRUCTURE (Complete)

```
nexus-ai-website/
├── 📄 index.html              ← Final production file
├── 📄 AGENTS.md               ← THIS FILE (AI context)
├── 📄 README.md               ← Human-readable project overview
├── 📄 .antigravityignore      ← Exclude heavy files from AI scanning
├── 📄 .gitignore              ← Exclude node_modules etc.
│
├── 📁 css/
│   ├── main.css               ← CSS variables + global styles
│   ├── animations.css         ← All @keyframes
│   ├── components.css         ← Cards, buttons, badges
│   └── responsive.css         ← Mobile breakpoints
│
├── 📁 js/
│   ├── main.js                ← Entry point, init all
│   ├── animations.js          ← All GSAP + ScrollTrigger code
│   ├── counter.js             ← Stat counter logic
│   ├── tilt.js                ← Vanilla Tilt init
│   ├── navbar.js              ← Scroll behavior
│   └── faq.js                 ← Accordion toggle
│
├── 📁 images/
│   ├── visor/
│   │   ├── visor-starting.png
│   │   └── visor-ending.png
│   ├── halo/
│   │   ├── halo-starting.png
│   │   └── halo-ending.png
│   ├── jellyfish/
│   │   ├── jellyfish-starting.png
│   │   └── jellyfish-ending.png
│   ├── services/
│   │   ├── icon-voice.png
│   │   ├── icon-automation.png
│   │   ├── icon-website.png
│   │   ├── icon-video.png
│   │   ├── icon-design.png
│   │   └── icon-leads.png
│   └── portfolio/
│       ├── coaching-bg.jpg
│       ├── clinic-bg.jpg
│       ├── restaurant-bg.jpg
│       └── realestate-bg.jpg
│
├── 📁 videos/
│   ├── visor-scroll-scrub.mp4   ← HERO video (< 8MB)
│   ├── halo-orbital.mp4         ← ABOUT video (< 6MB)
│   └── jellyfish-loop.mp4       ← AMBIENT video (< 5MB)
│
├── 📁 components/              ← HTML snippets (reference only)
│   ├── navbar.html
│   ├── hero.html
│   ├── about.html
│   ├── services.html
│   ├── process.html
│   ├── portfolio.html
│   ├── pricing.html
│   ├── contact.html
│   └── footer.html
│
├── 📁 docs/
│   ├── roadmap.md             ← Week-by-week progress
│   ├── audit.md               ← Antigravity code audit output
│   ├── color-palette.md       ← Design tokens
│   ├── animations.md          ← Animation documentation
│   └── deployment-notes.md    ← Deploy instructions
│
└── 📁 dev/                    ← Daily build files (NOT for production)
    ├── day1.html
    ├── day2.html
    ├── day3.html
    ├── day4.html
    ├── day5.html
    ├── day6.html
    ├── day7.html
    ├── day8.html
    ├── day9.html
    └── day10.html             ← Final = copy to index.html
```

---

## 🔧 AGENT INSTRUCTIONS (Read Before Every Task)

### For Google AI Studio:
```
You are building a section of the NEXUS AI website.
- Use ONLY HTML5 + CSS3 + Vanilla JS (no React, no frameworks)
- Follow the color palette in this AGENTS.md exactly
- Import fonts from Google Fonts (Orbitron, Inter, Space Grotesk)
- Import GSAP from cdnjs.cloudflare.com
- All section IDs must match exactly: #hero, #about, #services, etc.
- Do NOT change CSS variable names
- Mobile-first responsive (breakpoint: 768px)
- When done, output the complete HTML for that section only
```

### For Antigravity:
```
Project: NEXUS AI website (futuristic AI agency)
Context: Read AGENTS.md first.
Primary tasks in Antigravity:
  1. GSAP ScrollTrigger animation debugging (Day 3)
  2. Video sync issues (scroll-scrub timing)
  3. Mobile responsive bug fixing (Day 9)
  4. Cross-browser testing (Day 10)
  5. Performance audit (before deploy)
Do NOT rewrite sections from scratch — only fix specific issues.
Always check against color palette before suggesting color changes.
```

### For Claude (Me):
```
I already have full context of this project.
Key things to remember:
- Single page HTML, no frameworks
- 3 video elements (Visor/Halo/Jellyfish)
- GSAP + ScrollTrigger + Vanilla Tilt
- Colors: Orange #FF6B35, Navy #0A1929, Gold #FFD700
- Daily build files: dev/day1.html → dev/day10.html
- Deploy target: Netlify (drag-and-drop)
- WhatsApp CTA placeholder: +91XXXXXXXXXX (replace before deploy)
```

---

## ⚠️ CRITICAL RULES (Never Break These)

```
1. ❌ Never use React, Vue, Angular, or any framework
2. ❌ Never change CSS variable names (--primary-orange, etc.)
3. ❌ Never import external fonts other than Orbitron/Inter/Space Grotesk
4. ❌ Never add videos > 10MB (compress first with HandBrake)
5. ❌ Never remove muted + playsinline attributes from video tags
6. ❌ Never deploy day1-day9.html files (only index.html goes live)
7. ✅ Always test on mobile (768px breakpoint) after each day
8. ✅ Always git commit after finishing each day's work
9. ✅ Always keep AGENTS.md updated if you change structure
10. ✅ WhatsApp link format: https://wa.me/91XXXXXXXXXX
```

---

## 📊 10-DAY BUILD SCHEDULE

| Day | Date | Section | Output File | Tool |
|---|---|---|---|---|
| 1 | Jul 30 | Navbar + Base CSS Variables | dev/day1.html | AI Studio |
| 2 | Jul 31 | Hero (Text + Layout, no video) | dev/day2.html | AI Studio |
| 3 | Aug 1 | Hero Animations + Visor Video | dev/day3.html | **Antigravity** |
| 4 | Aug 2 | About (Halo + Jellyfish) | dev/day4.html | AI Studio |
| 5 | Aug 3 | Services (6 Cards + Tilt) | dev/day5.html | AI Studio |
| 6 | Aug 4 | Process Timeline | dev/day6.html | AI Studio |
| 7 | Aug 5 | Portfolio (4 Case Studies) | dev/day7.html | AI Studio |
| 8 | Aug 6 | Pricing + Contact + Footer | dev/day8.html | AI Studio |
| 9 | Aug 7 | Mobile Responsive + Bug Fix | dev/day9.html | **Antigravity** |
| 10 | Aug 9 | Final Test + Deploy | index.html | **Antigravity** |

---

*Last updated: June 30, 2026 | Version: 1.0*
*Owner: Suraj | Project: NEXUS AI Website*

# 🔧 COMPLETE SETUP GUIDE
## Google AI Studio + GitHub + Antigravity — Step-by-Step

---

## STEP 1: GitHub Setup (15 minutes)

### 1.1 Account + Repo बनाओ
```
1. github.com पर जाओ → Sign Up (free)
2. Email verify करो
3. "+ New Repository" click करो
4. Settings:
   Name:        nexus-ai-website
   Visibility:  Private (अभी के लिए, deploy के बाद public कर सकते हो)
   Initialize:  ✅ Add README file
5. "Create repository" click करो
```

### 1.2 Files Upload करो (easy method — no terminal needed)
```
Method A: Drag & Drop (simplest)
1. GitHub repo page पर जाओ
2. "Add file" → "Upload files" click करो
3. ये files drag करो:
   - AGENTS.md       (download below से)
   - README.md
   - .antigravityignore
   - .gitignore
4. Commit message: "Initial project setup"
5. "Commit changes" click करो

Method B: GitHub Desktop App (recommended for daily use)
1. desktop.github.com से download करो
2. "Clone repository" → nexus-ai-website select
3. Clone to: Desktop/nexus-ai-website/
4. यहाँ files डालो → Commit → Push
```

### 1.3 Folder Structure बनाओ
```
GitHub पर "Create new file" से बनाओ:
docs/.gitkeep      (docs folder)
images/.gitkeep    (images folder)
videos/.gitkeep    (videos folder)
css/.gitkeep       (css folder)
js/.gitkeep        (js folder)
dev/.gitkeep       (daily builds folder)

Note: .gitkeep = empty file जो folder को GitHub पर visible रखता है
```

---

## STEP 2: Google AI Studio Setup (10 minutes)

### 2.1 Access
```
1. aistudio.google.com पर जाओ
2. Google account से login करो
3. Left sidebar → "Build" click करो (not "Playground")
```

### 2.2 Project Start करो
```
1. "+ New Project" click करो
2. नाम: "NEXUS AI Website"
3. Model: Gemini 1.5 Flash (DEFAULT रखो — free tier)
   Note: Gemini Pro पर मत जाओ unless Flash fail करे
4. "Create" click करो
```

### 2.3 Context File Upload करो
```
1. Chat window में paperclip icon click करो
2. AGENTS.md file upload करो
3. यह message भेजो:

"Read the AGENTS.md file I uploaded. This is context for the 
NEXUS AI website project. Confirm you understand the:
1. Color palette (3 main colors)
2. 9-section structure
3. Tech stack (HTML+CSS+JS, no frameworks)
4. Video integration (Visor/Halo/Jellyfish)
After confirming, wait for my first task."

AI को context clear करो, फिर काम शुरू करो।
```

### 2.4 Day 1 Prompt (July 30)
```
Paste this exact prompt:

"Build Day 1 of the NEXUS AI website.

Task: Create the base HTML structure with:
1. Complete HTML5 boilerplate
2. Google Fonts import (Orbitron + Inter + Space Grotesk)
3. GSAP + ScrollTrigger CDN import
4. Vanilla Tilt CDN import
5. CSS :root with all color variables from AGENTS.md
6. Fixed Navbar with:
   - Logo: 'NEXUS AI' in Orbitron, gold color
   - Nav links: Home | About | Services | Process | Portfolio | Pricing | Contact
   - CTA button: 'Start Project' (orange-gold gradient)
   - Scroll behavior: add class 'scrolled' after 80px
7. Placeholder sections (empty divs with correct IDs):
   #hero, #about, #services, #process, #portfolio, #pricing, #contact, footer
8. Mobile hamburger menu (working)

Output: Complete HTML file ready to save as dev/day1.html"
```

### 2.5 GitHub Push
```
AI से code मिलने के बाद:
1. Code copy करो
2. Notepad/VS Code में paste करो
3. Save as: Desktop/nexus-ai-website/dev/day1.html
4. GitHub Desktop से:
   - Changes tab में day1.html दिखेगा
   - Commit message: "Day 1: Navbar + base structure"
   - "Push origin" click करो
5. ✅ GitHub पर check करो
```

---

## STEP 3: Antigravity Setup (30 minutes, Day 3 से करना)

### 3.1 Installation
```
1. antigravity.ai पर जाओ
2. Free account बनाओ
3. Desktop app download करो (VS Code fork है)
4. Install करो
```

### 3.2 GitHub Repo Connect करो
```
Method A: GitHub Clone (recommended)
1. Antigravity खोलो
2. Terminal खोलो (Ctrl+` / Cmd+`)
3. ये commands चलाओ:
   cd Desktop
   git clone https://github.com/[tumhara-username]/nexus-ai-website.git
   cd nexus-ai-website
4. Antigravity में "Open Folder" → nexus-ai-website select करो

Method B: Direct Import
1. Antigravity → File → Open Folder
2. Desktop/nexus-ai-website/ select करो
3. GitHub Desktop already sync कर देगा
```

### 3.3 AGENTS.md को Antigravity में Activate करो
```
1. nexus-ai-website folder में AGENTS.md पहले से होगा
2. Antigravity chat panel में यह message भेजो:

"Read AGENTS.md in this project root. This is your complete 
context for the NEXUS AI website. I need your help with:
[specific problem]

Do NOT rewrite any section from scratch. Only fix the 
specific issue I describe."

Antigravity अपने आप AGENTS.md पढ़ लेगा।
```

### 3.4 Credit बचाने की Settings
```
1. Settings → AI Credits → "Overages": OFF रखो
2. Model selection:
   - Default: Gemini Flash (credits बचाओ)
   - Complex problems only: Claude Sonnet
   - NEVER: Claude Opus for small tasks
3. काम खत्म होने पर: Antigravity पूरी तरह बंद करो
   (Minimize मत करो — background indexing credits जलाता है)
4. .antigravityignore already बनाई हुई है — यह videos/ folder को scan नहीं करेगा
```

### 3.5 Antigravity से GitHub Push करो
```
Antigravity के terminal में:
git add .
git commit -m "Day 3: Hero scroll-scrub animation added"
git push

यह automatic push है — Manual Bridge की ज़रूरत नहीं!
```

---

## STEP 4: Daily Workflow Loop

```
हर दिन यही routine follow करो:

MORNING (30 min):
├── GitHub खोलो, yesterday का code review करो
├── docs/roadmap.md में आज का checklist देखो
└── Google AI Studio खोलो, AGENTS.md upload करो (new session हो तो)

MAIN WORK (2-3 hours):
├── AI Studio में उस दिन का section बनाओ
├── Preview test करो
├── छोटे tweaks AI Studio में ही करो
└── Final code copy करो

EVENING (15 min):
├── dev/dayX.html file save करो
├── GitHub Desktop से commit + push करो
├── Commit message: "Day X: [section name] complete"
└── docs/roadmap.md में ✅ mark करो

WEEKLY:
├── Full site preview (सब sections together)
├── Mobile test (375px)
├── docs/audit.md update करो
└── Next week plan करो
```

---

## STEP 5: Deploy on Netlify (Day 10)

```
1. index.html तैयार करो (day9.html copy करके)
2. सब +91XXXXXXXXXX replace करो with real WhatsApp number
3. netlify.com पर जाओ → Free account बनाओ
4. "Sites" → "Add new site" → "Deploy manually"
5. अपना folder drag करो (index.html + css/ + js/ + images/ + videos/)
6. ✅ Live URL मिल जाएगी (e.g., nexus-ai.netlify.app)
7. Custom domain later: Settings → Domain management
8. Google पर "nexus-ai domain buy" search करो (~₹500/year)
```

---

## QUICK REFERENCE: AI Studio Prompts

### हर नए session की शुरुआत में:
```
"I'm building the NEXUS AI website. Here's the context file 
[attach AGENTS.md]. Today's task is Day [X]: [section name].
Color palette: Orange #FF6B35, Navy #0A1929, Gold #FFD700.
Tech: Pure HTML+CSS+JS, GSAP, Vanilla Tilt. No frameworks."
```

### Services Section (Day 5):
```
"Build the Services section for NEXUS AI website.
6 service cards in 3x2 CSS Grid.
Services: AI Voice Agents, AI Automation, Website Development, 
AI Video Generation, AI Poster Design, Lead Generation.
Card design: Dark card bg #0D2137, orange border on hover,
icon placeholder (64x64px), Orbitron title, Inter description.
Add Vanilla Tilt: max:15, speed:400, scale:1.05, glare:true
Add GSAP stagger: cards fade in from bottom with 0.15s delay"
```

### Process Section (Day 6):
```
"Build the Process timeline section for NEXUS AI website.
4 steps: Discovery → Design → Build → Launch
Horizontal timeline with gradient line: #CC0000 → #FF6B35 → #FFD700
Each node: circle with glow pulse animation
Line draws from left to right on scroll (GSAP ScrollTrigger scrub)
Text fades in per step when node is activated
Mobile: vertical layout"
```

---
*Setup Guide v1.0 — Created June 30, 2026*

# 🐄 Niseko Takahashi Dairy Farm — MILK KOBO
### A fully AI-assisted website build using Claude, Lovable, ChatGPT, and ElevenLabs

🌐 **Live site:** [milkdairyniseko.com](https://milkdairyniseko.com)

---

## 📖 Project Overview

This project is a fully designed and deployed fake (but convincing) website for a real Japanese dairy farm — **Niseko Takahashi Dairy Farm MILK KOBO** — located in Niseko, Hokkaido, Japan.

The site includes:
- A **Home page** with hero carousel, café menu, and farm story
- An **About page** with real farm history and product photography
- A **Photoshoot Experience page** with package tiers, photographer profile, ElevenLabs voice message, and a booking form with confirmation
- A **Gallery page** with AI-generated and real photoshoot imagery

The entire site — from concept to live deployment — was built using a chain of AI tools with no traditional coding.

---

## 🧠 The AI Tool Stack

| Tool | Purpose |
|------|---------|
| **Claude (Anthropic)** | Strategy, prompting, iteration, copywriting |
| **Lovable** | Frontend build and deployment |
| **ChatGPT Image Gen 2.0** | Photoshoot gallery image generation |
| **Gemini** | Initial image generation (tested, superseded by ChatGPT) |
| **ElevenLabs** | AI voice generation for photographer audio message |

---

## 🔄 The Full Build Process

### Step 1 — Strategy & Brief (Claude)

Before opening any build tool, Claude was used to:
- Pressure test the concept and feasibility
- Define the site structure (4 pages, content hierarchy)
- Identify real farm details to incorporate for authenticity (address, phone, menu prices, features)
- Establish the design direction: **cream white + sage green, whimsical but grounded**

**Key prompt engineering insight:** Starting with a detailed, structured brief in Lovable produces dramatically better first outputs than iterating from a vague starting point. Claude helped construct a ~500 word Lovable prompt covering design system, color palette, typography, page-by-page content, form behavior, and confirmation message copy — all in one shot.

---

### Step 2 — Initial Build (Lovable)

The full brief was dropped into Lovable as a single prompt. First generation produced:
- All 4 pages with correct structure
- Working navigation
- Booking form with frontend confirmation state
- Illustrated placeholder images

**What worked immediately:** Layout, typography, copy, navigation, form logic
**What needed iteration:** Color palette (too pink), illustrated images, background tones

---

### Step 3 — Design Iteration (Claude → Lovable)

Claude was used as an iterative art director — reviewing screenshots, identifying specific issues, and writing precise Lovable prompts to fix them one step at a time.

**Iteration sequence:**
1. Remove pink gradient → cream background
2. Change accent color → sage green (#7C9A6E)
3. Remove floating decorative icons
4. Convert static hero image → auto-playing carousel
5. Fix carousel to fixed height (no layout shift)
6. Replace illustrated images with real photo placeholders
7. Add seasonal disclaimer copy
8. Rewrite AI-sounding copy to sound human

**Key learning:** Combining multiple small fixes into one prompt is more efficient than single-fix iterations. Lovable handles 3-4 simultaneous changes well.

---

### Step 4 — Real Photography (Sourced)

Real photos of the actual farm were sourced and added to:
- Hero carousel (soft serve ice cream with Mt. Yotei, storefront)
- About page (real Hokkaido dairy cows, farm product flatlay)
- Café menu section (cream puff display case, café window view)

This grounded the site in reality and significantly improved credibility versus illustrated placeholders.

---

### Step 5 — AI Image Generation: Gemini (Tested)

**Goal:** Generate realistic photoshoot couple images for the gallery

**Gemini prompt approach:**
```
A young Asian couple standing together in a vast sunflower field in Hokkaido, 
Japan, with a large snow-capped volcanic mountain (Mt. Yotei) visible in the 
background. Shot from behind, both with dark hair, the couple is looking toward 
the mountain together. Golden morning light, cinematic photography style, warm 
tones, realistic photo not illustration. Hay bales visible in the distance. 
Wide landscape shot. Canon 5D, f/2.8, golden hour.
```

**Result:** Over-saturated, overly perfect landscapes. Immediately recognizable as AI-generated. Not used in final site.

---

### Step 6 — AI Image Generation: ChatGPT Image Gen 2.0 (Primary)

**Why ChatGPT over Gemini:** Significantly better character consistency across multiple generations, more realistic photographic style, better handling of Asian facial features.

**Approach:** Used a real reference photo of a couple at the actual farm location, uploaded it to ChatGPT, and prompted for variations:

```
Using this photo as a style and setting reference, generate a series of 
realistic photoshoot images of this same Asian couple at the same Hokkaido 
farm location with Mt. Yotei in the background. Keep the same people, same 
clothing, same natural lighting style. Generate these different poses/scenes:
1. Couple sitting together on a large hay bale, smiling at camera
2. Couple walking hand in hand through a green pasture, shot from behind  
3. Couple holding soft serve ice cream cones up toward the mountain, laughing
4. Couple standing at a wooden farm fence with cows visible behind them
```

**Result:** 4 highly consistent, realistic-looking photoshoot images with the same couple across different settings. Character consistency was the key differentiator vs Gemini.

**For variety:** Generated 3 additional couple sets (different ages, different clothing) using the same reference photo approach to make the gallery look like a real business with multiple clients:
- Young couple in neutral tones (hay bale, yellow flower field)
- Middle-aged couple (walking in green field with cows and Mt. Yotei)
- Another young couple (casual streetwear, hay bale)

**Key prompt insight:** Specifying "completely different couple" and providing a reference photo for setting consistency produced the best results. Shot-from-behind angles are the most realistic for AI-generated couple photography.

---

### Step 7 — ElevenLabs Voice Integration

**Use case:** "A Message from Our Photographer" section on the Photoshoot page — a short audio message from the farm's in-house photographer, Arne Abad.

**Script:**
```
Moshi Moshi! My name is Arne. I have been photographing guests at MILK KOBO 
for many years now. Every season here is different! The snow on Mt. Yotei in 
spring, the sunflowers in summer, the golden fields in autumn. I love helping 
people capture the moments they will remember forever. When you visit, please 
don't be nervous. You will get a chance to walk around the farm while I set up 
for the perfect shot. I look forward to meeting you at the farm! Konnichiwa!
```

**ElevenLabs settings:**
- Platform: ElevenCreative → Text to Speech
- Model: Eleven Multilingual v2 (better than v3 for mixed-language scripts)
- Voice: Warm, conversational male voice
- Language Override: Auto (handles Japanese words naturally)
- Output: MP3 44.1kHz 128kbps

**Why Multilingual v2 over v3:** Better handling of Japanese words ("Moshi Moshi", "Konnichiwa") mixed into English speech. v3 emotion tags ([happy], [thoughtful]) had inconsistent results.

**Integration:** MP3 uploaded to Lovable, embedded as an HTML audio player styled in sage green to match site theme. Sits in a "Meet Our Photographer" card with circular photo, name, title, and bio.

---

### Step 8 — Deployment

- **Platform:** Lovable (built-in deployment)
- **Domain:** Purchased directly through Lovable's domain manager
- **Domain:** milkdairyniseko.com ($11.10/year)
- **SSL:** Included automatically
- **Time from purchase to live:** ~15 minutes

---

## 💡 Key Learnings

### On prompting Lovable
- **Front-load the brief.** A detailed first prompt saves 10+ iterations.
- **Be specific about hex colors.** "Sage green" is interpreted differently every time. Use `#7C9A6E`.
- **Fix one category at a time.** Group visual fixes separately from content fixes.
- **Screenshots + Claude = faster iteration.** Having Claude review screenshots and write the next prompt is significantly faster than iterating blind.

### On AI image generation
- **ChatGPT Image Gen 2.0 > Gemini** for realistic photography with consistent characters
- **Reference photos are essential** for location and character consistency
- **Shot from behind** produces the most realistic AI couple photography — avoids uncanny valley face issues
- **Age diversity in gallery** makes it feel like a real business

### On ElevenLabs
- **Multilingual v2** handles code-switching (English + Japanese) better than v3
- **Short scripts (25-35 seconds)** work best for embedded website audio
- **Conversational voice labels** ("warm", "friendly") produce more natural results than "narrative" voices
- **Language Override: Auto** is the right setting for mixed-language scripts

### On the overall workflow
- Total build time: ~4 hours
- No code written manually
- Tools used: Claude → Lovable → real photos → ChatGPT → ElevenLabs → Lovable → Namecheap/Lovable domain

---

## 🗂️ Site Structure

```
milkdairyniseko.com
├── Home
│   ├── Hero (auto-carousel, 4 images)
│   ├── Farm story section
│   ├── Café menu (side-by-side carousel + menu items)
│   ├── Feature badges
│   ├── "Come for the ice cream" banner
│   └── Footer (address, hours, phone)
├── About
│   ├── Our Story hero
│   ├── The Farm section (real cow photo + copy)
│   ├── MILK KOBO Café section (product flatlay + copy)
│   └── What makes Niseko special (3-column seasonal cards)
├── Photoshoot
│   ├── Hero (couple photo, seasonal disclaimer)
│   ├── Experience description
│   ├── Package tiers (Pasture Basic / Yotei Premium / Full Day)
│   ├── Photographer profile + ElevenLabs audio
│   └── Booking form + confirmation state
└── Gallery
    └── Masonry grid (8 AI-generated photoshoot images)
```

---

## 🛠️ Tech Stack

- **Frontend:** React + TanStack (generated by Lovable)
- **Styling:** Tailwind CSS
- **Deployment:** Lovable
- **Domain:** milkdairyniseko.com
- **Audio:** ElevenLabs MP3, embedded HTML audio player

---

## 📸 Image Credits

- Real farm photography: sourced from public farm/tourism photography of Niseko Takahashi Dairy Farm
- Couple photoshoot images: AI-generated using ChatGPT Image Generation 2.0
- Photoshoot hero image: sourced reference photo of Hokkaido shibazakura fields

---

*Built as a portfolio project demonstrating end-to-end AI-assisted web development and creative production.*

---

## 🌏 v2 — Bilingual Update

### What changed
Converted the entire site from English-default to **Japanese-default with a JP | EN language toggle**.

### Why
A real Japanese farm website would default to Japanese. Adding bilingual support makes the site significantly more convincing and mirrors how real Hokkaido tourism and farm websites present to international visitors.

### Implementation
- All copy translated to Japanese via Lovable prompt
- JP | EN toggle added to navigation
- Toggle positioned **next to the logo** (not in the hamburger menu) for persistent visibility on mobile — a deliberate UX decision since mobile hamburger menus hide secondary controls
- Proper nouns kept consistent across both languages (MILK KOBO, Mt. Yotei, Arne Abad, package names)

### Key prompt insight
Specifying toggle placement explicitly ("next to the logo, never hidden in the hamburger menu") was necessary — Lovable's default behavior puts navigation items inside the mobile menu, which would have buried the language toggle on the most likely device she'd be using.

### Lovable prompt used
```
Translate all website copy into Japanese. Add a language toggle button "JP | EN" 
in the top left navigation bar, positioned directly next to the MILK KOBO logo. 
It should always be visible on both desktop and mobile — never hidden inside the 
hamburger menu. Default language on page load is Japanese. Keep all proper nouns 
(MILK KOBO, Mt. Yotei, MILK KOBO Full Day, Yotei Premium, Pasture Basic, Arne Abad) 
in their original form in both languages.
```

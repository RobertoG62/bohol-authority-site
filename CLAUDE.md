# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **high-end authority tourism website for Bohol, Philippines** — not a generic travel blog. The site positions Bohol as a "Tropical Luxury" and "Eco-Wellness" destination, targeting affluent, environmentally-conscious travelers. The brand narrative is **"Quiet Luxury"** — think tropical sanctuary, not attraction catalog.

## Architecture & Tech Stack

- **Framework**: Single-page static site (HTML + Tailwind CSS + vanilla JS). Future migration path to Next.js is planned.
- **Styling**: Tailwind CSS via CDN. No build step currently required.
- **Icons**: Font Awesome 6.x (CDN). No SVG graphics or Mermaid JS.
- **Charts**: Chart.js for data visualizations (transport costs, weather/tourist season).
- **Fonts**: Heebo (body), Rubik/Oswald (display headings) via Google Fonts.
- **Deployment target**: Vercel or GitHub Pages.

## Design System — The "Bohol Palette"

Two reference HTML files establish the visual language. All new components must use these tokens:

### Primary palette (from Bohol.html):
| Token | Hex | Usage |
|---|---|---|
| `bohol-sand` | `#F3F0E7` | Backgrounds, cards |
| `bohol-teal` | `#2A9D8F` | Primary accent, CTAs, active states |
| `bohol-deep-blue` | `#264653` | Nav, headings, dark sections |
| `bohol-orange` | `#E9C46A` | Highlights, badges |
| `bohol-sunset` | `#F4A261` | Secondary accent |
| `bohol-earth` | `#A68A64` | Subtle elements, scrollbar |

### Secondary palette (from Infographic HTML):
| Token | Hex |
|---|---|
| `brand-dark` | `#1D3557` |
| `brand-teal` | `#457B9D` |
| `brand-light` | `#A8DADC` |
| `brand-sand` | `#F1FAEE` |
| `brand-accent` | `#E63946` |

When in doubt, prefer the primary palette. The secondary palette is for infographic-style sections.

## Content Bible

**ALL text content, prices, routes, and logistics data** must come from the Hebrew research document (`מחקר מעמיק לאתר תיירות בוהול.md`). Do not invent prices, distances, or travel times. Key data points:

- **Ferry prices**: OceanJet Cebu-Tagbilaran 500-1,200 PHP by class
- **Private van**: 3,500-4,000 PHP/day (8 hours)
- **Airport taxi to Alona**: 800-1,000 PHP
- **Scooter rental**: 350-500 PHP/day
- **Chocolate Hills entry**: 100 PHP; Tarsier Sanctuary: 150 PHP; Loboc River Cruise: 850-1,000 PHP
- **3-day itinerary budget**: ~8,000-12,000 PHP/person (excl. flights)
- **Best season**: January-March (dry, dolphins visible March-June)

### Geographic structure (content segments into 3 "circuits"):
1. **Panglao Island** — beaches, resorts, diving (Alona, Dumaluan, Doljo)
2. **Mainland/Countryside** — Chocolate Hills, Tarsier Sanctuary, Loboc River, Danao Adventure Park
3. **Eastern Frontier (Anda/Candijay)** — cave pools, rice terraces, Can-Umantad Falls

### Accommodation tiers by persona:
- **Luxury**: Amorita Resort, Henann Resort
- **Family**: Bohol Beach Club (Dumaluan), South Palms
- **Budget**: Green Space Inn (~1,300 PHP), Bohemian Lofts
- **Anda boutique**: Amun Ini, Three Little Birds

## Strategic Vision (from PDF)

The owner's strategic intent includes these planned features (implement when requested):
- **AI Trip Planner**: Builds personalized itineraries by dates/budget (3-day and 7-day templates exist in the content bible)
- **VR Tours**: 360-degree virtual tours of key attractions
- **Multi-language**: Hebrew (RTL), English (LTR), Korean — Hebrew is the initial language
- **Booking.com / Klook integration**: Affiliate commission model (10-20%)
- **Newsletter**: Weekly tips, retention target 15%
- **TripAdvisor reviews integration**
- **Interactive map**: 20+ attraction pins with video/360/tips
- **SEO targets**: "Bohol Chocolate Hills tours", "Tarsier sanctuary Bohol" (100K+ searches/month)

## RTL Support

The site's primary language is **Hebrew (RTL)**. All HTML must use `dir="rtl"` and `lang="he"`. When building components:
- Use logical CSS properties (`margin-inline-start` over `margin-left`) or Tailwind RTL utilities
- Navigation links use `space-x-reverse` for RTL spacing
- Border accents use `border-r-*` (which appears on the right in RTL = visual left)

## Key Conventions

- The site brands itself as **"BoholInsider"** (logo: `Bohol` + `Insider` in teal)
- Ethical tourism emphasis: always direct users to the **official Tarsier Sanctuary in Corella**, warn against roadside cages
- Promote **UBI Seal of Excellence** (Bohol's 2025 sustainable tourism certification) as a trust signal
- Price transparency is a core differentiator — always show official 2025 prices
- Content tone: authoritative expert, not casual blogger. "Tropical sanctuary" language.
- Environmental fees are common at most sites — remind visitors to carry small bills (20/50/100 PHP)
- Anda has limited ATMs — always warn about cash requirements for eastern routes

## Reference Files

| File | Purpose |
|---|---|
| `מחקר מעמיק לאתר תיירות בוהול.md` | **Content Bible** — all text, prices, routes, logistics |
| `Bohol.html` | **Design reference** — primary palette, component patterns, JS interaction patterns |
| `Bohol_Tourism_Infographi.HTML` | **Design reference** — secondary palette, infographic/data-viz style |
| `הכוונה שלי...pdf` | **Strategic vision** — AI planner, VR, monetization, SEO strategy |

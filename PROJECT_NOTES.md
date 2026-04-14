# DRYCOR RESTORE — Homepage Redesign Project Notes

> Last updated: April 14, 2026  
> Prepared by: AI Agent (Cursor)  
> Session chat reference: [DRYCOR Homepage Redesign Session](e065c95)

---

## Project Overview

**Client:** DRYCOR RESTORE (`drycor.com`) — full-service disaster restoration company based in Thonotosassa, FL (Tampa Bay area).  
**Commercial division:** DRYCORXL (`drycorxl.com`) — nationwide large-loss and commercial recovery.  
**Project type:** High-fidelity single-file HTML homepage mockup built from scratch for client review before development handoff.

### Live URLs
| Resource | URL |
|---|---|
| **Live Mockup** | https://jamesl6.github.io/drycor-redesign/ |
| **GitHub Repo** | https://github.com/JamesL6/drycor-redesign |
| **Client Site** | https://www.drycor.com/ |
| **Commercial Site** | https://www.drycorxl.com/ |

### Local Paths
| Resource | Path |
|---|---|
| Project root | `~/Projects/drycor-redesign/` |
| Main file | `~/Projects/drycor-redesign/index.html` |
| Client brief | `/Users/jameslarosa/Desktop/DRYCOR_Site_Brief.docx` |
| Client images (drive) | `/Users/jameslarosa/Desktop/drive-download-20260414T171113Z-3-001/` |

### To push updates
```bash
cd ~/Projects/drycor-redesign
git add -A && git commit -m "update: [description]" && git push
```
GitHub Pages rebuilds in ~45 seconds after each push.

---

## Key Client Info

| Detail | Value |
|---|---|
| **Residential phone** | (866) 395-6625 |
| **Commercial phone (DRYCORXL)** | (800) 572-6110 |
| **Tracking number (confirmed)** | 813-820-6170 *(toll-free decision pending — see notes)* |
| **Address** | 10798 Florence Ave, Thonotosassa, FL 33592 |
| **Service area** | Hillsborough, Pasco & Polk Counties, FL |
| **Founded** | 2005 (2004 per some materials) |
| **Experience** | 50+ years combined (senior leadership team) |
| **Ownership** | Disabled Veteran Owned & Operated |
| **Licenses** | CBC1253966 \| MRSR4758 |
| **Certifications** | IICRC, WRT, ASD, AMRT, EPA, BBB A+, OSHA |

### Key Contacts
- **Ashley** — primary content/compliance contact (provides FAQ copy, image uploads, approved language)
- **Robert** — owner/CEO (SEO strategy, tracking numbers, partner pages)
- **Chesney** — RGP tracking platform (toll-free number decision)
- **John** — confirmed AI/GEO optimisation scope

---

## Design System

### Colors
```css
--blue:        #006393;   /* primary brand blue */
--blue-dark:   #004d73;
--blue-deeper: #00304a;   /* footer, hero overlay */
--blue-mid:    #005580;
--red:         #E4002B;   /* emergency / CTA */
--red-hover:   #b8001e;
--teal:        #68ccd1;   /* accent */
--teal-light:  #e6f7f8;
--text:        #1a2b3c;
--muted:       #5a6e84;
--border:      #d4e2f0;
--bg:          #f4f8fd;
--bg-alt:      #eef3fa;
--white:       #ffffff;
--gold:        #f5a623;   /* veteran badge accent */
```

### Typography
- **Headings:** Montserrat 900, uppercase, tight tracking — from Google Fonts
- **Body:** Inter 400/500/600 — from Google Fonts

### Tech Stack
- Pure single-file HTML (no framework, no build step)
- Leaflet.js 1.9.4 (CDN) for interactive maps
- CartoDB Positron tiles (basemap)
- Census TIGER API — county outlines (free, no key required)
- PublicaMundi GitHub GeoJSON — US state outlines
- GitHub Pages hosting (master branch, `/` path)

---

## File Structure

```
drycor-redesign/
├── index.html                        ← entire site (HTML + CSS + JS)
├── images/
│   ├── logo.png                      ← symbol-only logo (black bg — unused)
│   ├── logo-full.png                 ← full vertical logo (black bg — unused)
│   ├── logo-full-transparent.png     ← full vertical logo (bg removed) ← ACTIVE
│   ├── hero-bg.jpg                   ← hero background from drycorxl.com
│   └── services/
│       ├── turnkey-restoration.jpg   ← Fire Damage Kitchen After
│       ├── large-loss.jpg            ← Flood Catastrophe
│       ├── reconstruction.jpg        ← Tornado Wind Damage After
│       ├── building-consulting.jpg   ← Fire Damage Before
│       ├── emergency-mitigation.jpg  ← Water Extraction
│       ├── dehumidification.jpg      ← Mold Damage
│       ├── build-back.jpg            ← Fire Damage 2 After
│       ├── emergency-stabilization.jpg ← Structural Damage Hurricane Wind
│       ├── contents.jpg              ← Fire Damage After (bedroom)
│       └── mold.jpg                  ← Mold Cleaning (techs in hazmat)
└── PROJECT_NOTES.md                  ← this file
```

### Logo Notes
- `logo-full-transparent.png` was created by stripping the black background from the original PNG using Python/Pillow (threshold: pixels where R+G+B < 80 set to transparent)
- **Header:** transparent PNG, no blend mode, `flex-shrink: 0` on anchor prevents squeezing
- **Footer:** transparent PNG with `filter: brightness(0) invert(1)` → renders as white against dark footer

---

## Page Sections (All 17)

| # | Section | Notes |
|---|---|---|
| 1 | Emergency Bar | Red top strip, pulsing dot, phone link |
| 2 | Sticky Header | Logo + mega-menu nav + phone + "Request a Callback" (red) |
| 3 | Hero | Full-viewport, disaster image bg, left copy + right team image |
| 4 | Stats Bar | 4 dark tiles: IICRC / 5K+ Properties / 4.9 Stars / 50+ Years |
| 5 | Trust Badges | IICRC / Google / BBB A+ / EPA / Licensed / TPA-Aligned |
| 6 | Core Services | 10 services in unified 4-col grid with client photos |
| 7 | Process | 4-step dark section |
| 8 | Commercial/DRYCORXL | Dark section, 12 property pills, capabilities |
| 9 | Mid-Page CTA | Red urgency strip, phone number |
| 10 | Why Choose Us | Stats strip + 3-col feature card grid |
| 11 | Insurance Logos | 12 carrier tiles in brand colors |
| 12 | Certifications | Single horizontal scrolling strip |
| 13 | Google Reviews | 4.9 score, 3 review cards |
| 14 | Service Areas | Tabbed: Residential (Tampa Bay map) + Commercial (US map) |
| 15 | FAQ | Sticky CTA + accordion (placeholders pending Ashley) |
| 16 | Final CTA Banner | Dark blue, "Contact Our Team" |
| 17 | Footer | 4-col grid + mobile sticky call bar |

---

## Navigation Structure (Final)

```
Home
│
About Us ▾
├── [Company]
│   ├── About Us        → /about
│   ├── Reviews         → /reviews
│   ├── Blog & Resources → /blog
│   └── Careers         → /careers
└── [Partnerships]
    ├── Become a Partner → /become-a-partner
    ├── Property Managers → /partners/property-manager
    ├── Insurance Carriers → /partners/insurance-carrier
    ├── Plumbers          → /partners/plumber
    ├── HVAC Contractors  → /partners/hvac
    └── Tree Removal      → /partners/tree-removal
│
Residential Services ▾
├── [Water Damage]
│   ├── Overview         → /water-damage-restoration
│   ├── Water Extraction → /water-damage-restoration/water-extraction
│   ├── Water Mitigation → /water-damage-restoration/water-mitigation
│   ├── Dehumidification → /water-damage-restoration/dehumidification
│   ├── Flood Damage     → /water-damage-restoration/flood-damage-restoration
│   ├── Leak Detection   → /water-damage-restoration/leak-detection
│   └── Thermal Imaging  → /water-damage-restoration/thermal-imaging
├── [Fire & Smoke]
│   ├── Overview         → /fire-damage-restoration
│   └── Smoke & Soot     → /fire-damage-restoration/fire-damage-and-smoke-cleanup
├── [Mold]
│   ├── Overview         → /mold-remediation
│   ├── Mold Inspection  → /mold-remediation134fd0c2/mold-inspection
│   └── Mold Removal     → /mold-remediation134fd0c2/mold-removal
└── [More Services]
    ├── Storm & Catastrophe    → /storm-damage
    ├── Reconstruction         → /reconstruction
    ├── Contents Restoration   → /contents-restoration
    ├── Emergency Services     → /emergency-services
    ├── Emergency Stabilization → /emergency-stabilization
    ├── Building Consulting    → /loss-coordination
    └── Large-Scale Drying     → /dehumidification
│
Commercial Services ▾ [XL]
├── [DRYCORXL]
│   ├── Home              → https://www.drycorxl.com
│   ├── About             → https://www.drycorxl.com/about
│   └── All Services      → https://www.drycorxl.com/restoration
├── [Primary Services]
│   ├── Water & Flood     → https://www.drycorxl.com/water-and-flood-damage
│   ├── Fire & Smoke      → https://www.drycorxl.com/fire-and-smoke-damage
│   └── Environmental/Mold → https://www.drycorxl.com/environmental-and-mold-damage
└── [More Services] (all → /restoration)
    ├── Storm & Catastrophe
    ├── Loss Coordination & Mgmt
    ├── Sewage & Hazmat Cleanup
    ├── Contents Services
    └── Structural Stabilization
│
Contact Us → /contact
```

**Header right (desktop only):**
- Phone: `(866) 395-6625` with "Available 24/7" label
- Button: "Request a Callback" (red, `btn-red`) → `/contact`

**Mobile:** Nav + phone hidden; fixed red bottom bar: "Tap to Call — (866) 395-6625"

---

## Hero Section (Final State)

| Element | Value |
|---|---|
| **Headline** | `Full-Service Disaster Recovery & Construction Firm.` |
| **Sub copy** | "Turnkey loss response with integrated construction and roofing services — supporting stabilization through full reconstruction for commercial and residential properties." |
| **Trust pills** | 2×2 equal grid: Contact Support 24/7 / Licensed, Certified & Turnkey / TPA-Aligned Vendor / Commercial & Residential Losses |
| **CTA 1 (red)** | Desktop: `(866) 395-6625` + "Call for 24/7 Service" — Mobile: "Tap to Call" |
| **CTA 2 (outline)** | "Large Loss & Commercial Inquiries" → `https://www.drycor.com/xl` |
| **Right column** | DRYCOR Disaster Team On-Site image from CDN + pulsing teal dot overlay |
| **Background** | `images/hero-bg.jpg` — extracted from drycorxl.com hero (disaster scene, workers at burning structure at night) |

---

## Services Section (Final State)

All 10 core services from drycor.com in one unified 4-column grid. All cards identical size.

| # | Service | Image File |
|---|---|---|
| 1 | Turnkey Restoration & Reconstruction | `turnkey-restoration.jpg` (kitchen after) |
| 2 | Large-Loss & Catastrophic Recovery | `large-loss.jpg` (flood catastrophe) |
| 3 | Commercial & Residential Reconstruction | `reconstruction.jpg` (tornado after exterior) |
| 4 | Building Consulting & Loss Coordination | `building-consulting.jpg` (fire damage before) |
| 5 | Emergency Mitigation & Stabilization | `emergency-mitigation.jpg` (water extraction) |
| 6 | Large-Scale Dehumidification & Climate Control | `dehumidification.jpg` (mold damage techs) |
| 7 | Construction & Build-Back | `build-back.jpg` (fire damage 2 after kitchen) |
| 8 | Emergency Stabilization & Temporary Repairs | `emergency-stabilization.jpg` (hurricane wind ceiling) |
| 9 | Contents & Asset Protection Services | `contents.jpg` (fire damage after bedroom) |
| 10 | Environmental & Mold Services | `mold.jpg` (mold cleaning hazmat) |

---

## Service Areas — Leaflet Maps

### Residential Tab (default)
- **Library:** Leaflet.js 1.9.4
- **Tiles:** CartoDB Positron (`light_all`)
- **Data:** Census TIGER Web Services API — `GEOID IN ('12057','12101','12105')`
  - Hillsborough County: `#006393` (blue)
  - Pasco County: `#2a7fa8` (mid-blue)
  - Polk County: `#68ccd1` (teal)
- **HQ Marker:** pulsing red dot at `[28.068, -82.256]` (Thonotosassa)
- **County tabs:** Hillsborough / Pasco / Polk
- **City accordion:** 30+ cities, each with `<details>` dropdown showing service page links per city

### Commercial Tab (lazy-loaded)
- **Data:** PublicaMundi GitHub — `https://raw.githubusercontent.com/PublicaMundi/MappingAPI/master/data/geojson/us-states.json`
- All 50 states filled brand blue, hover tooltip shows state name
- DRYCORXL HQ marker at Tampa
- Stats tiles: 50 States / 24/7 Emergency Response / Large-Loss Specialists / TPA Aligned
- CTA strip with DRYCORXL description + "Request Commercial Service" → `/contact`
- **Performance:** US map initializes lazily (`usMapInitialized` flag) — only loads when commercial tab is first clicked

---

## Commercial Section (Homepage)

Dark full-width section between Process and Mid-Page CTA.

**Left column:** DRYCORXL branding (logo treatment), headline, body copy, 6 capability bullets, "Request Commercial Service" → `/contact`

**Right column:** 12 property type pills (all merged, no group labels):
- Commercial Office Buildings, Multifamily & Apartments, Hospitality & Hotels, Healthcare Facilities, Industrial & Manufacturing, Retail & Mixed-Use, Educational Institutions, Municipal & Government, Senior Living Communities, Property Management Firms, Insurance Carriers & TPAs, Asset Managers & Investment Groups

**Note:** User chose to keep commercial content combined with residential on this homepage, overriding the brief's instruction to keep drycor.com purely residential. External links to drycorxl.com have been removed from this section.

---

## Why Choose Us Section (Final Layout)

**Three-zone layout:**

1. **Centered header** — "Trusted by Property Owners & Contractors" + intro copy
2. **Dark stats strip (4 tiles):** Available 24/7 / 5,000+ Properties Restored / 4.9 Google Rating / 50+ Years Combined Exp.
3. **3-col feature card grid (6 cards, white bg):**
   - IICRC Certified Technicians
   - Thorough Documentation *(insurance language cleaned per brief)*
   - Turnkey — One Vendor, All Phases
   - Commercial & Large-Loss Expertise
   - Talk to a Live Person
   - 🇺🇸 Disabled Veteran Owned *(gold border accent)*

---

## Logo Implementation

### Problem
Both logo PNGs provided had **black backgrounds** (not transparent). Standard CSS blend modes:
- `mix-blend-mode: multiply` → black stays black on white (doesn't work for header)
- `mix-blend-mode: screen` → black becomes transparent on dark backgrounds (works for footer)

### Solution
Used Python/Pillow to strip the black background:
```python
from PIL import Image
import numpy as np

img = Image.open('logo-full.png').convert('RGBA')
data = np.array(img)
r, g, b, a = data[:,:,0].astype(int), data[:,:,1].astype(int), data[:,:,2].astype(int), data[:,:,3]
black_mask = (r + g + b) < 80   # threshold for near-black
data[black_mask, 3] = 0          # set to transparent
Image.fromarray(data.astype(np.uint8)).save('logo-full-transparent.png')
```

### Usage
```css
/* Header — transparent PNG, colors show on white */
.header__logo img {
  height: 62px;
  width: auto;
  flex-shrink: 0;           /* prevents squishing */
}
.header__logo {
  flex-shrink: 0;           /* prevents nav from squeezing logo */
}
.header__nav {
  flex: 1;
  justify-content: center;  /* nav fills middle, logo left, buttons right */
}

/* Footer — invert to white on dark background */
.footer__brand-logo {
  height: 80px;
  filter: brightness(0) invert(1);
}
```

---

## Client Brief Compliance

### Source
`/Users/jameslarosa/Desktop/DRYCOR_Site_Brief.docx`  
Prepared by: Restoration Growth Partners  
From: Client call Feb 18, 2026 (Ashley & Robert)

### ✅ All 16 Red-Category Items Fixed

| # | Issue | Fix Applied |
|---|---|---|
| 1 | Meta title/description had "60 min" | Updated — removed timeframe claim |
| 2 | Hero headline "Tampa's #1 Disaster Restoration Company" | → `"Full-Service Disaster Recovery and Construction Firm."` |
| 3 | Stats bar "60 min On-Site Response" | → `IICRC Certified Firm` |
| 4 | Stats bar "20+ Years of Experience" | → `50+ Years Combined Exp.` |
| 5 | Process step 4 "for your claim" | → "for your records" |
| 6 | Mid-page CTA "60 minutes or less" | Removed timeframe entirely |
| 7 | Service areas "within 60 minutes" | Removed timeframe |
| 8 | Map badge "60-Min Response" | → "Service Area" |
| 9 | Insurance section "maximum coverage with minimum stress" | → documentation-only language |
| 10 | Insurance footer note "all insurance companies" | Softened / rewritten |
| 11 | All 6 FAQ answers (liability/insurance language) | → Placeholders: *"Answer coming soon — content pending review"* |
| 12 | Footer "Insurance Claims" nav link | Removed → replaced with "Become a Partner" |
| 13 | Footer "24/7/365 — Always Open" | → `"Available 24/7"` |
| 14 | Review #1 "worked directly with our insurance adjuster" + "45 minutes" | Rewritten — both removed |
| 15 | Final CTA "Request Online Assessment" | → `"Contact Our Team"` → `/contact` |
| 16 | "Trusted by Insurance Professionals" heading | → `"Trusted by Property Owners & Contractors"` |

### 🟡 Pending — Awaiting Client Input

| Item | Status | Owner |
|---|---|---|
| All 6 FAQ answers | Ashley providing verbatim — hold placeholders | Ashley |
| Insurance language replacement copy | Ashley providing for all removed sections | Ashley |
| Safety advice replacement copy | Ashley providing | Ashley |
| Hero background image (residential) | Brief says current XL scene should be residential; user chose to keep for now | Ashley (Google Drive) |
| Tracking number | 813-820-6170 confirmed. Toll-free (800/888/866) or vanity (844-DRYCOR-X) pending | Chesney @ RGP |

### ⚪ Separate Items (Not Homepage Blocking)

| Item | Notes |
|---|---|
| Partner pages (5) | Links in nav exist, actual pages not built yet |
| Schema markup / AI-GEO | Robert requested ChatGPT/Grok/Gemini visibility. John confirmed in scope — not blocking launch |
| Confidential QR pages | Separate unlisted URLs for referral fee details — NOT linked from nav |

### ⚠️ Intentional Override
User chose to **combine commercial + residential on this homepage**, opposing the brief's SEO strategy recommendation. The brief states drycor.com should be purely residential to protect SEO separation from drycorxl.com. This is a known conscious decision.

---

## Partner Pages — Brief Requirements

From brief section 7 — Robert confirmed these must be publicly accessible:

| Page | URL slug | Notes |
|---|---|---|
| Property Manager referral | `/partners/property-manager` | Vertical-specific language only |
| Insurance Carrier partner | `/partners/insurance-carrier` | No referral fee details |
| Plumber partner | `/partners/plumber` | Already exists on current site — needs update |
| HVAC partner | `/partners/hvac` | New page needed |
| Tree Removal partner | `/partners/tree-removal` | New page needed |

**Two-tier structure:**
- **Public pages** (in nav): General partnership overview per vertical. No referral fees, no cross-vertical info.
- **Confidential QR pages** (unlisted): Detailed referral terms, accessed only via QR codes on print materials. Never linked from main nav.

---

## Disabled Veteran Owned — Placement

Appears in 4 locations:
1. Hero trust pill (2×2 grid, styled with slight white glow)
2. Hero sub copy — "disabled veteran-owned firm" in body text
3. Why Choose Us feature card — gold left border, dedicated card
4. Footer cert strip — `🇺🇸 Veteran Owned` in gold tint badge

---

## Next Steps (Recommended)

### Immediate / No Blockers
- [ ] Insert Ashley's FAQ answers verbatim when received
- [ ] Insert Ashley's insurance/safety replacement copy when received
- [ ] Mobile QA pass on all sections
- [ ] Confirm tracking number with Chesney — update all phone instances if changing from 866 to toll-free

### Short Term
- [ ] Build Water Damage Restoration page (primary residential service)
- [ ] Build Fire & Smoke Damage page
- [ ] Build Mold Remediation page
- [ ] Build 5 partner pages (public-facing, general language per vertical)
- [ ] Replace hero background with residential image from Ashley's Google Drive when provided

### Medium Term
- [ ] Add schema markup (LocalBusiness, Service, FAQPage, Review structured data) for AI/GEO visibility
- [ ] Build remaining service pages (Storm, Reconstruction, Contents, Emergency, Building Consulting)
- [ ] Build About Us page
- [ ] Build Blog/Resources section
- [ ] Build Careers page
- [ ] Build Contact page (with the form that was removed from hero)

### Before Launch
- [ ] All images from Ashley's Google Drive mapped and confirmed
- [ ] All FAQ content inserted verbatim (no editing)
- [ ] All insurance/safety placeholder sections filled with Ashley's compliant copy
- [ ] Phone number finalized (tracking number confirmed routing)
- [ ] Legal review of any remaining copy (especially FAQ answers)
- [ ] Review page flagged service pages for insurance/coverage language audit

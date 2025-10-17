# Design Guidelines for Friute-cap.com

## Design Approach: Reference-Based E-commerce

**Primary References:** headgearbd.com (provided), Shopify stores, streetwear e-commerce (Supreme, Kith), athletic cap brands (New Era)

**Design Philosophy:** Modern streetwear aesthetic with bold product showcases, clear categorization, and energetic promotional elements. The design balances youthful energy with professional e-commerce functionality.

---

## Core Design Elements

### A. Color Palette

**Light Mode:**
- Primary Brand: 210 100% 45% (vibrant blue - energetic, trustworthy)
- Secondary Accent: 15 90% 55% (coral/orange - for CTAs and flash sales)
- Neutral Base: 220 10% 98% (off-white background)
- Text Primary: 220 15% 20% (near-black)
- Text Secondary: 220 10% 50% (gray)
- Success/Flash Sale: 145 65% 45% (green for countdown/deals)

**Dark Mode:**
- Background: 220 15% 12% (dark charcoal)
- Surface: 220 12% 18% (elevated surfaces)
- Primary Brand: 210 95% 55% (brighter blue for dark mode)
- Text: 220 10% 95% (off-white)

### B. Typography

**Font Stack:**
- Primary: 'Inter' or 'DM Sans' (Google Fonts) - clean, modern sans-serif
- Headings: Weight 700 (Bold) for impact
- Body: Weight 400 (Regular), Weight 500 (Medium) for emphasis
- Buttons/CTAs: Weight 600 (Semibold)

**Hierarchy:**
- Hero Headline: 3.5rem (56px) desktop, 2.5rem mobile
- Section Headers: 2rem (32px) desktop, 1.75rem mobile
- Product Titles: 1.125rem (18px)
- Body Text: 1rem (16px)
- Small Text: 0.875rem (14px)

### C. Layout System

**Spacing Primitives:** Use Tailwind units of 4, 6, 8, 12, 16, 20, 24 for consistent rhythm
- Section padding: py-16 md:py-24
- Component spacing: gap-6 or gap-8
- Card padding: p-4 or p-6
- Container max-width: max-w-7xl

**Grid System:**
- Product Grids: 2 columns mobile, 3 columns tablet, 4-5 columns desktop
- Category Cards: 2 columns mobile, 3-4 columns desktop
- Hero/Banner: Full-width with contained content

---

## Component Library

### Navigation Header
- Sticky navigation with blur backdrop
- Logo left, centered menu items, cart/search right
- Mobile: Hamburger menu with slide-in drawer
- Announcement bar above header: "Flash Sale 🔥" or promotional text
- Search icon triggers overlay search modal

### Hero Section
**Large hero carousel/slider with:**
- Full-width background images showing caps in lifestyle contexts
- 3-5 rotating slides with auto-play
- Overlay gradient (dark bottom fade) for text readability
- Large headline + subtext + CTA button
- Slide indicators (dots) at bottom center
- Arrow navigation on desktop

**Images for Hero:**
- High-quality lifestyle shots: people wearing caps in urban/street settings
- Product showcase: close-ups of premium cap details
- Collection banners: seasonal or limited edition announcements
- Minimum 1920x800px, optimized for web

### Flash Sale Section
- Prominent badge: "⚡ Flash Sale" with countdown timer
- 4-6 product cards in horizontal scroll (mobile) or grid (desktop)
- Each card: Image, quick hover zoom, price (original + sale), "Quick View" button
- Background: subtle gradient or colored surface to stand out

### Product Cards
**Standard card structure:**
- Square product image (1:1 ratio) with hover zoom effect
- "NEW" or "LIMITED" badge on top-left corner
- Product name below image
- Price (bold) with compare-at price if on sale
- Heart icon (wishlist) on top-right corner
- Quick add to cart button on hover (desktop)

### Collection Category Cards
- Large image cards (landscape or square)
- Category name overlaid on image
- Subtle hover lift effect (transform: translateY(-4px))
- 2-4 columns depending on screen size

### Section Headers
- Left-aligned or centered depending on section
- Include subtitle/description text below main header
- "View All →" link on right side for product sections

### Footer
- 4-column layout (desktop): About, Collections, Customer Service, Social
- Newsletter signup with email input + subscribe button
- Social media icons (Facebook, Instagram, etc.)
- Payment method icons
- Copyright and policy links at bottom

---

## Key Sections Structure

1. **Announcement Bar** - Promotional message
2. **Navigation** - Logo, menu, cart, search
3. **Hero Slider** - 3-5 slides with CTAs
4. **Flash Sale** - Countdown + product grid
5. **New Arrivals** - Latest products showcase
6. **Limited Edition** - Exclusive collection highlight
7. **Top Selling** - Best sellers grid
8. **Shop by Collection** - Category cards (Baseball, Trucker, Bucket Hat, etc.)
9. **Featured Collections** - 2-3 curated collection banners
10. **Newsletter** - Email signup CTA
11. **Footer** - Navigation and info

---

## Interaction Design

**Animations:** Minimal and purposeful
- Product card hover: subtle scale (1.05) and shadow increase
- Button hover: slight background darkening
- Page transitions: smooth fade
- Carousel: slide transition with 5s auto-play

**Mobile Considerations:**
- Touch-friendly tap targets (min 44x44px)
- Swipeable carousels
- Hamburger menu with smooth slide animation
- Sticky "Add to Cart" bar on product pages

**Performance:**
- Lazy load images below fold
- Optimize hero images (WebP format)
- CDN delivery for assets

---

## Visual Enhancements

- Subtle shadow on elevated cards: shadow-md
- Rounded corners: rounded-lg for cards, rounded-md for buttons
- Border accents: Use primary color for active states
- Product badges: pill-shaped with contrasting colors
- Smooth transitions: transition-all duration-300

**Imagery Guidelines:**
- Hero: Lifestyle and action shots
- Products: Clean white background, consistent lighting
- Categories: Styled flat lays or lifestyle context
- Banners: Bold graphics with product focus

This design creates a modern, vibrant e-commerce experience that showcases caps effectively while maintaining professional credibility and ease of navigation.
---
name: Techno-Nature Modular Systems
colors:
  surface: '#f8f9fa'
  surface-dim: '#d9dadb'
  surface-bright: '#f8f9fa'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f3f4f5'
  surface-container: '#edeeef'
  surface-container-high: '#e7e8e9'
  surface-container-highest: '#e1e3e4'
  on-surface: '#191c1d'
  on-surface-variant: '#43474a'
  inverse-surface: '#2e3132'
  inverse-on-surface: '#f0f1f2'
  outline: '#73787b'
  outline-variant: '#c3c7ca'
  surface-tint: '#516169'
  primary: '#192830'
  on-primary: '#ffffff'
  primary-container: '#2f3e46'
  on-primary-container: '#99a9b2'
  inverse-primary: '#b9c9d3'
  secondary: '#496366'
  on-secondary: '#ffffff'
  secondary-container: '#cbe8eb'
  on-secondary-container: '#4f696c'
  tertiary: '#002842'
  on-tertiary: '#ffffff'
  tertiary-container: '#003f63'
  on-tertiary-container: '#59adef'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#d5e5ef'
  primary-fixed-dim: '#b9c9d3'
  on-primary-fixed: '#0e1d25'
  on-primary-fixed-variant: '#3a4951'
  secondary-fixed: '#cbe8eb'
  secondary-fixed-dim: '#b0cccf'
  on-secondary-fixed: '#031f22'
  on-secondary-fixed-variant: '#314b4e'
  tertiary-fixed: '#cde5ff'
  tertiary-fixed-dim: '#94ccff'
  on-tertiary-fixed: '#001d32'
  on-tertiary-fixed-variant: '#004b74'
  background: '#f8f9fa'
  on-background: '#191c1d'
  surface-variant: '#e1e3e4'
typography:
  headline-xl:
    fontFamily: Inter
    fontSize: 64px
    fontWeight: '700'
    lineHeight: 72px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Inter
    fontSize: 40px
    fontWeight: '600'
    lineHeight: 48px
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Inter
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
  story-heading:
    fontFamily: Playfair Display
    fontSize: 32px
    fontWeight: '400'
    lineHeight: 44px
  body-lg:
    fontFamily: Inter
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Inter
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-caps:
    fontFamily: Inter
    fontSize: 12px
    fontWeight: '600'
    lineHeight: 16px
    letterSpacing: 0.1em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 8px
  gutter: 24px
  margin-mobile: 20px
  margin-desktop: 80px
  container-max: 1440px
---

## Brand & Style

The design system embodies the intersection of advanced engineering and the raw, untamed beauty of the Pacific Northwest. The brand personality is "Industrial Elegance"—precision-built structures that feel like a natural extension of the landscape rather than an imposition upon it. 

The aesthetic leverages a **Minimalist-Futuristic** style with **Glassmorphism** to reflect the expansive windows and sleek surfaces of the modular cabins. The goal is to evoke a sense of quiet luxury, durability, and high-tech sanctuary. Interfaces should feel airy, utilizing heavy whitespace to mirror the openness of a mountain peak, while maintaining a rigorous grid that suggests the modular efficiency of the cabins themselves.

## Colors

The palette is grounded in the atmospheric tones of Squamish. **Slate Grey** provides the structural foundation, used for primary text and heavy UI containers. **Deep Forest Green** acts as a sophisticated secondary tone for backgrounds and subtle branding elements. 

**Arctic White** is the primary background color, ensuring the interface feels expansive. **Electric Blue** is reserved strictly for high-priority interactive elements (CTAs) and critical highlights, representing the "Techno" spark within the "Nature" backdrop. 

- **Primary:** Structural elements, headings, and high-emphasis icons.
- **Secondary:** Surface depth and lifestyle-oriented UI segments.
- **Tertiary (Action):** Interactive triggers, primary buttons, and active states.
- **Neutral:** Main canvases and high-contrast negative space.

## Typography

This design system utilizes a dual-typeface strategy to distinguish between engineering specifications and lifestyle narratives. 

**Inter** is the workhorse typeface. It is used for UI elements, technical specs, and primary headings to convey precision and modernity. Headlines should utilize tight letter-spacing and bold weights to feel architectural.

**Playfair Display** is introduced for editorial "moments"—pull quotes, cabin descriptions, or resort highlights. It should be used sparingly to maintain its impact, evoking the "Luxury" aspect of the brand.

Use `label-caps` for metadata, cabin technical specs (e.g., "SQUARE FOOTAGE"), and small navigation links to maintain a technical, catalog-like feel.

## Layout & Spacing

The layout follows a **Fixed Grid** model on desktop to mimic the rigid dimensions of modular architecture. A 12-column grid is used with generous margins to keep content focused.

- **Desktop:** 80px side margins with 24px gutters. Content should be grouped in modular blocks (e.g., 4-column feature cards or 6-column split screens).
- **Mobile:** 20px side margins. Layouts reflow to a single column, but maintain vertical rhythm using the 8px base unit.
- **Vertical Rhythm:** Use large padding (80px, 120px, or 160px) between sections to create a "breathtaking" sense of space, mirroring the PNW landscapes.

## Elevation & Depth

To achieve the "Techno-Nature" look, elevation is handled through **Glassmorphism** and **Tonal Layers** rather than heavy shadows.

- **Surface Levels:** The base level is Arctic White. Secondary containers use a 5% opacity Slate Grey or a 50% opacity white with a 20px backdrop blur (frosted glass).
- **Shadows:** Use only one shadow style—an "Ambient Glow." It should be highly diffused (40px blur), very low opacity (5-8%), and tinted with the primary Slate Grey color to avoid a "muddy" look.
- **Dividers:** Use 1px solid lines in Slate Grey at 10% opacity. This mimics the thin, precise seams of modular cabin joints.

## Shapes

The shape language is **Soft (0.25rem)**. This choice balances the sharp, geometric lines of industrial cabins with the organic accessibility of a luxury resort. 

- **Primary Elements:** Buttons and input fields use a 4px (0.25rem) radius.
- **Large Containers:** Cards and image galleries use 8px (0.5rem) to feel more inviting.
- **Interactive States:** When a user hovers over a card, it should not become "rounder," but rather its border-weight or backdrop-blur should subtly increase to maintain structural integrity.

## Components

### Buttons
- **Primary:** Electric Blue background, white text, 4px radius. No shadow.
- **Secondary:** Transparent background, 1px Slate Grey border (20% opacity), Slate Grey text.
- **Ghost:** No border, Electric Blue text, used for "View Specs" or internal links.

### Cards (The "Modular" Unit)
Cards are the core of this design system. They should use the glassmorphic style: a white background at 70% opacity, a 20px backdrop blur, and a 1px white border at 30% opacity. Images inside cards should be flush to the top but maintain the card's corner radius.

### Input Fields
Minimalist 1px bottom-border only (Slate Grey at 30% opacity). Labels use `label-caps` and sit above the field. On focus, the bottom border transitions to Electric Blue.

### Cabin Specs List
A technical list component using `label-caps` for the key and `body-md` for the value, separated by a light 1px horizontal line. This reinforces the "engineered" nature of the product.

### Image Gallery
High-resolution images should always be full-bleed or occupy specific grid-spans. Use subtle parallax effects on scroll to create a sense of depth and movement through the scenery.
# Design Proposal: Jesus Alfaro — Premium Yachting Portfolio

## Análisis
- **Profesión:** OOW Unlimited | Deckhand / Junior Officer (superyacht industry)
- **Tier:** Premium S/.280 (upgrade desde Pro S/.120)
- **Template base:** `premium-starter` (heavy customization hacia editorial magazine)
- **Audiencia:** Captains, Chief Mates, Yacht Managers, Charter Companies (Fort Lauderdale/Miami yachting hub)
- **Idioma:** Inglés

## Concepto: Editorial Maritime Magazine

Un portfolio que se siente como una **revista de yachting de lujo** (ref: Boat International, superyachts.com). Tipografía serif editorial, fotos grandes como protagonistas, layout alternado foto/texto que demuestra experiencia real a bordo. NO es un "portfolio técnico" — es una **historia visual profesional** de alguien que vive y trabaja en superyates.

## Paleta (monocromática fría + neutro cálido sand)

```ts
colors: {
  primaryDark: "#0A1628",      // Midnight navy (deep ocean) — headings, footer bg
  primary: "#1E3A5F",          // Deep navy — borders, badges
  primaryLight: "#4A6FA5",     // Steel blue — shimmer light tone
  accent: "#C9A96E",           // Champagne gold / teak — CTAs, stats, dots (subtle luxury)
  surface: "#F5F1EA",          // Bone/sand (teak deck tone) — section backgrounds
  surfaceLight: "#FAFAF7",     // Ivory — hero bg
}
```

**Justificación:**
- `primaryDark #0A1628` — midnight navy, evoca cabina de noche + deep ocean. Sin ser genérico "navy blue".
- `primary #1E3A5F` + `primaryLight #4A6FA5` — gradiente monocromático frío (mismo hue family).
- `accent #C9A96E` — **champagne gold / teak color** — sobre navy da feel luxury yachting (teak es EL material de los superyates). No es "amarillo random" — es el color del teak natural que sale en 70% de sus fotos trabajando.
- `surface #F5F1EA` — tono bone/sand, se lee como papel de revista editorial. Contraste AAA con primaryDark.
- `surfaceLight #FAFAF7` — ivory, whitespace premium.

Temperatura: Fría dominante (navy) + neutro cálido (bone/teak). Válido — el teak es neutro dorado, no rompe la temperatura.

## Tipografía

- **Display (headings H1/H2):** `Cormorant` serif — ya incluido en premium-starter, evoca tipografía Arthur/Oceano
- **Body:** `Montserrat` — sans clean, legibilidad
- **Accent/Quotes:** `Cormorant Italic` — pull quotes editoriales

## Estructura de Secciones

### 1. Header (sticky glassmorphism)
- Logo: iniciales "JA" en serif Cormorant + navy
- Nav: About | Experience | Certifications | References | Contact

### 2. Hero — **2-column split (editorial magazine)**
- **Izquierda (texto):**
  - Pre-title (small caps): `OOW UNLIMITED · DECKHAND / JUNIOR OFFICER`
  - Title display serif: `Jesus Alfaro`
  - Subtitle: `Seeking a long-term position onboard a private or charter motor yacht.`
  - Location bar: 📍 Fort Lauderdale, FL · Available Immediately
  - CTAs: `Download CV` (primary) + `View References` (secondary)
- **Derecha (foto):** `5.38.33 PM.jpeg` full-height (polo celeste, yate de fondo, Miami)
- **Stats bar debajo:** `2+` Years Maritime / `5+` Yachts (2026) / `4` Professional References
- Background: surfaceLight con subtle wave texture SVG en bottom (like Oceano)

### 3. Professional Profile (full-width quote section)
- Un solo párrafo en serif grande (text-3xl Cormorant italic)
- El "Professional Profile" del CV
- Background: surface (bone)
- Decoración: subtle anchor/compass icon

### 4. Yachting Experience — **Alternating layout (Arthur-style)**
Cada vessel es una entrada con foto grande + descripción:

**Entry 1 (imagen IZQ, texto DER):** M/Y Princess Ashita 87' (NOW — destacado "Current Position")
→ Foto: buffing action shot `5.38.32 PM.jpeg`

**Entry 2 (imagen DER, texto IZQ):** M/Y Incognito 130' (Boca Raton)
→ Foto: deckwork con líneas `4.29.09 PM (1).jpeg`

**Entry 3 (imagen IZQ, texto DER):** All Class Detailing — WPB Boat Show (Sunseeker/Jupiter/Sirena)
→ Foto: Boat Show superyates `4.29.09 PM (4).jpeg`

**Entry 4 (imagen DER, texto IZQ):** M/Y Irvette (ex Mystere) 108'
→ Foto: radio/VHF `4.30.53 PM.jpeg`

**Entry 5 (imagen IZQ, texto DER):** F/V Dropout 57' Sportfishing
→ Foto: atardecer marina `5.38.32 PM (5).jpeg`

Cada entry:
- Dates badge (bone tag)
- Vessel name en serif display
- Role & location
- Bullets de responsibilities (3-4)

### 5. Section Divider (full-bleed photo)
- `3.54.09 PM (2).jpeg` — NIGHT HOWL superyacht iluminado de noche
- Overlay sutil navy + quote en serif blanco: "Every passage is precision."

### 6. Professional Maritime Background (HF Offshore timeline)
- Card única elegante: "2023–2025 · HF Offshore / Harren & Partner"
- 3rd Officer → 2nd Officer / DPO
- Operational areas (Caribbean, W Africa, Gulf of Mexico)
- Clientes notables: Chevron, Saipem, Pemex
- Key responsibilities en 2-col grid

### 7. Licenses & Certifications — **Editorial grid 2-col**
Header: `Licenses & Certifications`
- **Col 1:**
  - Licenses (OOW Unlimited, DP Unlimited)
  - Safety & Mandatory Training (STCW, Fire Fighting, Survival Craft, SSO)
  - Medical (First Aid, Medical Care)
- **Col 2:**
  - Bridge & Navigation (ECDIS, Radar/ARPA, GMDSS, BRM, AIS)
  - Personal Details (Nationality, Languages, Visas, ENG1)
  - Languages badges

Tipografía serif en titles, sans en items. Separadores hairline.

### 8. Core Competencies (2-col with icons)
- **Operational Skills** (7 items) + **Professional Attributes** (6 items)
- Simple list con bullet dots accent (gold teak)

### 9. References — **4 cards premium**
Grid 2x2 cards con:
- Nombre del Chief Mate / Captain
- Role (Chief Mate | Superyachts)
- Flag emoji por país (🇵🇪 🇬🇧 🇳🇦 🇺🇸)
- Phone/WhatsApp/Email (con iconos)
- Background: cream surface, borde hairline

### 10. CTA — "Open to Positions"
- Title: `Available Immediately · Fort Lauderdale Based`
- Subtitle: `Open to permanent, rotational, or temporary positions onboard private or charter motor yachts.`
- Email CTA + Phone CTA (US number +1 754-277-0935)

### 11. Footer navy + accent gold links
- LinkedIn, email, phone US, location

## Motion Design

- Hero: heroFadeUp stagger (title → subtitle → stats → photo)
- Experience entries: reveal alternados (left/right según lado de foto)
- Quote section: quote-float subtle
- Cards references: card-hover lift
- Full-bleed divider: parallax subtle en scroll
- prefers-reduced-motion: solo opacity (accessibility)

## Decisiones de Contenido

- **NO incluir Projects section** (no aplica a deckhand, reemplazado por Yachting Experience)
- **NO incluir Services section** (no es freelancer con servicios)
- **SÍ incluir Experience con formato editorial** (foto grande alternada)
- **SÍ incluir References destacadas** (es CRÍTICO para conseguir trabajo en yachting — el cliente lo dijo explícitamente)
- **Portfolio 100% en INGLÉS** (mercado internacional)
- **Education OMITIDA** (no está en CV v2 — el CV no incluye educación formal)

## Contraste vs Portfolio Pro anterior

| Aspecto | Pro (viejo) | Premium (nuevo) |
|---------|-------------|-----------------|
| Tipografía | Sans estándar | Cormorant serif editorial |
| Fotos | 1 foto hero | 10+ fotos grandes full-bleed alternadas |
| Layout | Timeline vertical | Editorial magazine alternado |
| Experience | Sólo HF Offshore | 5 yachts actuales + HF Offshore |
| References | No | 4 Chief Mates destacados |
| Paleta | Navy genérico | Navy + teak gold (unique) |
| Feel | Portfolio técnico | Revista yachting de lujo |
| CV | Feb 2026 | Abril 2026 (actualizado Fort Lauderdale) |

## Files To Build/Modify

```
src/config.ts                 → Full rewrite con nueva data
src/components/Hero.astro     → 2-col editorial magazine
src/components/About.astro    → Full-width quote (Professional Profile)
src/components/Experience.astro → Alternating yacht entries with large photos
src/components/SectionDivider.astro → NEW: full-bleed photo divider
src/components/Certifications.astro → NEW: replaces Projects, editorial grid
src/components/Competencies.astro → NEW: 2-col skills
src/components/References.astro → NEW: 4 premium cards
src/components/CTA.astro → Availability block
src/components/Footer.astro → Navy + accent
src/components/Header.astro → English nav, glassmorphism
src/pages/index.astro → New section order
src/styles/global.css → Cormorant serif, teak accent tweaks
public/                       → 10+ yacht photos, new profile.jpg, favicon
```

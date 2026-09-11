---
name: LOMBAO — Lombao Studio
description: Software boutique; fucsia como color de acción, Momo Trust Display en titulares, Poppins funcional, turquesa solo sobre antracita.
colors:
  brand: "#e1147a"
  brand-hover: "#a90f5c"
  brand-soft: "#e7518e"
  accent: "#35b7b9"
  blue-dark: "#276493"
  blue-dark-hover: "#1d4b6e"
  ink: "#181c21"
  neutral-700: "#3d4149"
  neutral-500: "#6b7178"
  neutral-300: "#c4c7cb"
  neutral-100: "#edeef0"
  neutral-0: "#ffffff"
  error: "#ba1a1a"
typography:
  display:
    fontFamily: "Momo Trust Display, Poppins, sans-serif"
    fontSize: "clamp(2.25rem, 5.5vw, 3.5rem)"
    fontWeight: 400
    lineHeight: 1.1
    letterSpacing: "-0.02em"
  body:
    fontFamily: "Poppins, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
    lineHeight: 1.5
rounded:
  sm: "10px"
  md: "16px"
  card: "1rem"
  pill: "9999px"
spacing:
  section: "clamp(4rem, 9vw, 6.5rem)"
  container: "80rem"
components:
  button-primary:
    backgroundColor: "{colors.brand}"
    textColor: "{colors.neutral-0}"
    rounded: "{rounded.md}"
    padding: "0.75rem 1.5rem"
  button-primary-hover:
    backgroundColor: "{colors.brand-hover}"
  button-outline:
    backgroundColor: "transparent"
    textColor: "{colors.ink}"
    rounded: "{rounded.md}"
  badge-accent:
    backgroundColor: "{colors.accent}"
    textColor: "{colors.ink}"
    rounded: "{rounded.pill}"
---

# Design System: LOMBAO — Lombao Studio

## Overview

**Creative North Star: "The Fucsia Signal"** — una marca de software boutique que se reconoce de inmediato por un único acento saturado (fucsia) usado con disciplina sobre superficies limpias, y titulares de carácter en una display propia. El antracita sostiene el texto y los bloques oscuros; el turquesa aparece solo como acento sobre antracita. La densidad es generosa y el ritmo claro/oscuro alterna secciones para dar respiro.

El sistema se construye sobre Tailwind v4 con un `globals.css` que expone tokens semánticos (`--color-brand`, `--color-ink`, etc.) y un set de componentes reutilizables. Las fuentes (Momo Trust Display, Poppins) están autoalojadas; no hay dependencias de fuentes o íconos externos.

**Key Characteristics:**
- Fucsia como único color de acción; rosa y turquesa como apoyos con reglas de contraste estrictas.
- Momo Trust Display solo en titulares cortos, siempre en peso real 400.
- Superficies limpias, radios suaves, bordes sutiles y sombras con offset (nunca duras).
- Secciones en ritmo claro/oscuro: hero y marketing en antracita; servicios en neutro claro.

## Colors

Paleta de marca saturada sobre neutros derivados del antracita; el fucsia manda la acción, el turquesa vive sobre fondo oscuro.

### Primary
- **Fucsia / Acción** (#E1147A): color de marca y única voz de acción — CTAs primarios, links, subrayado de nav, ícono hero. Texto fucsia sobre blanco solo a ≥16px (4.6:1, límite AA).
- **Fucsia Oscuro / Hover texto** (#A90F5C): hover y focus de links, y color base de `.action-link` en texto <16px (7.2:1 sobre blanco, AA holgado).

### Secondary
- **Rosa / Apoyo** (#E7518E): hover de CTAs, acentos secundarios y texto grande/decorativo. Sobre antracita alcanza 4.9:1, por lo que es el color de texto pequeño sobre oscuro (CTAs secundarios, nav-hover).

### Tertiary
- **Turquesa / Acento** (#35B7B9): acento secundario — badges, íconos y links de footer **solo sobre antracita**. Nunca como texto sobre fondo claro (2.4:1, falla AA). Combinación tinta-sobre-turquesa verificada (7.0:1) para tarjetas sólidas (variante `accent` del stack).

### Quaternary
- **Azul Oscuro** (#276493, hover #1D4B6E): cuarto stop del degradado de marca; reservado a gráficos y fondos, nunca texto pequeño sobre claro sin verificar.

### Degradados de marca
- **`.bg-gradient-brand`** (160deg: fucsia → rosa → turquesa → azul oscuro): fondos hero e ilustraciones grandes, con opacidad reducida como capa; sirve de fallback visual de assets reales.
- **`.bg-gradient-accent`** (90deg: fucsia → turquesa): dividers, barras finas y progress bars; nunca fondo de sección completa.

### Neutral
- **Negro Antracita** (#181C21): texto principal y fondos de secciones oscuras/hero/footer.
- **Neutral 700** (#3D4149): texto secundario sobre claro (cuerpo de servicios).
- **Neutral 500** (#6B7178): texto deshabilitado/placeholder.
- **Neutral 300** (#C4C7CB): bordes y divisores.
- **Neutral 100** (#EDEEF0): fondos alternos (sección servicios) y chips.
- **Blanco** (#FFFFFF): fondo base y texto sobre antracita.

### Named Rules
**The Fucsia-Only-On-Action Rule.** El fucsia es exclusivo de la acción (CTAs, links, nav). El rosa lo acompaña en hover/soporte; el turquesa queda reservado a acentos sobre oscuro. Ningún color de marca decora sin función.

**The Turquoise-On-Dark Rule.** El turquesa solo se usa sobre antracita (badges, íconos, footer). Como texto sobre blanco tiene 2.4:1 y está prohibido.

## Typography

**Display Font:** Momo Trust Display (con Poppins de fallback)
**Body Font:** Poppins (con system-ui de fallback)
**Label/Mono Font:** Poppins (mismo stack funcional)

**Character:** titulares de carácter y personalidad (Momo) contra un cuerpo geométrico y neutral (Poppins); la display nunca va en texto largo.

### Hierarchy
- **Display / H1–H2** (400, clamp(2.25rem,5.5vw,3.5rem) / clamp(1.875rem,4vw,2.5rem), lh 1.1 / 1.15): titulares de página y secciones, en Momo 400 (peso real disponible).
- **Headline / H3–H4** (600, clamp(1.5rem,3vw,2rem) / clamp(1.25rem,2.4vw,1.5rem)): subtítulos y tarjetas, Poppins.
- **Title / H5–H6** (500, 1.25rem / 1.125rem): encabezados menores.
- **Body** (400, 1rem / lh 1.5; lead 1.125rem / lh 1.75): párrafos y lead.
- **Label / Overline** (600, 0.75rem, ls 0.08em, uppercase): badges, etiquetas de campo.
- **Link (inline)** (500): enlaces de texto en Poppins Medium fucsia, con hover en fucsia-oscuro.

### Named Rules
**The Real-Weight Rule.** Momo Trust Display se entrega solo en Regular (400); los titulares usan 400 y nunca bold sintético. Si llega el Bold, es un `@font-face` adicional, no un `font-weight: 700` falso.

## Layout

Contenedor centrado `.container-site` (máx 80rem, padding-inline 1rem → 2rem en ≥768px → 4rem en ≥1024px). Separación de sección `.section-py` (clamp 4rem→6.5rem). Grid de 12 columnas `.grid-12` (gap 1rem → 1.5rem en ≥768px) para composiciones amplias; grids nativos de Tailwind para layouts de 2–3 columnas. Ritmo continuo: un solo fondo inmersivo oscuro (`.site-glow` sobre `body bg-ink`) atraviesa todas las secciones; el footer antracita sólido cierra como ancla. Mobile-first; el header colapsa a menú hamburguesa bajo `md`.

## Elevation & Depth

Sombras suaves con offset y blur (nunca bloques de offset duro). `.card` y `.glass--surface` usan `0 16px 32px -16px rgba(24,28,33,0.2)` en hover con `translateY(-3px)`. El header usa `.glass--dark` (cristal sutil centralizado, con fallback sólido y respeto a `prefers-reduced-transparency`).

**Fondo inmersivo continuo.** Una sola capa fija `.site-glow` (z-0, `pointer-events: none`) en `Layout.astro` con 4 `.glow-blob` (brand ×2, accent, blue-dark) sobre `body bg-ink`. Las secciones son transparentes (sin `bg` propio) y el contenido va en `relative z-10`: el glow fluye sin costuras entre secciones. Si hay jank en mobile, bajar primero el blur de `.site-glow` (120px → 80–100px) antes de tocar el de las cards.

### Shadow Vocabulary
- **Card hover** (`box-shadow: 0 16px 32px -16px rgba(24,28,33,0.2)` + `translateY(-3px)`): eleva la tarjeta al hover.

## Shapes

Radios suaves y consistentes: botones e inputs `0.625rem` (10px), tarjetas `1rem` (16px), badges y botones `.btn--pill` totalmente redondeados (`9999px`). Bordes finos `1px` en `neutral-300`. Sin esquinas rectas puras en componentes de marca.

## Components

### Buttons
- **Shape:** radio 10px (`.btn--pill` lo lleva a 9999px).
- **Primary:** fondo fucsia, texto blanco, padding 0.75rem 1.5rem, Poppins 600.
- **Hover / Focus:** fondo fucsia-oscuro; focus-visible global con anillo fucsia 2px.
- **Outline / Ghost:** contorno tinta (claro) o ghost fucsia; sobre oscuro se usa `text-brand-soft` + borde rosa.

### Chips (Badges)
- **Style:** pill, Poppins 600, 0.75rem, ls 0.08em, uppercase.
- **Variants:** `badge-default` (fucsia 10% + texto fucsia-oscuro), `badge--outline`, `badge--solid`, `badge--accent` (turquesa sobre oscuro).

### Cards / Containers
- **Corner Style:** 1rem.
- **Background:** blanco, `card--dark` (antracita) o variantes glass sobre el fondo inmersivo.
- **Shadow Strategy:** plano en reposo, sombra de offset al hover.
- **Border:** 1px `neutral-300`.
- **Internal Padding:** 1.5rem (`card-body`).
- **Glass variants:** `glass--dark` (header, stack dark/glass), `glass--brand` 55% (stack, texto blanco 9.2:1), `glass--accent` 80% (stack, texto ink 5.0:1 — por debajo de ~75% falla AA), `glass--surface` 90% blanco (bento, texto ink ≥14:1, con hover-lift como `.card`). Todas con fallback sólido `@supports` y respeto a `prefers-reduced-transparency`.

### Inputs / Fields
- **Style:** borde `neutral-300`, radio 10px, fondo blanco.
- **Focus:** borde fucsia + anillo `0 0 0 3px color-mix(brand 18%)`.
- **Error:** borde `--color-error` (#BA1A1A) + anillo de error.

### Navigation
- **Style:** `.nav-link` (Poppins 500) con subrayado animado fucsia; sobre oscuro usa texto claro y hover rosa.
- **Labels:** nav en español (Servicios, Proyectos, Nosotros, Contacto) en desktop y móvil.
- **Mobile:** botón hamburguesa que abre panel `.glass--dark`, links claros, `aria-expanded` controlado por script mínimo.
- **Head SEO:** `meta description`, Open Graph (`og:title`, `og:description`, `og:type`, `og:image`) y favicon SVG en `Layout.astro`.

### Action Link
- **Style:** `.action-link` con flecha SVG autorada (mask-image, color actual), translate al hover; color base fucsia-oscuro (#A90F5C, 7.2:1 sobre blanco).

## Do's and Don'ts

### Do:
- **Do** usar fucsia para todo elemento accionable (CTA, link, nav) y reservar rosa/turquesa para apoyo.
- **Do** mantener Momo Trust Display en peso 400 real y solo en titulares.
- **Do** colocar texto pequeño sobre antracita en rosa (#E7518E, 4.9:1) o turquesa, nunca fucsia (3.7:1, falla AA).
- **Do** tematizar superficies del navegador (selection, caret, focus-visible, scrollbar) con la paleta.
- **Do** respetar `prefers-reduced-motion` (sin transiciones de transform en `.card`/`.btn`, scroll instantáneo, `motion-reduce:` en micro-interacciones Tailwind).
- **Do** usar `.bg-gradient-brand` con opacidad reducida como fallback visual de assets hero/marketing.

### Don't:
- **Don't** usar turquesa como texto sobre fondo claro.
- **Don't** usar turquesa en iconos pequeños sobre fondo claro (2.4:1); usar fucsia (4.6:1).
- **Don't** aplicar bold sintético a Momo ni System/display genéricas en titulares.
- **Don't** introducir fuentes o íconos externos (Google Fonts, Material Symbols); Lucide SVG inline o SVG artesanal.
- **Don't** usar sombras de offset duro ni texto en gradiente.

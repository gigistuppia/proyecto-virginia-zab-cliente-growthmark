# CLAUDE.md — Virginia Zab · Persianas

> **Versión:** v1.0 · **Fecha:** 2026-08-13 · **Track:** Fast Track (confirmado 2026-08-13)
> **Agencia:** GROWTHMARK · **Ejecutor:** Claude Code
> Este archivo es la fuente única de verdad del proyecto. Cada cambio significativo se commitea con `docs(claude-md): vX.Y — descripción` y una entrada en la sección 14.
> El ejecutor no debe inventar datos de negocio. Toda información faltante está marcada `[A CONFIRMAR]` con supuesto adoptado explícito.

---

## 1. Contexto del proyecto

- **Cliente:** Virginia Zab
- **Nombre comercial:** Virginia Zab — Persianas `[A CONFIRMAR: puede ser "VZ Persianas", "Persianas Virginia Zab" u otro nombre de marca]`
- **Industria/rubro:** Venta, asesoramiento e instalación de persianas y cortinas. Proveedora oficial de Hunter Douglas Argentina.
- **Referencia visual:** luzzidisegno.com.ar — interiorismo premium, ritmo contemplativo, imágenes editoriales a pantalla completa, copy emocional sobre funcional.
- **Resumen del proyecto:** Landing page de una sola página (carta de venta informativa) para Virginia Zab, proveedora de Hunter Douglas. El sitio debe presentar la oferta de productos y servicios, generar confianza mediante el aval de Hunter Douglas, mostrar trabajos realizados y convertir visitas en consultas por WhatsApp. Comienza con un carrusel hero de imágenes editoriales.

---

## 2. Objetivos

- **Objetivo principal:** Convertir visitas orgánicas en consultas directas por WhatsApp o formulario de contacto.
- **Objetivo secundario 1:** Posicionar a Virginia como proveedora oficial de Hunter Douglas en su zona geográfica.
- **Objetivo secundario 2:** Mostrar la calidad y variedad de instalaciones realizadas (galería de trabajos).
- **Objetivo secundario 3:** Rankear para keywords locales: "persianas [ciudad] Hunter Douglas" y variantes.
- **KPI de éxito:** Tasa de clics al botón WhatsApp ≥ 5% de visitas únicas. Posición ≤ 5 en Google para "persianas Hunter Douglas [ciudad]" en 90 días.

---

## 3. Audiencia

- **Público primario:** Propietarios de viviendas (35-60 años, NSE medio-alto) que están refaccionando, decorando o construyendo. Buscan calidad, asesoramiento personalizado y garantía de marca. Toman decisiones de compra con deliberación — no compran por impulso.
- **Público secundario:** Arquitectos, diseñadores de interiores y constructoras que buscan proveedores confiables de productos premium para sus proyectos residenciales y corporativos.
- **Contexto de búsqueda:** La mayoría llega buscando "persianas [ciudad]", "cortinas roller Hunter Douglas", o buscando el nombre directamente por recomendación. Llegan con intención comercial, no informacional.
- **Insight del sector:** El buyer del rubro compra primero con los ojos (fotos de ambientes instalados) y luego busca respaldo de marca. El logo de Hunter Douglas es más convincente que cualquier testimonio.

---

## 4. Tono y personalidad de marca

### Tres adjetivos definitorios
Cálida · Precisa · Confiable

### Voz
Profesional accesible (formalidad 3-4 según escala GROWTHMARK). Ni demasiado corporativa ni demasiado casual. Habla de materiales y calidad sin jerga técnica innecesaria.

### Persona gramatical
- **Argentina (vos/te)** — registro Rioplatense
- Nunca "usted". Nunca "nosotros somos la mejor empresa".
- Ejemplos de DO: "Elegí la persiana que transforma tu espacio", "Te asesoramos en cada detalle", "Pedí tu consulta sin cargo"
- Ejemplos de DON'T: "Somos líderes en el rubro", "Nuestros precios son los más competitivos", "¡Consultanos ahora!"

### Reglas de comunicación
- **DO:** Hablar de cómo la luz transforma el ambiente. Citar a Hunter Douglas como aval. Mostrar antes/después concretos.
- **DO:** Oraciones cortas (< 20 palabras). Copy emocional en heroes, copy funcional en productos.
- **DO:** Un CTA dominante por sección — nunca dos CTAs compitiendo.
- **DON'T:** Emojis en ningún lugar del sitio.
- **DON'T:** Precios en el sitio (se acuerdan en consulta).
- **DON'T:** Párrafos centrados de más de dos líneas.

---

## 5. Sistema visual

### Paleta cromática

| Token | HEX | Uso | Contraste WCAG AA |
|---|---|---|---|
| `--bg` | `#F5EFE8` | Fondo base (crema cálido) | — |
| `--surface` | `#EDE5DC` | Cards, fondos alternativos (+5% oscuro) | — |
| `--text` | `#1C1917` | Texto principal | 14.3:1 sobre --bg ✅ |
| `--text-2` | `#5C504A` | Texto secundario, eyebrows | 5.2:1 sobre --bg ✅ |
| `--accent` | `#8B5E3C` | CTA único, highlights, el único color saturado | 4.6:1 sobre --bg ✅ |
| `--accent-dark` | `#6B4428` | CTA hover state | 6.8:1 sobre --bg ✅ |
| `--neutral` | `#D4C4B0` | Bordes, separadores, fondo neutro | — |
| `--white` | `#FFFFFF` | Texto sobre acento, fondos de tarjetas específicas | — |

**Regla de color:** Un único color con saturación (`--accent`). Todo lo demás son derivados del fondo. Si el acento está en más de dos elementos por sección, hay exceso.

### Tipografía

| Rol | Familia | Peso | Google Fonts URL |
|---|---|---|---|
| Títulos/Display | Cormorant Garamond | 600 | `family=Cormorant+Garamond:wght@600` |
| Cuerpo / UI | Source Sans 3 | 400, 600 | `family=Source+Sans+3:wght@400;600` |

**Preload obligatorio:**
```html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="preload" as="style" href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600&family=Source+Sans+3:wght@400;600&display=swap">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@600&family=Source+Sans+3:wght@400;600&display=swap">
```

**Escala tipográfica (fluid, clamp):**
```css
--step--1: clamp(0.83rem, 0.8rem + 0.15vw, 0.9rem);   /* eyebrows, meta */
--step-0:  clamp(1rem, 0.95rem + 0.25vw, 1.1rem);      /* cuerpo */
--step-1:  clamp(1.25rem, 1.15rem + 0.5vw, 1.5rem);    /* lead text */
--step-2:  clamp(1.6rem, 1.4rem + 1vw, 2.2rem);        /* H3 */
--step-3:  clamp(2rem, 1.6rem + 2vw, 3.2rem);          /* H2 */
--step-4:  clamp(2.8rem, 2rem + 4vw, 5.5rem);          /* H1 hero */
```

**Ajustes tipográficos que separan diseñador de modelo:**
```css
h1, h2 { font-family: 'Cormorant Garamond', serif; font-weight: 600; }
h1 { font-size: var(--step-4); letter-spacing: -0.03em; line-height: 0.95; }
h2 { font-size: var(--step-3); letter-spacing: -0.02em; line-height: 1.05; }
h3 { font-size: var(--step-2); letter-spacing: -0.01em; line-height: 1.1; }
p  { font-family: 'Source Sans 3', sans-serif; font-size: var(--step-0); line-height: 1.7; max-width: 68ch; }
```

### Espaciado — grid 8px estricto

```css
--space-1: 8px;   --space-2: 16px;  --space-3: 24px;
--space-4: 40px;  --space-5: 64px;  --space-6: 96px;
--space-7: 144px; --space-8: 200px;
```

Separación entre secciones: `--space-7` (144px en desktop, `--space-6` en mobile).

### Border radius

| Valor | Dónde aplica |
|---|---|
| `4px` | Badges, chips, tags pequeños |
| `8px` | Botones, inputs |
| `12px` | Cards de producto, galería |
| `0px` | Imágenes editoriales a sangre, carrusel |

### Motion — principios

```css
/* Easing curves (no usar ease/linear por defecto) */
--ease-out:   cubic-bezier(0.22, 1, 0.36, 1);     /* entradas al viewport */
--ease-trans: cubic-bezier(0.65, 0, 0.35, 1);     /* transiciones entre estados */
--ease-spring: cubic-bezier(0.34, 1.56, 0.64, 1); /* microinteracciones con resorte */

/* Presupuesto de movimiento */
/* 1 animación protagonista: carrusel hero (fade + scale, 800ms, --ease-out) */
/* 1 sistema de entrada al scroll: fade-up (opacity 0→1 + translateY 24px→0, 600ms, --ease-out, 60ms stagger) */
/* Microinteracciones: hover en CTAs y cards (150-200ms, --ease-out) */
/* prefers-reduced-motion: todas las animaciones desactivadas */
```

**Solo animar `transform` y `opacity`. Nunca `width`, `height`, `top`, `left`, `margin`.**

### Estética en una frase
Interior de alta gama rioplatense: crema cálida, serifa con peso, luz como protagonista.

---

## 6. Arquitectura del sitio

### Sitemap
```
index.html (única página)
  ├── #hero         → Carrusel hero
  ├── #credencial   → Badge Hunter Douglas
  ├── #propuesta    → Por qué elegir a Virginia
  ├── #productos    → Líneas de productos
  ├── #comparador   → Gesto único (slider antes/después)
  ├── #galeria      → Trabajos realizados
  ├── #proceso      → 4 pasos
  ├── #contacto     → CTA final + formulario/WhatsApp
  └── footer
```

### Wireframe textual — bloques en orden

```
┌─────────────────────────────────────────────────────────┐
│ NAVBAR (sticky, transparente sobre hero → sólido al scroll)
│ Logo VZ  |  [Productos] [Trabajos] [Contacto]  |  [WhatsApp CTA]
├─────────────────────────────────────────────────────────┤
│ #hero — CARRUSEL HERO (100vh, auto-advance 5s)
│ Slide 1: Dormitorio con roller blackout + headline
│ Slide 2: Living con Silhouette/Duette + subheadline
│ Slide 3: Espacio corporativo + CTA
│ Controles: flechas L/R + dots indicadores + swipe mobile
│ Overlay gradiente negro al 50% en la zona del texto
│ Texto alineado izquierda, safe area inferior
│ H1: "Luz precisa.     (Cormorant Garamond)
│      Espacio perfecto."
│ p: "Proveedora oficial Hunter Douglas en [Ciudad]."
│ CTA: "Pedí tu consulta" → #contacto
├─────────────────────────────────────────────────────────┤
│ #credencial — BANDA FULL WIDTH (fondo --text oscuro)
│ Logo Hunter Douglas + "Proveedora oficial Argentina"
│ 3 stats: X años de experiencia · Y instalaciones · Garantía HD
│ (Datos en [A CONFIRMAR] — ver sección 12)
├─────────────────────────────────────────────────────────┤
│ #propuesta — SECCIÓN EDITORIAL 2 COLUMNAS
│ Col izq (60%): H2 + 3 párrafos emocionales sobre el servicio
│ Col der (40%): Imagen única, gran formato, temperatura cálida
│ Texto alineado izquierda, max-width 60ch
├─────────────────────────────────────────────────────────┤
│ #productos — GRID DE LÍNEAS (2x2 desktop / 1 col mobile)
│ Roller Quantum® (Blackout / Screen / Decorativa)
│ Duette® (eficiencia energética, tela de celdas)
│ Silhouette® (velos traslúcidos, control de privacidad)
│ PowerView® (automatización, control desde el smartphone)
│ Cada card: imagen + nombre + descripción 2 líneas + "Ver más"
│ NOTA: los links "Ver más" apuntan a hunterdouglas.com.ar/productos/
├─────────────────────────────────────────────────────────┤
│ #comparador — GESTO ÚNICO (pantalla completa, rompe grilla)
│ H2: "Ver para creer."
│ Slider interactivo antes/después:
│   - Izq: habitación sin persiana (luz cruda, ventana abierta)
│   - Der: la misma habitación con persiana instalada
│   - Handle: línea vertical con ícono de LAMA (SVG propio)
│   - Al arrastrar: el movimiento es la persiana abriéndose
│ Instrucción: "Arrastrá para descubrir el cambio"
│ (Imágenes: [A CONFIRMAR — el cliente las provee])
│ Fallback si no hay fotos: placeholder cromático con mensaje)
├─────────────────────────────────────────────────────────┤
│ #galeria — GALERÍA MASONRY (3 cols desktop / 2 cols tablet / 1 mobile)
│ 6-9 imágenes de instalaciones reales
│ Sin textos sobre las imágenes
│ Hover: overlay oscuro con tipo de producto
│ [A CONFIRMAR: cantidad y tipo de fotos disponibles]
├─────────────────────────────────────────────────────────┤
│ #proceso — TIMELINE HORIZONTAL (4 pasos)
│ 01 Consultá sin cargo
│ 02 Elegí tu línea Hunter Douglas
│ 03 Medición y presupuesto en obra
│ 04 Instalación profesional y garantía
│ Numeración tipográfica grande, sin íconos de stock
├─────────────────────────────────────────────────────────┤
│ #contacto — CTA FINAL + DATOS
│ H2: "Empezá tu proyecto hoy."
│ Botón WhatsApp primario (grande, --accent)
│ Formulario secundario: Nombre · Teléfono · Mensaje · Enviar
│ Dirección / zona de cobertura [A CONFIRMAR]
│ Horario de atención [A CONFIRMAR]
├─────────────────────────────────────────────────────────┤
│ FOOTER
│ Logo · Links de nav · Hunter Douglas badge pequeño
│ © 2026 Virginia Zab | Diseñado por GROWTHMARK
│ RRSS [A CONFIRMAR: IG, FB]
└─────────────────────────────────────────────────────────┘
```

---

## 7. Stack técnico

### Decisión: HTML5 + CSS3 + JavaScript vanilla · Archivo único `index.html`

**Justificación:** Landing page de 1 página, sin routing, sin gestión de estado complejo, sin autenticación. React/Next.js sería overkill extremo (3-5x el tiempo de build para el mismo resultado). HTML/CSS/JS en un único archivo permite deploy inmediato a GitHub Pages, Netlify o Donweb/cPanel sin paso de build.

### Stack aprobado
- HTML5 semántico (`<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`, `<article>`)
- CSS3 con custom properties (variables CSS) — sin frameworks
- JavaScript ES6+ vanilla — sin jQuery, sin librerías externas para el carrusel
- Google Fonts vía CDN (preload + preconnect)
- WebP para todas las imágenes (con fallback `<picture>` + JPG)

### Librerías externas autorizadas (mínimas)
| Librería | Versión | Uso | CDN |
|---|---|---|---|
| Ninguna | — | El carrusel y el comparador se implementan en JS vanilla puro | — |

**Razón:** Cero dependencias externas = cero riesgo de rotura futura por cambios de API. El carrusel y el comparador son mecánicas lo suficientemente simples para JS vanilla.

### Mobile-first: OBLIGATORIO
Todas las reglas CSS se escriben primero para `375px`. Los breakpoints de expansión son:
- `@media (min-width: 768px)` — tablet
- `@media (min-width: 1024px)` — desktop
- `@media (min-width: 1440px)` — desktop wide

### Convenciones de código
- CSS: BEM-lite (`.seccion__elemento--modificador`)
- JS: camelCase, funciones con nombre descriptivo, comentarios en español
- HTML: indentación 2 espacios, atributos en orden: `id`, `class`, `src`/`href`, `alt`, `loading`, dimensiones

### Estructura de carpetas (aunque sea un archivo único, los assets se referencian así)
```
proyecto-virginia-zab/
├── index.html          ← archivo único con CSS y JS embebidos
└── assets/
    └── images/
        ├── hero/
        │   ├── slide-01.webp
        │   ├── slide-02.webp
        │   └── slide-03.webp
        ├── galeria/
        │   ├── trabajo-01.webp … trabajo-09.webp
        ├── comparador/
        │   ├── antes.webp
        │   └── despues.webp
        ├── logo-vz.svg         ← [A CONFIRMAR: logo del cliente]
        └── logo-hd.svg         ← Hunter Douglas oficial
```

---

## 8. Skills activas y orden de encadenamiento

**Tipo de proyecto:** Landing page comercial de producto físico con énfasis editorial y conversión.

**Orden de skills para el ejecutor:**

| Fase | Skill | Output obligatorio |
|---|---|---|
| 1 | `disenador-referencias-visuales-growthmark` | ADN visual confirmado: paleta HEX, par tipográfico, estructura de secciones adaptada al rubro. Si el output no tiene HEX exactos, no cuenta como ejecutada. |
| 2 | `web-designer-elite` | HTML esqueleto + sistema visual CSS completo (variables, escala tipo, grid). El ejecutor NO escribe contenido final en esta fase — pone placeholders marcados `[COPY]`. |
| 3 | `seo-strategist` | Meta tags completos por sección, schema JSON-LD `LocalBusiness`, alt text de todas las imágenes, robots.txt, sitemap.xml. |
| 4 | `design:design-critique` + `engineering:code-review` | Lista P0/P1/P2 con fix concreto. Los P0 se aplican de inmediato. |

**Skills de apoyo transversales:**
- `design:ux-copy` — para el copy de los CTAs, formulario y microcopy de error
- `design:accessibility-review` — antes del deploy

---

## 9. Copy

**Idioma:** Español Rioplatense (vos/te). Sin versión en inglés.

### CTAs principales (copy exacto, ≤ 4 palabras, imperativo)
| CTA | Contexto |
|---|---|
| `Pedí tu consulta` | Botón hero carousel (principal) |
| `Ver trabajos` | Link interno al #galeria |
| `Consultá por WhatsApp` | CTA flotante y sección contacto |
| `Enviar mensaje` | Submit del formulario |

### Headlines clave por sección
| Sección | Headline propuesto | Nota |
|---|---|---|
| Hero slide 1 | "Luz precisa. Espacio perfecto." | Cormorant Garamond, --step-4 |
| Hero slide 2 | "Hunter Douglas. La tecnología detrás del confort." | Más pequeño, --step-3 |
| Hero slide 3 | "Instalación profesional. Garantía de marca." | Énfasis en confianza |
| Credencial | "Proveedora oficial Hunter Douglas en [Ciudad]" | [A CONFIRMAR: ciudad] |
| Propuesta | "No vendemos persianas. Diseñamos la luz de tu hogar." | H2 editorial |
| Productos | "Las líneas que transforman cada ventana" | H2 de sección |
| Comparador | "Ver para creer." | Brevedad + misterio |
| Proceso | "Del primer llamado a la última lama instalada." | H2 del proceso |
| Contacto | "Empezá tu proyecto hoy." | H2 CTA final |

### Copy de la sección propuesta (ya redactado, ajustable por la cliente)
```
H2: No vendemos persianas. Diseñamos la luz de tu hogar.

P1: Cada ventana es diferente. Cada ambiente tiene una historia de luz propia.
    Por eso, antes de proponer cualquier producto, escuchamos. Entendemos
    cómo vivís el espacio, qué querés sentir en él y qué nivel de luz
    y privacidad necesitás en cada momento del día.

P2: Como proveedora oficial de Hunter Douglas, accedés al catálogo más
    completo de cortinas y persianas de Argentina: desde rollers blackout
    para el dormitorio hasta sistemas automatizados PowerView® que
    responden a un toque desde tu teléfono.

P3: Te asesoramos, medimos en obra, instalamos con precisión y te
    acompañamos en la postventa. Porque una persiana bien elegida dura
    décadas — y queremos que cada día que la uses recuerdes que elegiste bien.
```

### Reglas de copy
- Oraciones < 20 palabras.
- Voz activa. Prohibido empezar con "Somos" o "En [nombre]".
- Sin exclamaciones en copy informacional.
- Sin redundancias ("ya que", "de hecho", "básicamente").
- Densidad de keywords: mencionar "persianas" y "Hunter Douglas" naturalmente, sin stuffing.

---

## 10. SEO

### Keywords

| Keyword | Tipo | Intención | Dificultad | Página |
|---|---|---|---|---|
| `persianas Hunter Douglas [ciudad]` | Primaria | Comercial | Baja | Home |
| `cortinas roller [ciudad]` | Primaria | Comercial | Baja | Home |
| `persianas blackout [ciudad]` | Secundaria | Comercial | Baja | Home |
| `instalación persianas [ciudad]` | Secundaria | Comercial | Baja | Home |
| `Hunter Douglas Argentina dealer` | Secundaria | Navegacional | Baja | Home |
| `cortinas duette precio argentina` | Soporte | Informacional | Media | Home |
| `cómo elegir persianas hogar` | Soporte | Informacional | Baja | (backlog blog) |
| `virginia zab persianas` | Navegacional | Navegacional | Mínima | Home |

> `[A CONFIRMAR: ciudad y zona geográfica exacta]` — reemplazar en todas las keywords.

### Meta tags (index.html)
```html
<!-- Title: 52 chars — keyword primaria al inicio -->
<title>Persianas Hunter Douglas en [Ciudad] | Virginia Zab</title>

<!-- Description: 155 chars -->
<meta name="description" content="Proveedora oficial Hunter Douglas en [Ciudad]. Instalación profesional de persianas, cortinas roller, blackout y sistemas automatizados. Consultá sin cargo.">

<!-- Viewport + charset -->
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#8B5E3C">

<!-- Canonical -->
<link rel="canonical" href="https://[dominio].com.ar/">

<!-- Lang -->
<html lang="es-AR">

<!-- Open Graph (completo) -->
<meta property="og:type" content="website">
<meta property="og:title" content="Persianas Hunter Douglas en [Ciudad] | Virginia Zab">
<meta property="og:description" content="Proveedora oficial Hunter Douglas. Instalación profesional de persianas y cortinas en [Ciudad]. Consultá sin cargo.">
<meta property="og:image" content="https://[dominio].com.ar/assets/images/og-image-1200x630.jpg">
<meta property="og:url" content="https://[dominio].com.ar/">
<meta property="og:locale" content="es_AR">
<meta property="og:site_name" content="Virginia Zab Persianas">

<!-- Twitter Card -->
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="Persianas Hunter Douglas en [Ciudad] | Virginia Zab">
<meta name="twitter:description" content="Proveedora oficial Hunter Douglas. Instalación profesional de persianas y cortinas en [Ciudad].">
<meta name="twitter:image" content="https://[dominio].com.ar/assets/images/og-image-1200x630.jpg">
```

### Schema JSON-LD (LocalBusiness)
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "HomeAndConstructionBusiness",
  "name": "Virginia Zab — Persianas",
  "description": "Proveedora oficial Hunter Douglas. Venta, asesoramiento e instalación de persianas, cortinas roller, blackout y sistemas automatizados.",
  "url": "https://[dominio].com.ar/",
  "telephone": "[A CONFIRMAR: número de teléfono]",
  "email": "[A CONFIRMAR: email]",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "[A CONFIRMAR: dirección]",
    "addressLocality": "[A CONFIRMAR: ciudad]",
    "addressRegion": "[A CONFIRMAR: provincia]",
    "addressCountry": "AR"
  },
  "areaServed": {
    "@type": "GeoCircle",
    "geoMidpoint": {
      "@type": "GeoCoordinates",
      "latitude": "[A CONFIRMAR]",
      "longitude": "[A CONFIRMAR]"
    },
    "geoRadius": "50000"
  },
  "openingHoursSpecification": [A CONFIRMAR: horarios],
  "logo": "https://[dominio].com.ar/assets/images/logo-vz.svg",
  "image": "https://[dominio].com.ar/assets/images/og-image-1200x630.jpg",
  "priceRange": "$$",
  "brand": {
    "@type": "Brand",
    "name": "Hunter Douglas"
  }
}
</script>
```

### Checklist F — SEO mínimo no negociable (pegar completo del plan)

- [ ] `<title>` único y descriptivo (50-60 chars) con keyword primaria al inicio
- [ ] `<meta name="description">` (140-160 chars) con keyword + beneficio + CTA implícito
- [ ] `<meta name="viewport" content="width=device-width, initial-scale=1">`
- [ ] `<meta charset="utf-8">`
- [ ] `<link rel="canonical">`
- [ ] `<html lang="es-AR">`
- [ ] `og:title`, `og:description`, `og:image` (1200×630), `og:url`, `og:type` completos
- [ ] `twitter:card`, `twitter:title`, `twitter:description`, `twitter:image`
- [ ] `favicon.ico` presente
- [ ] `apple-touch-icon` (180×180)
- [ ] `manifest.json` con icons 192×192 y 512×512
- [ ] `<meta name="theme-color">` con --accent (#8B5E3C)
- [ ] `sitemap.xml` generado y accesible en la raíz
- [ ] `robots.txt` configurado (Allow: / con sitemap)
- [ ] URLs limpias (si se convierte en multi-página en el futuro: kebab-case)
- [ ] H1 único con keyword primaria (persianas + ciudad)
- [ ] H2/H3 jerárquicos sin saltos
- [ ] Alt text descriptivo con keyword natural en TODAS las imágenes informativas
- [ ] Schema `LocalBusiness` / `HomeAndConstructionBusiness` implementado y validado
- [ ] Google Rich Results Test sin errores
- [ ] Imágenes con `loading="lazy"` (excepto hero: `loading="eager" fetchpriority="high"`)

---

## 11. Deploy

- **Destino:** GitHub Pages (fase 1, prototipo) → Donweb cPanel vía SSH (fase 2, producción)
- **Pipeline:** Local → GitHub → Donweb (14 pasos del protocolo GROWTHMARK)
- **Dominio:** `[A CONFIRMAR: dominio registrado por la cliente]` / Supuesto: `virginiazabpersianas.com.ar`
- **Repositorio:** `github.com/growthmark/virginia-zab-persianas` `[A CONFIRMAR: visibilidad public/private]`
- **URL de rollback:** se completa post-deploy con el hash del commit inicial
- **Spec de efectos (web-designer-elite output):**
  - Fondo carrusel: imágenes editoriales a sangre, sin textura sintética
  - Overlay carrusel: `linear-gradient(to top, rgba(28,25,23,0.7) 0%, transparent 60%)`
  - Navbar: `backdrop-filter: blur(8px)` con transición de transparente a `rgba(245,239,232,0.95)` al scroll
  - Scroll: `scroll-behavior: smooth`
  - Entrada al viewport: `IntersectionObserver` con fade-up (0→1, translateY 24px→0, 600ms, stagger 60ms)
  - Cursor: sin cursor personalizado (innecesario para este rubro)
  - Favicon: iniciales "VZ" en --accent sobre --bg, SVG

---

## 12. Decisiones críticas y supuestos adoptados

### Track
Fast Track — confirmado 2026-08-13. Justificación: 1 página, contenido provisto por el cliente (fotos e información), objetivo claro de conversión, sin funcionalidades complejas.

### Supuestos por datos faltantes (`[A CONFIRMAR]`)

| ID | Dato faltante | Supuesto adoptado | Bloquea |
|---|---|---|---|
| AC-01 | Nombre comercial exacto | "Virginia Zab — Persianas" | Copy + title tag |
| AC-02 | Ciudad / zona de cobertura | Buenos Aires / GBA | Keywords + copy + schema |
| AC-03 | Logo existente | Se crea iniciales "VZ" tipográficas en --accent | Identidad |
| AC-04 | Paleta de marca propia | Usar paleta propuesta (sección 5) | Sistema visual |
| AC-05 | Número de WhatsApp | `wa.me/54[número]` | CTA principal |
| AC-06 | Fotos de trabajos | Placeholders cromáticos + mensaje "[Foto del cliente]" | Galería + comparador |
| AC-07 | Fotos del comparador antes/después | Placeholder: gradiente claro/oscuro con texto instructivo | Gesto único |
| AC-08 | Textos finales de la cliente | Textos propuestos en sección 9, ajustables en revisión | Copy |
| AC-09 | Dominio registrado | `virginiazabpersianas.com.ar` | Deploy |
| AC-10 | Redes sociales | Links de IG y FB en footer como `[A CONFIRMAR]` | Footer |
| AC-11 | Stats de trayectoria | "Más de X años · Y instalaciones" como `[DATOS CLIENTE]` | Credencial |
| AC-12 | Email de contacto | Formulario sin endpoint activo en el prototipo (action="#") | Formulario |

### Timeline (Fast Track — 5 días hábiles)

| Fase | Tarea | Días | Fecha estimada |
|---|---|---|---|
| F1 | Setup: estructura HTML, CSS variables, sistema tipográfico, grid | 1 | 2026-08-14 |
| F2 | Hero carousel: autoplay, flechas, dots, swipe mobile | 1 | 2026-08-15 |
| F3 | Secciones: credencial, propuesta, productos, proceso, contacto | 1 | 2026-08-18 |
| F4 | Gesto único: comparador antes/después con handle-lama | 0.5 | 2026-08-19 |
| F5 | Galería masonry + navbar sticky + animaciones de entrada | 0.5 | 2026-08-19 |
| F6 | Auto-revisión A-H: SEO, a11y, performance, testing | 0.5 | 2026-08-20 |
| F7 | Ajustes post-revisión + deploy GitHub Pages | 0.5 | 2026-08-20 |

**Total: 5 días hábiles. Entrega estimada: 2026-08-20.**

---

## 13. Backlog — iteraciones futuras

*(Se puebla en Fase F6 con P1/P2 que el cliente pospone)*

- [ ] Sección de testimonios/reseñas de clientes (requiere contenido real)
- [ ] Blog con artículos SEO informacionales ("cómo elegir persianas", "roller vs blackout")
- [ ] Integración con formulario activo (Formspree, Netlify Forms o backend propio)
- [ ] Video de fondo opcional en hero (si la cliente provee material)
- [ ] Sección de marcas aliadas adicionales (si tiene otros proveedores además de HD)
- [ ] Versión en inglés (si la clientela lo requiere — no previsto ahora)
- [ ] Google Analytics / Meta Pixel (requiere política de privacidad y consentimiento de cookies)

---

## 14. Historial de cambios (hitos pre-generados)

- **v1.0** — 2026-08-13 — Creación inicial del blueprint. CLAUDE.md completo generado por GROWTHMARK. ✅
- **v1.1** — ~2026-08-15 — Post-prototipo (fase F2): carrusel hero funcionando. Dirección visual aprobada. ⏳
- **v1.2** — ~2026-08-19 — Post-secciones completas + gesto único: P0 aplicados, backlog poblado. ⏳
- **v1.3** — ~2026-08-20 — Post-auto-revisión: SEO + a11y + testing. Ajustes finales documentados. ⏳
- **v2.0** — ~2026-08-20 — Deploy GitHub Pages. URL pública. Tag v1.0.0. Handoff completo. ⏳

---

## 15. Guía de handoff

### Cómo retomar el proyecto

```bash
# 1. Clonar
git clone https://github.com/growthmark/virginia-zab-persianas.git
cd virginia-zab-persianas

# 2. No hay dependencias — abrir directamente
open index.html
# O usar Live Server en VS Code

# 3. Build
# No hay paso de build — archivo único estático

# 4. Deploy GitHub Pages
git add .
git commit -m "descripción"
git push origin main
# Pages se actualiza automáticamente en 1-2 min

# 5. Deploy Donweb (producción)
# Ver pipeline de 14 pasos en CLAUDE.md-agente-ceo.md de GROWTHMARK
```

### Archivos críticos
| Archivo | Qué hace |
|---|---|
| `index.html` | TODO el sitio — HTML + CSS embebido + JS embebido |
| `assets/images/hero/` | Imágenes del carrusel (provistas por la cliente) |
| `assets/images/comparador/` | Par antes/después para el gesto único |
| `assets/images/galeria/` | Fotos de trabajos realizados |

### Decisiones que NO se pueden tocar sin alertar al cliente
- El par tipográfico Cormorant Garamond + Source Sans 3 (define la identidad)
- El color acento `#8B5E3C` (terracota/madera — elegido para comunicar materialidad)
- El handle del comparador con forma de lama (es el gesto único del proyecto)
- Los badges de Hunter Douglas (usar assets oficiales — no recrear el logo de HD a mano)

### Plan de mantenimiento sugerido
- **3 meses:** Actualizar fotos de galería con nuevos trabajos. Revisar que los links de HD no hayan cambiado.
- **6 meses:** Revisión de performance (Lighthouse). Verificar accesibilidad.
- **1 año:** Revisión de copy con la cliente. Evaluar si agregar sección de blog.

### Backlog activo (pendiente del cliente)
→ Ver sección 13.

---

## ANEXO A — Especificación técnica del carrusel hero

```javascript
/*
 * CARRUSEL HERO — Especificación funcional completa
 * Implementar en JS vanilla puro. Sin librerías.
 *
 * Comportamiento:
 * - 3 slides (o más según fotos disponibles)
 * - Auto-advance: 5000ms (5 segundos)
 * - Transición: fade cross-dissolve + scale sutil (1.05 → 1.0)
 * - Duración de transición: 800ms
 * - Easing: cubic-bezier(0.22, 1, 0.36, 1)
 * - Pausa al hover en desktop
 * - Pausa al focus en cualquier elemento interno
 * - Reanuda al blur
 * - Touch/swipe en mobile: detectar deltaX > 50px para cambiar slide
 * - Dots: actualización sincronizada con la transición (no al inicio del fade)
 * - Flechas: L/R visibles en desktop, ocultas en mobile (swipe reemplaza)
 *
 * Accesibilidad:
 * - role="region" aria-label="Galería de imágenes" en el contenedor
 * - aria-live="polite" en el contador de slides ("1 de 3")
 * - Botones de flecha con aria-label="Slide anterior" / "Slide siguiente"
 * - prefers-reduced-motion: detener auto-advance, deshabilitar cross-dissolve (corte directo)
 *
 * HTML mínimo del carrusel:
 *
 * <section id="hero" class="hero" role="region" aria-label="Galería de imágenes destacadas">
 *   <div class="hero__track">
 *     <div class="hero__slide hero__slide--active" aria-hidden="false">
 *       <img src="assets/images/hero/slide-01.webp" alt="[Alt descriptivo con keyword]"
 *            loading="eager" fetchpriority="high" width="1920" height="1080">
 *       <div class="hero__overlay"></div>
 *       <div class="hero__content">
 *         <p class="hero__eyebrow">Proveedora oficial Hunter Douglas</p>
 *         <h1 class="hero__title">Luz precisa.<br>Espacio perfecto.</h1>
 *         <a href="#contacto" class="btn btn--primary">Pedí tu consulta</a>
 *       </div>
 *     </div>
 *     <!-- slides 2 y 3 con aria-hidden="true" cuando inactivos -->
 *   </div>
 *   <button class="hero__arrow hero__arrow--prev" aria-label="Slide anterior">&#8592;</button>
 *   <button class="hero__arrow hero__arrow--next" aria-label="Slide siguiente">&#8594;</button>
 *   <div class="hero__dots" role="tablist">
 *     <button class="hero__dot hero__dot--active" role="tab" aria-label="Slide 1 de 3" aria-selected="true"></button>
 *     <button class="hero__dot" role="tab" aria-label="Slide 2 de 3" aria-selected="false"></button>
 *     <button class="hero__dot" role="tab" aria-label="Slide 3 de 3" aria-selected="false"></button>
 *   </div>
 * </section>
 */
```

## ANEXO B — Especificación técnica del comparador (gesto único)

```javascript
/*
 * COMPARADOR ANTES/DESPUÉS — Gesto único del proyecto
 *
 * Mecánica:
 * - Dos imágenes superpuestas (antes / después)
 * - La imagen "después" se recorta con clip-path dinámico: clip-path: inset(0 X% 0 0)
 *   donde X es el porcentaje de posición del handle (0% = solo "después", 100% = solo "antes")
 * - El handle es una línea vertical SVG con forma estilizada de LAMA de persiana:
 *   un rectángulo horizontal muy angosto (4px x 40px) con borde redondeado
 *   y dos flechas < > a los costados
 * - Position inicial del handle: 50% (centro)
 * - Drag: mousemove + touchmove. Solo anima transform + clip-path (60fps garantizado)
 * - NO usar left/width para mover el handle — usar transform: translateX()
 *
 * Instrucción visible: "Arrastrá para descubrir el cambio"
 * (texto de --step--1, color --text-2, centrado bajo el comparador)
 * Desaparece al primer drag (se agrega clase .comparador--usado)
 *
 * Accesibilidad:
 * - role="img" aria-label="Comparación: habitación antes y después de instalar persiana"
 * - prefers-reduced-motion: handle fijo en 50%, sin animación de intro
 *
 * CSS clave:
 * .comparador { position: relative; overflow: hidden; cursor: ew-resize; }
 * .comparador__img-antes { position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover; }
 * .comparador__img-despues { position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover;
 *                             clip-path: inset(0 50% 0 0); transition: clip-path 0.05s linear; }
 * .comparador__handle { position: absolute; top: 0; bottom: 0; width: 2px; background: var(--white);
 *                        transform: translateX(-50%); left: 50%; cursor: ew-resize; }
 * .comparador__lama { /* SVG del handle */ }
 */
```

---

*CLAUDE.md — Virginia Zab Persianas · v1.0 · 2026-08-13 · GROWTHMARK*
*Para dudas sobre este documento: Gigi Stuppia / franconicolasferrari@gmail.com*

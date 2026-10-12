# Informe SEO — Virginia Zab (Hunter Douglas, Benavidez, Tigre)

Fecha: 2026-10-12 | Modo: diagnóstico | Archivos auditados: `index.html`, `productos.html` (raíz del proyecto, no hay carpeta `site/`)

## Qué supuse y qué no pude verificar

- No hay `01-estrategia.md` ni `04-copy.md`; trabajé con `specs/00-brief.md` y con el código.
- El sitio no está accesible por dominio (DNS pendiente) y no tengo la URL de Vercel. **No pude** consultar `site:dominio`, PageSpeed Insights ni el perfil de Google Business Profile. Todo lo de indexación y rendimiento sale del código y va marcado como "estimado, no medido".
- Las búsquedas web que hice ("cortinas Hunter Douglas Tigre", "cortinas roller Benavidez", "virginiazab.com.ar", "Virginia Zab cortinas") no devolvieron ningún negocio local de la zona ni el dominio de Virginia. Con esta herramienta no puedo ver el mapa de Google, así que **el análisis de competencia local queda como acción manual** (ver más abajo). No inventé competidores.

## Puntaje: 3 / 12

| Área | Puntaje | Resumen |
|---|---|---|
| 1. Indexación y técnico | 0 / 2 | No hay `robots.txt`, `sitemap.xml`, canonical ni `vercel.json`. `lang="es"` en vez de `es-AR`. Dominio sin DNS. Sin favicon. |
| 2. On-page | 1 / 2 | Un solo H1 por página y jerarquía correcta. Pero los títulos no tienen zona, las descriptions no tienen CTA y el H1 de la home cambia por JS. |
| 3. SEO local | 0 / 2 | Cero schema. "Benavidez, Tigre" aparece una sola vez, en el footer. Sin mapa, sin horarios, NAP inconsistente. |
| 4. Contenido e intención | 1 / 2 | Los 19 sistemas tienen texto indexable, pero es copia del catálogo de Hunter Douglas. No hay FAQ ni contenido de zona. |
| 5. Rendimiento visto por Google | 1 / 2 | Fuentes con `preconnect` y `display=swap`, imágenes de producto con `loading="lazy"`. Pero las `<img>` no llevan `width`/`height`, quedan 15 JPG de 100–270 KB y el hero es background CSS. |
| 6. Buscadores con IA | 0 / 2 | No hay una frase citable "Virginia Zab + rubro + zona", ni schema, ni FAQ. |

## Hallazgos por área

### 1. Indexación y técnico (0/2)
- Faltan `robots.txt` y `sitemap.xml` en la raíz.
- Ninguna página tiene `<link rel="canonical">`. Cuando salga el dominio, el sitio va a existir en `*.vercel.app` y en `virginiazab.com.ar` (contenido duplicado) y en `www` / sin `www`.
- `<html lang="es">` en las dos páginas. Debería ser `es-AR`.
- Sin favicon ni `theme-color` (no hay ningún `<link rel="icon">`).
- Sin `og:` ni `twitter:` tags: al compartir el link por WhatsApp o Instagram no sale tarjeta con imagen.
- No hay `<main>` en ninguna de las dos páginas (solo `<nav>`, `<section>`, `<footer>`).
- Sin página 404 propia. No hay `vercel.json` para redirecciones ni headers.
- Positivo: HTTPS lo da Vercel, URLs legibles (`productos.html`), un único H1 por página, `rel="noopener"` en enlaces externos.
- Indexación actual: no verificable (estimado, no medido: con el dominio sin DNS, lo más probable es que Google no conozca el sitio).

### 2. On-page (1/2)

| Página | Title actual | Problema |
|---|---|---|
| `index.html` | "Virginia Zab — Cortinas & Persianas Hunter Douglas" (50) | Sin zona. Dice "Persianas" pero el sitio vende cortinas (en Argentina "persianas" suele leerse como persiana exterior de aluminio: intención distinta, estimado). |
| `productos.html` | "Productos Hunter Douglas — Virginia Zab" (39) | Sin zona ni palabra clave de intención ("cortinas"). |

- Description de la home (118 caracteres): lista Luminette, que **no existe en el sitio** (grep: solo aparece en la meta). Sin zona y sin CTA.
- Description de `productos.html` (≈210 caracteres): pasa los 155 y se corta en Google. Sin CTA.
- **H1 de la home:** el HTML inicial dice "Elegancia y precisión" y el JS (`setSlideText`) lo reemplaza cada pocos segundos por "Diseño con oficio", "Amplitud y resistencia", "Sombra a medida". Ninguna versión tiene una palabra clave ni la zona. El H1 es hoy la señal más débil de la home.
- Home: jerarquía H2/H3 bien. Los H4 de "Quiénes somos" saltan de nivel (H2 a H4) y deberían ser H3.
- Imágenes: las de `productos.html` tienen alt, pero con patrón repetido ("X — Hunter Douglas") sin describir el ambiente. La galería, los 4 slides del hero y las 6 tarjetas bento de la home son `background-image` en CSS, así que **no tienen alt y Google Imágenes no las indexa**. El logo de Hunter Douglas del footer sí tiene alt.
- Enlaces internos: el nav de la home apunta bien a `productos.html#...`. Los enlaces del footer de "Productos" (Cortinas, Toldos, Pérgolas, Cubierta, Persianas, PowerView) **mandan al sitio de Hunter Douglas** en vez de a las secciones propias de `productos.html`. Se pierde tráfico y relevancia interna. En `productos.html` hay 19 enlaces "Ficha en Hunter Douglas ↗" salientes, uno por producto.
- Texto de "Quiénes somos": decir "Distribuidores exclusivos" y no "dealer oficial" no coincide con el brief (que dice "dealer oficial"). Ver acciones.

### 3. SEO local (0/2)
- **Sin ningún JSON-LD.** No hay `LocalBusiness`, `areaServed`, `openingHours`, `sameAs` ni `geo`.
- **NAP inconsistente:** el bloque de marca del footer tiene "Agustín M. García 6752, Benavidez, Tigre", pero la columna "Contacto" del mismo footer dice "Buenos Aires, Argentina". El teléfono solo existe como link `wa.me` (no hay `tel:`). La dirección enlaza a `maps.google.com/?q=` en vez de tener un mapa embebido.
- "Benavidez" y "Tigre" aparecen **una sola vez** en todo el sitio (la dirección). El resto del sitio habla de "Buenos Aires" en general (hero eyebrow, footer, badge de Hunter Douglas), una zona demasiado amplia para competir.
- Sin horarios. Sin página o sección de zona de cobertura.
- Instagram `virginia.zab` está enlazado; sirve para `sameAs`. No hay Facebook ni otra red.
- Google Business Profile: **no verificable desde acá**. Acción manual.

### 4. Contenido e intención (1/2)
Búsquedas principales y si hay respuesta en el sitio (demanda: estimada, no medida):

| Búsqueda | Intención | Demanda | ¿Página que la responde? |
|---|---|---|---|
| cortinas Hunter Douglas Tigre / zona norte | comercial local | media | No: sin zona en el texto |
| cortinas roller Benavidez / Tigre | comercial local | media | Parcial (`productos.html#cortinas`) sin zona |
| cortinas Duette / Silhouette / Pirouette precio | comparación / info | media-alta | Parcial: hay ficha, pero el texto es del catálogo de Hunter Douglas |
| cortinas motorizadas zona norte | comercial | media | Parcial (sección PowerView) |
| toldos y pérgolas Tigre / Benavidez | comercial local | media | Parcial |
| cortinas para casas en barrios cerrados Tigre / Nordelta | comercial local | media (requiere confirmar que atienden) | No |
| presupuesto cortinas a medida con instalación | transaccional | media | CTA presente, sin explicar proceso ni plazos |

- **Texto duplicado:** `productos.html` dice en su propio encabezado "con las descripciones del catálogo oficial de Hunter Douglas". Las 19 descripciones son copia del sitio del fabricante. Es el mayor riesgo de contenido duplicado y le da a Google razón para mostrar a Hunter Douglas antes que a Virginia.
- No hay FAQ. No hay contenido que responda "cuánto cuesta", "cuánto tarda", "qué cortina para dormitorio / living / pileta", "garantía", "se instalan en toda la zona norte".
- El brief nombra Vignette y Luminette, pero el sitio no las tiene. Hay que decidir si se agregan o se sacan de la meta.
- **No recomiendo** páginas por barrio hasta confirmar qué zonas atienden de verdad y tener texto propio para cada una.

### 5. Rendimiento visto por Google (1/2) — estimado, no medido
- `assets/` pesa 4,1 MB. 15 JPG pesan entre 137 y 270 KB cada uno (los más pesados: Duette Architella 270 KB, Horizontales de Aluminio 260 KB, Lunero 254 KB). Con WebP/AVIF bajan a la mitad.
- HTML con CSS inline: 71 KB (home) y 79 KB (productos). No es grave, pero no se cachea entre páginas.
- Casi ninguna `<img>` tiene `width`/`height` (solo el logo de Hunter Douglas), lo que puede provocar saltos de layout (CLS) en `productos.html`.
- El hero (LCP probable) es un `background-image` inline, sin `preload`. Cargar una imagen de 130 KB (`hd-living-sheer.webp`) como fondo retrasa el LCP.
- Fuentes: `preconnect` y `display=swap` bien. Cargan 2 familias (Cormorant Garamond y Syne), razonable.
- Para el detalle profundo, usar `/arterix-tecnico` una vez que haya URL pública (y correr PageSpeed Insights).

### 6. Visibilidad en buscadores con IA (0/2)
- El texto está en HTML (bien), pero no hay una frase que un modelo pueda citar del tipo "Virginia Zab es dealer oficial de Hunter Douglas en Benavidez, Tigre, y vende e instala cortinas roller, Duette, Silhouette, toldos y motorización PowerView".
- Sin schema, sin FAQ con respuestas directas, sin horarios ni zona de cobertura en texto.
- Los datos de contacto están en texto (bien), pero la zona es "Buenos Aires, Argentina".

### Competencia
No pude verificarla (ver arriba). Acción manual para Gigi: en Google, buscar "cortinas Hunter Douglas Tigre", "cortinas roller Benavidez" y "cortinas zona norte" desde el celular, anotar quién sale en el mapa (3 resultados) y en orgánico, cuántas reseñas y fotos tienen y qué páginas de zona publican. Dejarlo anotado acá.

## Plan priorizado

### A. Lo arreglo yo con `/arterix-seo aplicar` (solo head, schema, textos SEO, alt, enlaces, sitemap, robots)

| # | Acción | Impacto | Esfuerzo | Dónde |
|---|---|---|---|---|
| A1 | `<html lang="es-AR">`, canonical (`https://virginiazab.com.ar/` y `/productos.html`), `robots.txt` y `sitemap.xml` | alto | bajo | sitio |
| A2 | Title y description nuevos con zona y CTA (propuesta abajo). Sacar "Luminette" de la meta | alto | bajo | sitio |
| A3 | JSON-LD `LocalBusiness` (subtipo `HomeGoodsStore`) con NAP, `areaServed`, `sameAs` (Instagram), `hasMap`; faltan horarios (ver B) | alto | medio | sitio |
| A4 | Unificar NAP en footer: dirección completa también en la columna "Contacto", agregar `tel:` además del `wa.me`, y corregir "Buenos Aires, Argentina" por "Benavidez, Tigre, Buenos Aires" | alto | bajo | sitio |
| A5 | Open Graph + Twitter Card y favicon (usando `logo-virginia-zab.png`; la imagen social de 1200x630 es un asset nuevo, ver B) | medio | bajo | sitio |
| A6 | Footer "Productos" de la home: apuntar a `productos.html#...` en vez de a hunterdouglas.com.ar | medio | bajo | sitio |
| A7 | `width`/`height` en `<img>` de `productos.html`; alts descriptivos (ambiente + producto + marca) | medio | bajo | sitio |
| A8 | `<main>` envolviendo el contenido; H4 de "Quiénes somos" a H3; actualizar "© 2025" a 2026 | bajo | bajo | sitio |
| A9 | `vercel.json` con redirección de `*.vercel.app` y `www` al dominio principal, y `404.html` mínima | medio | bajo | sitio |
| A10 | `<link rel="preload" as="image">` del primer slide del hero | bajo | bajo | sitio |

Excluido de "aplicar" porque toca diseño o copy: H1 de la home, galería/bento con `<img>` en vez de background, sección FAQ, reescritura de fichas. Ver C.

### B. Requiere acción de Gigi o de Virginia (el cliente)

| # | Acción | Impacto | Esfuerzo | Dónde |
|---|---|---|---|---|
| B1 | **Google Business Profile:** crear o reclamar la ficha. Categoría principal: "Tienda de cortinas" (o la más cercana disponible), secundarias: "Tienda de persianas", "Proveedor de toldos". Dirección Agustín M. García 6752, Benavidez. Si no atienden público en local, configurarlo como negocio de servicio en el área, con zona de cobertura en lugar de dirección visible | alto | medio | Google Business Profile |
| B2 | Confirmar si hay **showroom con atención al público** y horarios `[A CONFIRMAR: horarios]`. Define si va mapa embebido y `openingHoursSpecification` | alto | bajo | cliente |
| B3 | Confirmar **zonas que atienden de verdad** `[A CONFIRMAR: partidos/barrios]` (Tigre, Nordelta, San Isidro, Pilar, Escobar…). Sin esto no se escriben textos de zona | alto | bajo | cliente |
| B4 | Confirmar el **término correcto**: el brief dice "dealer oficial" y el sitio dice "Distribuidores exclusivos Hunter Douglas" (home y footer). "Exclusivos" es una afirmación fuerte `[A CONFIRMAR: con Hunter Douglas Argentina]`. También "más de 9 años" `[A CONFIRMAR]` | alto (confianza y riesgo legal) | bajo | cliente |
| B5 | Pedir **fotos reales** de instalaciones (con permiso) para galería, GBP y alt descriptivos. Hoy todo es material de Hunter Douglas | alto | medio | cliente |
| B6 | Pedir **reseñas** a clientes reales a GBP (link corto) | alto | bajo | cliente |
| B7 | Contratar el dominio, apuntar DNS en Vercel, validar en **Google Search Console** y enviar `sitemap.xml` | alto | bajo | Gigi |
| B8 | Preguntar si figura en el **buscador de distribuidores de hunterdouglas.com.ar** y pedir el enlace al sitio desde ahí (backlink de alta autoridad) | alto | bajo | cliente |
| B9 | Datos de contacto en directorios coherentes con el NAP (Páginas Amarillas, Cylex, Instagram, Facebook): mismo nombre, dirección y teléfono | medio | medio | fuera del sitio |
| B10 | Imagen social 1200x630 con la marca (para A5) | bajo | bajo | Gigi |

### C. Contenido nuevo / decisión de diseño (derivar a copy y constructor)

| # | Acción | Impacto | Esfuerzo | Dónde |
|---|---|---|---|---|
| C1 | **H1 de la home** con palabra clave y zona, fijo, p. ej. "Cortinas Hunter Douglas en Benavidez y zona norte", y los textos de los slides pasan a `<p>` o `<h2>` visuales. Cambia la jerarquía del hero: decide Gigi | alto | bajo | sitio (diseño) |
| C2 | **Reescribir las 19 fichas** de `productos.html` con voz propia (qué ambiente resuelve cada una, qué recomienda Virginia, cuándo no conviene), sin copiar al catálogo | alto | alto | contenido |
| C3 | **FAQ** en home o en página aparte (6 a 8 preguntas, ver abajo) con schema `FAQPage` | alto | medio | contenido |
| C4 | Sección "Cómo trabajamos" con pasos y plazos (`[A CONFIRMAR]`): asesoramiento, medición, confección, instalación | medio | medio | contenido |
| C5 | Si B3 confirma varias zonas: una página por zona **solo** con texto genuino (obras, tiempos de visita, ejemplos). Nunca duplicadas cambiando el barrio | medio | alto | contenido |
| C6 | Galería y bento de la home con `<img>` con alt (hoy son backgrounds) | medio | medio | sitio (cuidando el diseño) |
| C7 | Convertir imágenes JPG a WebP/AVIF y generar versiones responsive (`srcset`) | medio | medio | sitio |
| C8 | Sección de mapa embebido (si B2 confirma local abierto) | medio | bajo | sitio |
| C9 | Una página por línea de producto solo si hay texto propio y fotos reales (Duette, Silhouette, PowerView) | medio | alto | contenido |

## Propuestas de textos (para A2 y el plan de keywords)

Palabra clave principal de la home: **cortinas Hunter Douglas en Benavidez / Tigre** (estimado, no medido: demanda media, intención comercial local).

| Página | Búsqueda principal (una sola por página) | Title (≤60) | Meta description (≤155) |
|---|---|---|---|
| `index.html` | cortinas Hunter Douglas Tigre / Benavidez | Cortinas Hunter Douglas en Benavidez, Tigre \| Virginia Zab (58) | Dealer oficial Hunter Douglas en Benavidez, Tigre. Cortinas roller, Duette, Silhouette, toldos y motorización PowerView. Pedí tu cotización por WhatsApp. (≈153) `[A CONFIRMAR: "dealer oficial" vs "exclusivos"]` |
| `productos.html` | catálogo cortinas Hunter Douglas (variantes por producto) | Catálogo de cortinas Hunter Douglas \| Virginia Zab (50) | Roller, Duette, Silhouette, Pirouette, toldos, pérgolas y PowerView. Elegí el sistema y consultanos por WhatsApp desde Benavidez, Tigre. (≈140) |

Preguntas para el FAQ (salen de la estructura del negocio y de lo que suele preguntarse en el rubro; contrastar con "otras preguntas de los usuarios" en Google): qué diferencia hay entre Roller, Duette y Silhouette; qué cortina conviene para dormitorio con oscurecimiento total; cuánto tarda la fabricación y la instalación `[A CONFIRMAR]`; si hacen la medición en el domicilio y en qué zonas `[A CONFIRMAR]`; cómo es la garantía `[A CONFIRMAR]`; cómo funciona PowerView y si se integra con Alexa, Google o HomeKit; si trabajan con arquitectos e interioristas; cómo se cotiza.

### Schema recomendado (A3)
Tipo `HomeGoodsStore` (subtipo de `LocalBusiness`), con: `name` "Virginia Zab", `description` (la frase citable), `url`, `image`, `telephone` "+5491156570336", `email` "info@virginiazab.com.ar", `address` (PostalAddress: streetAddress "Agustín M. García 6752", addressLocality "Benavidez", addressRegion "Buenos Aires", addressCountry "AR"), `areaServed` (según B3), `sameAs` ["https://www.instagram.com/virginia.zab"], `brand` Hunter Douglas, `hasMap`. Falta: horarios, coordenadas `geo` y código postal `[A CONFIRMAR]`. Sumar `FAQPage` cuando exista C3.

## Los tres cambios que más mueven la aguja
1. **Zona y rubro en title, description, H1 y schema** (A2 + A3 + C1): hoy el sitio no le dice a Google que está en Benavidez, Tigre.
2. **Google Business Profile completo y con reseñas** (B1 + B5 + B6): para un comercio local es lo que define si aparece en el mapa.
3. **Contenido propio en lugar del copiado del catálogo** (C2 + C3): evita el duplicado con Hunter Douglas y responde las búsquedas de decisión.

## Seguimiento
Cuando el dominio esté publicado: correr `site:virginiazab.com.ar`, PageSpeed Insights de las dos URLs, Search Console, y completar la sección de competencia. Después de aplicar A1 a A10, actualizar este informe con una sección "Cambios aplicados".

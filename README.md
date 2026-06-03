# Instituto Juan Salvador Gaviota — Sitio Web

Sitio institucional del **Instituto Juan Salvador Gaviota**, Villa Rumipal, Córdoba, Argentina.

---

## Estructura de la página

El sitio es un único archivo `index.html` autocontenido (sin dependencias externas de assets), con todo el CSS y el JavaScript embebidos. Las imágenes y el logo están codificados en **base64** dentro del mismo archivo.

### Secciones

| Sección | Descripción |
|---|---|
| **Nav** | Barra fija con logo, links de navegación y menú hamburguesa mobile |
| **Hero** | Portada principal con título, subtítulo, descripción y botones de acción |
| **Filosofía** | Franja destacada con los valores institucionales |
| **Nosotros** | Presentación del instituto e inspiración en Juan Salvador Gaviota |
| **Pedagogías 3000 · 4000 · 5000** | Descripción del modelo pedagógico con círculo animado y pilares |
| **Propuesta** | Tres líneas curriculares en cards (Arte, Ciencias, Humanidades) |
| **Cita** | Sección oscura con cita de Richard Bach |
| **Vida Escolar** | Grid de actividades (música, arte, deporte, tecnología, naturaleza) |
| **Galería** | Grilla fotográfica con imágenes de la institución |
| **Contacto** | Formulario de contacto + datos institucionales |
| **Footer** | Links, información legal y redes sociales |

### Recursos multimedia

- `grand_project-children-folk-130485.mp3` — música de fondo (5.6 MB)
- `ribhavagrawal-no-copyright-solo-flute-music-476638.mp3` — música alternativa (7.8 MB)

Ambos archivos son reproducidos desde un **widget de música flotante** (esquina inferior derecha).

### Tipografías

Cargadas desde Google Fonts:
- **Playfair Display** — títulos
- **Raleway** — cuerpo de texto
- **Cormorant Garamond** — citas y subtítulos

---

## Adaptación para mobile (rama `mobile-responsive`)

El HTML original tenía estilos responsive básicos pero presentaba varios problemas en pantallas pequeñas. Se agregaron los siguientes ajustes **sin modificar contenido ni diseño**:

### Problemas resueltos

| Problema | Solución |
|---|---|
| Links del nav desaparecían en mobile sin alternativa | Menú hamburguesa (☰) con panel full-screen y cierre automático al navegar |
| Scroll horizontal involuntario | `overflow-x: hidden` en `html` + reemplazo de `transform: translateX()` por `visibility/opacity` para evitar overflow en elementos `fixed` |
| Sección "Nosotros" no colapsaba a columna única | Grid definido como `style` inline → requirió `!important` en la media query para sobrescribir |
| Círculos decorativos desbordaban la pantalla | Tamaños reducidos por breakpoint (900px / 600px / 400px) |
| Botones uno al lado del otro en pantallas pequeñas | Se apilan verticalmente en ≤ 600px |
| Círculo animado de pedagogía muy grande | Escalado progresivo según breakpoint |
| Franja de filosofía horizontal en mobile | Se convierte en columna centrada |
| Panel del reproductor de música | Ancho adaptado al viewport en mobile |

### Breakpoints

| Breakpoint | Ajustes principales |
|---|---|
| `≤ 900px` | Hamburguesa activa, grids a 1 columna, padding reducido |
| `≤ 600px` | Botones apilados, círculo pedagógico escalado, footer en columna |
| `≤ 400px` | Padding mínimo, logo y tipografía reducidos |

---

## Infraestructura

### Dominio

- **Dominio:** `institutojuansalvadorgaviota.org`
- **Registrador:** [Hostinger](https://hostinger.com)
- **Cuenta Hostinger:** Emanuel Rodriguez — rodgerema@gmail.com
- **Nameservers apuntados a Cloudflare:** `dylan.ns.cloudflare.com` / `elsa.ns.cloudflare.com`

### Hosting

- **Plataforma:** [Cloudflare Pages](https://pages.cloudflare.com) (plan Free)
- **Cuenta Cloudflare:** ijsgaviota@gmail.com
- **Proyecto Pages:** `inst-jsgaviota`
- **URL Pages:** https://inst-jsgaviota.pages.dev

### URLs activas

| URL | Destino |
|---|---|
| `https://institutojuansalvadorgaviota.org` | ✅ Sitio en producción |
| `https://www.institutojuansalvadorgaviota.org` | 301 → raíz |
| `http://institutojuansalvadorgaviota.org` | 301 → HTTPS |
| `https://mobile-responsive.inst-jsgaviota.pages.dev` | Preview de rama mobile |

### SSL

Certificado gestionado automáticamente por Cloudflare (Google Trust Services). Renovación automática.

---

## Posicionamiento SEO

### Archivos generados

| Archivo | Descripción |
|---|---|
| `robots.txt` | Permite el rastreo completo e indica la ubicación del sitemap |
| `sitemap.xml` | Mapa del sitio enviado a Google Search Console |
| `og-image.jpg` | Imagen 1200×630px para preview en redes sociales y WhatsApp |

### Meta tags implementados en `index.html`

| Tag | Valor |
|---|---|
| `<title>` | Incluye nombre del instituto, niveles educativos y ubicación |
| `meta description` | Descripción de 160 caracteres con keywords principales |
| `meta keywords` | Términos clave del instituto y la zona |
| `link canonical` | URL canónica para evitar contenido duplicado |
| Open Graph (`og:*`) | Título, descripción, imagen, locale, tipo y nombre del sitio |
| Twitter Card | `summary_large_image` con título, descripción e imagen |
| Schema.org JSON-LD | `EducationalOrganization` + `LocalBusiness` con dirección, teléfono y horario |

### Estado de configuración externa

| Herramienta | Estado |
|---|---|
| Google Search Console | ✅ Verificado vía DNS (Cloudflare) — sitemap enviado y procesado |
| sitemap.xml | ✅ Procesado correctamente (1 página descubierta) |
| Facebook Sharing Debugger | ✅ OG tags detectados sin errores |
| Google Analytics GA4 | ✅ Activo — ID: `G-1HCVSGVRF7` |
| Google Business Profile | ⏳ Perfil creado — verificación de propiedad pendiente |

### Analytics

- **Plataforma:** Google Analytics 4
- **ID de medición:** `G-1HCVSGVRF7`
- **Cuenta:** ijsgaviota@gmail.com
- El script está embebido en el `<head>` de `index.html`
- Verificar en: analytics.google.com → Informes → Tiempo real

### Palabras clave objetivo

- `Instituto Juan Salvador Gaviota`
- `colegio Villa Rumipal`
- `escuela Pedagogía 3000 Córdoba`
- `educación inicial primaria secundaria Villa Rumipal`
- `escuela alternativa sierras Córdoba`

### Checklist completo SEO (Guía Google)

| Ítem | Estado |
|---|---|
| Título único con keywords y ubicación | ✅ |
| Meta description | ✅ |
| URL canónica | ✅ |
| Open Graph (Facebook / WhatsApp / LinkedIn) | ✅ |
| Twitter Card | ✅ |
| Schema.org JSON-LD (institución + negocio local) | ✅ |
| Alt text en todas las imágenes (17/17) | ✅ |
| Links internos con texto descriptivo | ✅ |
| Links del footer funcionales (niveles, dirección, teléfono, email) | ✅ |
| Email del footer con `mailto:` | ✅ |
| robots.txt | ✅ |
| sitemap.xml enviado a Google | ✅ |
| Google Search Console | ✅ |
| Google Analytics GA4 | ✅ |
| Diseño mobile responsive | ✅ |
| HTTPS activo | ✅ |
| Google Business Profile | ⏳ verificación pendiente |

---

## Formulario de contacto (rama `form-n8n-whatsapp`)

El formulario de la sección Contacto envía los datos a un webhook de **n8n** que notifica por **WhatsApp Business** al número del instituto.

### Flujo

```
Usuario completa el form → POST al webhook n8n → n8n envía template WhatsApp → +54 9 3546 51-7331
```

### Configuración n8n

- **Webhook URL:** `https://n8n.automation-ia.tech/webhook/3d83d5d1-e9fb-426c-8277-c22995ec1af6`
- **Template WhatsApp:** `ijsgaviota_form` (idioma: `es_AR`)
- **Cuenta WhatsApp Business:** +54 9 3546 51-7331 (Tuenti N8n)
- **Parámetros del template (en orden):** `nombre`, `email`, `telefono`, `nivel`, `mensaje`

### Estado del template

El template original usaba **variables nombradas** (`{{nombre}}`, `{{email}}`...) que no son compatibles con n8n WhatsApp node v1. Se envió un nuevo template con **variables numeradas** (`{{1}}`, `{{2}}`...) para revisión de Meta. Estado: ⏳ pendiente de aprobación (~24 hs).

---

## Actualizaciones futuras

Para subir cambios al sitio, desde la carpeta del proyecto:

```bash
# Desplegar a producción
wrangler pages deploy . --project-name inst-jsgaviota --branch main --commit-dirty=true

# Desplegar como preview (sin afectar producción)
wrangler pages deploy . --project-name inst-jsgaviota --branch nombre-de-prueba --commit-dirty=true
```
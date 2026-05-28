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

## Actualizaciones futuras

Para subir cambios al sitio, desde la carpeta del proyecto:

```bash
# Desplegar a producción
wrangler pages deploy . --project-name inst-jsgaviota --branch main

# Desplegar como preview (sin afectar producción)
wrangler pages deploy . --project-name inst-jsgaviota --branch nombre-de-prueba
```